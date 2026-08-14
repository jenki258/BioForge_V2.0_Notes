# Research Tablet API

#BioForge #BioForge_V0_54T #JavaAPI #JSONAPI #ResearchTablet #AddonDevelopment

A Research Tablet page defines ID, title/body content, ordering/category, unlock triggers, icons, and structured recipe references. JSON pages load from `research_journal`; Java addons register page definitions/views before registry finalization.

Recipe views can represent crafting and BioForge machine operations with station labels, slot-like icons, counts, and alternatives. Unlocks are server-side per-player progress and should be granted by stable item/page IDs.

Custom rendering must preserve scrolling, text wrapping, accessibility, and locked-page behavior. See [[BioForge addon creation guide]] for copy-ready registration examples.
