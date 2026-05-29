#Extra

The mod uses **NBT obfuscation** to prevent players from reading or tampering with sensitive item data (blood samples, infection strains, medical records, etc.) via commands like `/data get` or inventory viewers.

- All blood data (type, amount, source UUID) is stored in an obfuscated format.
- Infection strain data (pathogen, symptoms, colony ID) is similarly protected.
- Clipboard and Medical Report data are also obfuscated.

Without obfuscation, a player could cheat by inspecting an item’s NBT to determine blood type without testing reagents, or copy infection strains without using a swab.

## How It Works

The `NbtObfuscator` class encrypts data using a combination of:

- **XOR encryption** with a derived key stream.
- **Random salt** (UUID) per write.
- **Checksum** (Adler‑32 style) to detect corruption.
- **Flag byte** to quickly verify if data exists.

Data is stored in the item’s `CompoundTag` under special keys:
- `bf_s0`, `bf_s1` - salt (XOR‑masked)
- `bf_p` - encrypted payload (byte array)
- `bf_c` - checksum
- `bf_f` - flag (derived from salt)

The keys are non‑descriptive to avoid easy discovery.

## Two Write Modes

### 1. Random salt (normal)
- Every write generates a new random UUID as salt.
- Used for most items (needles, swabs, petri dishes, etc.).
- Produces different obfuscated output even for identical plaintext - prevents pattern recognition.

### 2. Deterministic salt
- Used for infected crop drops (`writeStringDeterministic`).
- Salt is derived from the plaintext (SHA‑256 hash).
- Ensures that identical infection strains always produce the same obfuscated bytes. This allows drops from the same infected crop type to be stackable (identical NBT).

## API (for developers)

### Writing data

```java
// Write blood sample data
NbtObfuscator.write(tag, amount, typeName, sourceName, subjectUUID);

// Write arbitrary string (random salt)
NbtObfuscator.writeString(tag, payload);

// Write arbitrary string (deterministic salt)
NbtObfuscator.writeStringDeterministic(tag, payload);
```

### Reading data

```java
// Read blood sample data (returns ObfuscatedData record)
ObfuscatedData data = NbtObfuscator.read(tag);

// Read arbitrary string
String payload = NbtObfuscator.readString(tag);
```

### Checking presence

```java
if (NbtObfuscator.hasData(tag)) { ... }
```

### Clearing

```java
NbtObfuscator.clear(tag);
```