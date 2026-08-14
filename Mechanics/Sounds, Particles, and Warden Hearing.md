# Sounds, Particles, and Warden Hearing

#BioForge #BioForge_V0_54T #Mechanic #Sound #Particle #Warden #Accessibility #PlayerGuide

BioForge uses sounds/particles as readable disease and machine feedback.

Coughing and sneezing choose from multiple bundled variants, create visible respiratory particles, and emit a gameplay event that the Warden can hear. Medical Masks and full HazCure muffle those sounds. Paranoia uses intermittent voices; mutation effects may declare particles and sounds with intervals/chances.

Machines use appropriate feedback: UI button variants, gene completion, chamber completion, disinfection, liquid pour, chemical production, and centrifuge operation. Sounds should confirm state without being the only way to understand it; GUI progress and particles remain available.

Addon mutation effects can use registered play-sound/spawn-particle behavior, including a game-event ID when other mobs should react.
