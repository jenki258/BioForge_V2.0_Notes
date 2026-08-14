# Mutation API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #Mutation #AddonDevelopment

Mutation JSON defines metadata, compatible pathogens, rarity/weight, enable/hidden state, requirements, conflicts, tags, effects, and interactions.

Built-in handlers cover symptom changes, route changes, potion/attribute effects, damage/heal/exhaustion/ignite, sound/particles, climbing, camouflage, light/grass/water reactions, respiration, effect clearing, and self-destruction. Java addons register a MutationEffectHandler for new executable types.

Handlers receive a server context and must be deterministic about cleanup, intervals, saved IDs, and client synchronization. Invalid effect targets must reject validation instead of throwing during entity ticks.
