# Dice Computer Bugs

… and areas for improvement

## General

- The architecture is not rigorous about the absence or presence of data in memory cells. It should probably be defined somewhere, such as that  an empty cell is equal to a, say, `15` which is a noop. Or add an instruction `66` and use that.
- No handling of overflow or underflow numerical conditions
- No stack

## Author

Steven R. Loomis (@srl295) of [Code Hive Tx, LLC](https://codehivetx.us)

## License

All text is © 2022 Code Hive Tx LLC and licensed under [CC-BY-SA-4.0](http://creativecommons.org/licenses/by-sa/4.0/) which is also in [LICENSE](./LICENSE)

> This work is licensed under the Creative Commons Attribution-ShareAlike 4.0 International License. To view a copy of this license, visit <http://creativecommons.org/licenses/by-sa/4.0/> or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

SPDX-License-Identifier: CC-BY-SA-4.0
