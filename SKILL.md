---
name: catan-board-generator
description: Generates a custom Settlers of Catan board layout. Use when the user asks to "generate a catan board", "make a board that is wood heavy", "build a road-building map", etc.
---

# Generate Catan Board

## Instructions

Call the `run_js` tool with the following exact parameters:

- script name: index.html
- data: (REQUIRED) A JSON string with the following fields representing the user's requested modifiers. You MUST always provide this parameter, even if all flags are false:
  - board_name: String (Generate a wacky, fun, PG-13 name for the board here, e.g. "The Great Sheep Empire" or "Oretropolis")
  - road_heavy: Boolean (Set to true if they want lots of wood/brick or road building)
  - dev_card_farm: Boolean (Set to true if they want to buy development cards, favors wheat/ore/sheep)
  - stone_heavy: Boolean (Set to true if they want a city-building or ore-heavy game)
  - wheat_favored: Boolean
  - wood_favored: Boolean
  - brick_favored: Boolean
  - sheep_favored: Boolean

**CRITICAL INSTRUCTION:**
If the user simply asks to "generate a catan board for me" (or similar) without specifying any particular resource preferences, you MUST set ALL of the above boolean parameters to `false`. This will generate a completely randomized standard Catan board.
