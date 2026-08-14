# Viral Scanner Gate

#BioForge #BioForge_V0_54T #Block #Scanner #Redstone #Containment #PlayerGuide #ModpackGuide

> Registry ID: `bioforge:viral_scanner`.

The full Viral Scanner Gate is a two-block-high walkthrough detector with both side frames and an upper beam. It faces the placer and occupies a paired lower/upper block state.

## Detection

- Every 10 ticks, the lower controller checks living entities inside its passage.
- An infected entity powers the scanner at redstone level 15.
- The signal clears when no detectable infected entity remains.
- The scanner reports only presence; it does not identify a strain or cure the subject.
- A strain carrying the `scanner_evasion` mutation tag passes undetected.

Breaking either half invalidates the paired structure. Use the full gate where collision framing on both sides is acceptable.

Related: [[Scanner Evasion]], [[Area Scanning and Redstone Detection]], [[Open-Left Viral Scanner]].

