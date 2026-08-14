# Infectivity, Strength, and Cure Resistance

#BioForge #BioForge_V0_54T #Mechanic #Balance #Infection #Vaccine #ModpackGuide

These three values affect different parts of the infection loop.

## Infectivity

Infectivity belongs to lifecycle behavior and scales how readily exposure establishes a strain. Transmission route, environmental concentration, PPE, immunity, and server balance still matter.

## Infection strength

`infection_strength` is an editable clinical parameter with a range up to 10000. It represents the host burden used by treatment, symptom, and mutation calculations; it is not the same as airborne speed or route count.

## Cure resistance

Cure resistance is a lifecycle/treatment value that lowers the success of matching treatment. Mutation tags such as vaccine defense or protective coating can add further resistance and special host requirements.

## Vaccine result

A correct CRISPR sequence and correction matrix improve quality, but final treatment still combines quality with exact-strain match, host blood/Rh fit, strength, cure resistance, and defensive mutations. This is why a high-quality vaccine is rewarding without being an unconditional admin cure.

Related: [[Vaccine Quality]], [[Vaccinated Blood Assay]], [[Adaptive Vaccine Defense]].

