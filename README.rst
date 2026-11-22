====================================
dbk re-implementation of ``V6`` Unix
====================================

Dependencies
============

.. code:: bash

        $ brew trust riscv-software-src/riscv
        $ brew tap riscv-software-src/riscv
        $ brew install riscv-tools
        $ brew test riscv-tools
        $ brew install riscv64-elf-gdb
        $ brew install qemu

Pinning
-------

Pin the above packages

.. code:: bash

        $ brew pin qemu riscv-gnu-toolchain riscv-isa-sim riscv-pk riscv-tools riscv64-elf-gdb

.. code:: bash

        $ brew info --installed --json | jq ' .[] | select(.pinned) | .installed.[].time |= todateiso8601 |"\(.full_name), \(.installed.[].time ), \(.installed.[].version)"'
        "qemu, 2026-11-22T03:40:32Z, 11.1.3"
        "riscv-software-src/riscv/riscv-gnu-toolchain, 2026-11-22T17:17:16Z, main"
        "riscv-software-src/riscv/riscv-isa-sim, 2026-11-22T17:17:20Z, main"
        "riscv-software-src/riscv/riscv-pk, 2026-11-22T17:17:23Z, main"
        "riscv-software-src/riscv/riscv-tools, 2026-11-22T17:17:25Z, 0.2"
        "riscv64-elf-gdb, 2026-11-22T17:18:29Z, 18.1"

.. code:: bash

        [deebakkarthi@macbook]src/v6/opt % qemu-system-riscv64 --version                                     main
        QEMU emulator version 11.1.3
        Copyright (c) 2003-2026 Fabrice Bellard and the QEMU Project developers

        [deebakkarthi@macbook].local/src/v6 % riscv64-unknown-elf-gcc --version                              main
        riscv64-unknown-elf-gcc (g6afcc4f6d) 16.1.0
        Copyright (C) 2026 Free Software Foundation, Inc.
        This is free software; see the source for copying conditions.  There is NO
        warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

