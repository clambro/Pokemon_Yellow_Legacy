# Bug fixes

Fixes in this fork relative to [Pokémon Yellow Legacy](https://github.com/cRz-Shadows/Pokemon_Yellow_Legacy) at base commit `15169d1`:

1. **Pikachu's badge boosts:** Correct the reversed condition so Pikachu receives the intended 25% stat boost and other species receive 12.5%.
2. **Trainer AI type effectiveness:** Initialize neutral effectiveness correctly instead of treating neutral attacks as super effective.
3. **Trainer AI resisted attacks:** Restrict the alternative-move search to the Pokémon's four move slots, preventing unrelated memory from making the AI reject resisted attacks when it has no better damaging move.
4. **Trainer AI Mirror Move:** Consult the actual move history when deciding whether Mirror Move has a move to copy.
5. **Trainer AI predicting player actions:** Use the outgoing Pokémon's types, status, and speed when evaluating a voluntary switch, including speed checks for moves such as Fissure. Likewise, use the pre-cure status when evaluating Dream Eater. This prevents the AI from reacting to switches or cures before they happen; per-action flags are also reset to prevent stale decisions.
6. **Hard-mode level caps:** Prevent above-cap Pokémon from losing experience or levels in battle or Day Care, triggering spurious move-learning prompts, or producing incorrect Day Care fees. Rare Candy is also rejected at or above the cap.
7. **Hard-mode obedience:** Preserve the badge count when choosing obedience thresholds instead of incorrectly selecting the same threshold for zero through seven badges.
8. **Capture calculations:** Correct ball-factor selection and restore HP-dependent capture chances while retaining the Ultra/Safari Ball advantage. Poké Balls use factor 12; Great, Ultra, and Safari Balls use factor 8.
9. **S.S. Anne money gift:** Initialize the complete ¥500 amount and terminate the dialogue script correctly, preventing stale memory from changing the reward or the script's continuation.
10. **Move relearner:** Exclude stale list metadata from duplicate checks so valid moves are not incorrectly omitted.
11. **Moveset corrections:** Put Golduck's Tail Whip in level order so generated movesets include the appropriate moves, and restore Light Screen to Sabrina's second team's Mr. Mime instead of a duplicate Substitute slot.
12. **Shortcut Cut animation:** Initialize the cut tile before entering the shared Cut routine so previous grass-cutting state cannot affect a tree-cutting animation.
13. **Experience distribution:** Stop EXP.ALL from dividing the party-wide half of experience and stat experience by the participant count twice. Exclude fainted Pokémon from awards and recipient counts, with or without EXP.ALL, while preserving rounding, bonuses, and level caps.
14. **Trainer AI dual-type effectiveness:** Combine both defensive types when scoring attacks, including canceling weaknesses/resistances and immunities. Single-type Pokemon are counted once. Preserve outgoing-target types on voluntary switches and Lorelei’s Dewgong exception.
