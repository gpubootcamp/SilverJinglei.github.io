# Reference
cross compiler:
https://baike.baidu.com/item/%E4%BA%A4%E5%8F%89%E7%BC%96%E8%AF%91/10916911
https://en.wikipedia.org/wiki/Cross_compiler

Toolchain:
https://baike.baidu.com/item/Toolchain/1318786

Establish Environment:
https://www.cnblogs.com/louyihang-loves-baiyan/p/4171368.html
https://www.cnblogs.com/lidabo/p/4499011.html


# Terminology
Native Compilation - compile and run in same cpu-os-host

Corss Compliation tool chain - compile and run in diff host (x86-linux => ARM)
- Windows PC, ADS (ARM IDE) + armcc (compiler) => ARM CPU exe
- Linux PC, arm-linux-gcc (compiler) => Linux ARM exe
- Windows PC, cygwin + arm-elf-gcc (compiler) => ARM CPU

host - compiler platform, always x86 PC
target - customer dev platform, always non-x86, host compiler => exe run in target
prefix - cross compiler installation location

CPU-Vendor-OS
arm-linux, i386-pc-linux2.4.3
sparc-sun-sunos4.1.4

Toolchain

Patch - cross compiler => stability => need patch

# Requirement
I need program in Embedded Board

> But:
The board hasn't enough memory and cpu => install IDE or compile to build

> So:
Only one choice: compile and build in another Host (always x86 linux) => gen exe file

# Implement
Ubuntu install ARM-gcc toolchain: https://www.cnblogs.com/muyun/p/3370996.html

## GDB - (GNU Debugger) symbolic debugger => cross compiler
https://www.cnblogs.com/lidabo/p/4499011.html


Company always establish a standalone shared [Build Server]

## GCC - GNU Compiler Collection
