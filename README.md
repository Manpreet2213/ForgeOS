# OS Forge

Learn x86 assembly from zero by building your own operating system, **ForgeOS**, one mission at a time.

Each mission has two steps:

1. **Learn**: simple lesson cards with pictures, everyday examples and quick quizzes.
2. **Build**: write real NASM assembly and boot it on a simulated PC in your browser, with a Step button to watch the registers change.

## Phase 1: Boot sector (playable now)

1. Power On: a 512-byte boot sector with the 55 AA signature
2. First Words: print with BIOS `int 0x10`
3. Counting: `inc`, `cmp`, `jne` loops
4. Strings in Memory: `db`, `SI`, `lodsb`
5. Functions: the stack, `call`, `ret`
6. Listen: keyboard input with `int 0x16`
7. The Prompt: Enter and Backspace
8. Your First Shell: a command shell inside 512 bytes

Phases 2 to 5 (disk loading, 32-bit protected mode, a C kernel, interrupts, paging, multitasking, a filesystem) are planned.

## Run it

Open `index.html` in any browser. No install needed.

## Run your code on a real PC emulator

```
nasm -f bin forge.asm -o forge.bin
qemu-system-x86_64 -drive format=raw,file=forge.bin
```

The browser simulator supports a subset of about 30 16-bit instructions. Byte sizes it reports are close estimates.
