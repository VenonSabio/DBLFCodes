This is where we add/edit Dragon Ball: Legendary Forces codes.

They're located in `codes.json`.

Changes made to `codes.json` are automatically loaded by active game servers within 60 seconds. Every code can only be redeemed once per player.

## Code format

```json
{
  "codes": {
    "CODE_NAME": {
      "enabled": true,
      "rewards": {
        "zeni": 100000,
        "x2Zeni": 1800, -- Seconds
        "x2Xp": 1800, -- Seconds
        "raceReroll": 1,
        "traitReroll": 1
      }
    },
  }
}
