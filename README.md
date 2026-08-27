# Dragon Ball: Legendary Forces Codes

This repository manages Dragon Ball: Legendary Forces redeem codes.

All codes are stored in `codes.json`. After editing the file and committing the changes, active game servers automatically load the new version within 60 seconds.

Each code can only be redeemed once per player.

## Code format

```json
{
  "codes": {
    "CODE_NAME": {
      "enabled": true,
      "rewards": {
        "zeni": 100000,
        "x2Zeni": 1800,
        "x2Xp": 1800,
        "raceReroll": 1,
        "traitReroll": 1
      }
    }
  }
}
```

## Available attributes

| Attribute | Type | Description |
| --- | --- | --- |
| `CODE_NAME` | String | The code players must enter. Codes are not case-sensitive. |
| `enabled` | Boolean | `true` activates the code. `false` disables it without deleting it. |
| `zeni` | Number | Amount of Zeni granted. |
| `x2Zeni` | Number | Duration of the 2x Zeni boost, in seconds. |
| `x2Xp` | Number | Duration of the 2x XP boost, in seconds. |
| `raceReroll` | Number | Amount of Race Rerolls granted. |
| `traitReroll` | Number | Amount of Trait Rerolls granted. |

All reward attributes are optional. You may use one reward or combine multiple rewards in the same code.

## How to add a code

1. Open `codes.json`.
2. Click the pencil icon to edit the file.
3. Add the new code inside the `"codes"` object.
4. Click **Commit changes**.
5. Wait up to 60 seconds for active servers to load the update.

Example: adding a Zeni and 2x XP code:

```json
{
  "codes": {
    "WELCOME": {
      "enabled": true,
      "rewards": {
        "zeni": 100000,
        "x2Xp": 1800
      }
    }
  }
}
```

`x2Xp: 1800` means 30 minutes of 2x XP.

## How to add multiple codes

```json
{
  "codes": {
    "WELCOME": {
      "enabled": true,
      "rewards": {
        "zeni": 100000
      }
    },
    "REROLLS": {
      "enabled": true,
      "rewards": {
        "raceReroll": 2,
        "traitReroll": 2
      }
    }
  }
}
```

## Important: commas

JSON is strict about commas.

- Add a comma after an entry only when another entry comes after it.
- Never add a comma after the final entry in an object.
- JSON does not allow comments such as `-- Seconds` or `// Seconds`.

Correct:

```json
"rewards": {
  "zeni": 100000,
  "x2Xp": 1800
}
```

Incorrect:

```json
"rewards": {
  "zeni": 100000,
  "x2Xp": 1800,
}
```

The final entry, `x2Xp`, must not have a comma after it.

## Disabling a code

To temporarily disable a code without deleting it, change:

```json
"enabled": true
```

to:

```json
"enabled": false
```

Disabled codes cannot be redeemed. Players who already redeemed a code will not be able to redeem it again, even if its rewards are changed later.
