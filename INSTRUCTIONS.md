# dice-computer INSTRUCTIONS

Format is `II - NN` where `II` is the opcode, and `NN` is the operand.

## Instructions

| `II` | `NN` | Abbr | Description |
| -- | - | - | - |
| 11 | NN | `NN -> PC` | Jump to NN |
| 12 | NN | `PC+NN -> PC` | Add NN to PC |
| 13 | NN | `PC-NN -> PC` | Sub NN from PC |
| 15 |    | `NOOP` | Do nothing |
| 16 | NN | `HALT` | NN=11: and catch fire |
| 21 |    | `RND A` | Roll AA (both dice). Random. |
| 22 | NN | `[NN+XX] -> AA` | Copy memory NN+XX into AA |
| 23 | NN | `AA,XX -> [NN]` | Copy "AA-XX" into memory `NN` |
| 24 | NN | `AA -> [NN+XX]` | Copy AA into memory NN+XX |
| 25 | NN | `NN -> XX` | Copy NN into XX |
| 26 | NN | `NN -> AA` | Copy NN into AA |
| 31 | PP | `AA -> (PP)` | Copy AA to output port PP (see [Ports](#ports)) |
| 32 | PP | `AA -> (PP)` | Copy AA from input port PP (see [Ports](#ports)) |
| 41 |  | `AA -> XX` | Copy AA into XX |
| 42 |  | `XX -> AA` | Copy XX into AA |
| 43 | NN | `[NN] -> AA` | Copy memory `NN` into AA |
| 51 |  | `AA = XX` | Skip (+2) unless AA = XX |
| 52 |  | `AA < XX` | Skip (+2) unless AA < XX |
| 53 | NN | `XX = NN` | Skip (+2) unless XX == NN |
| 54 | NN | `XX < NN` | Skip (+2) unless XX < NN |
| 56 | NN | `AA = NN` | Skip (+2) unless AA = NN |
| 61 |  | `XX+1 -> XX` | Add 1 to XX |
| 62 |  | `XX+AA -> AA` | Add XX to AA |

## Ports

See also [PAD-11](./PAD-11.md) for text encoding.

### Output

| Port | Meaning |
| ---- | ------- |
| 31 11 | Write letter on a pad of paper. |

### Input

| Port | Meaning |
| ---- | ------- |
| 31 11 | Read letter from a pad of paper, or ask user for a letter. |

## Math

What does `1-1 + 1-1` equal? `1-1`! Here's a table for adding or subtracting.

In other words, Adding `1-1` would add zero, adding `1-2` would add 1, etc.

TODO: Overflow!

| NN | ±  |
| -- | -- | 
| 11 | 0  |
| 12 | 1  |
| 13 | 2  |
| 14 | 3  |
| 15 | 4  |
| 16 | 5  |
| 21 | 6  |
| …… | …  |
| 66 | 35 |

## Author

Steven R. Loomis (@srl295) of [Code Hive Tx, LLC](https://codehivetx.us)

## License

All text is © 2022 Code Hive Tx LLC and licensed under [CC-BY-SA-4.0](http://creativecommons.org/licenses/by-sa/4.0/) which is also in [LICENSE](./LICENSE)

> This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. To view a copy of this license, visit <http://creativecommons.org/licenses/by-sa/4.0/> or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

SPDX-License-Identifier: CC-BY-SA-4.0
