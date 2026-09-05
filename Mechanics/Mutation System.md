# Mutation System

#BioForge #BioForge_V2_0 #Build_V0_54T #Mechanic #Mutation #JSON #PlayerGuide #ModpackGuide #AddonDevelopment

Mutations are reloadable strain definitions with compatibility, selection, lifecycle effects, and interactions. V0.54T bundles 81 definitions; the Universal pathogen class can use every bundled mutation.

## Acquisition

Mutations may be part of a natural strain, selected naturally/at random, granted by an interaction, introduced by a failed vaccine, added through a directed or random mutation vaccine, recovered as a rare wild-host gene, or assigned by command.

## Selection rules

Enabled state, pathogen compatibility, prerequisites, conflicts, hidden state, weight, rarity, and server switches are validated. Weight zero mutations are normally reached through explicit lifecycle/interaction/wild-host logic instead of random selection.

## Runtime

Effects may run on apply, continuously at an interval/chance, or on removal. Built-in effects can modify symptoms, add/remove routes, apply potion effects/attributes, deal damage, heal, exhaust, ignite, play sounds, spawn particles, climb, camouflage, clear effects, react to light/grass/water, breathe underwater, or self-destruct.

## Data safety

Invalid effect definitions are rejected rather than silently becoming broken runtime behavior. See [[Mutation Catalogue]], [[Mutation API]], and [[Testing and Validation]].
# 2.1 update

Mutation Upgrade Vaccine can raise a selected mutation tier, while the random upgrade variant chooses an eligible mutation from the infection. Universal strains support the full mutation catalogue; addon definitions remain data-driven.
