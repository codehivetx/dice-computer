# Dice Computer Overview

This is a game/vm/teaching tool whereby one or more people pretend to be a simple computer.

## requirements

- papers and pencils
- as many dice as possible

## jobs

One person can play this game, or for more enjoyment, the tasks can be split up between several people.

- programmer (filling out initial memory. starting/stopping the computer.)
- 'the pad' (output)
- registers (tracking the PC, AA, XX)
- memory (responding to fetch requests)
- instruction decode (looking up the instructions, calling out orders)
- clock (keeping everyone moving and data flowing)

## basics

- Each digit is a die. So 12 34 is four dice: 1, 2, 3, 4
- Memory has a 'word' of four dice, consisting of a Two digit opcode.  0-2 digit operand. Memory can be as big as you like up to address `66`.
- Registers (all 2-die)
  - AA General purpose accumulator
  - XX General purpose index
  - PC Program Counter. Starts at 11 on cold boot.

## registers

Make a piece of paper that has three entries:  AA, XX, and PC.

Place two dice each on each entry.

PC should start as `11`. After each instruction is completed, increment PC by one, unless PC was otherwise changed. (Note that `16` is followed by `21`, etc.)

## memory

Memory can be a pad of paper with a program, or ideally it would be a pad of paper with dice placed on it to represent memory values.  (Note that `16` is followed by `21`, etc.)

For example:

      ##: I I  N N
      11: _ _  _ _
      12: _ _  _ _
      13: _ _  _ _
      …
      66: _ _  _ _

## example

- Suppose the memory was initialized as follows:

      11: 26 35
      12: 31 11
      13: 16

- At first: PC=11, AA=??, XX=?? (questionmarks = does not matter)
- Since the program counter is `11`, fetch `26 35` from memory.
    Use four dice to make `2-6 3-5`
- `26` means move NN (that's `35`) into AA. So, change AA to `35`
- Increment the PC from `11` to `12`
- Now fetch `31 11`.
  - `31` means to write AA to port `11`, the 'pad of paper'
  - Look up the value of AA, `35` in [PAD-11](./PAD-11.md). It is `Q`.
  - Write a `Q` in the next spot on the output pad.
- Increment the PC to `13`
- Now fetch `16`
  - `16` means to halt, or stop. The game is over.

## License

All text is © 2022 Code Hive Tx LLC and licensed under CC-BY-SA-4.0

SPDX-License-Identifier: CC-BY-SA-4.0
