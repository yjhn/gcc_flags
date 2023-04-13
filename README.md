## GCC flags

All GCC flags: https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html

Note: -Wpedantic is not included, because it always checks ISO C compatibility,
even if -std=gnuXX is given (for example, it warns about stuff that is in POSIX
but not in ISO C)

`-Os` = `-O2` + size optimizations
`-D_FORTIFY_SOURCE` enables some bounds checking
`-ftrapv` kills the program on overflow, but is really slow
`-fwrapv` make overflow always wrap (no UB)

`_FORTIFY_SOURCE=3` is available since glibc 2.35 and GCC 12 or LLVM 9

### Flags

```
-D_FORTIFY_SOURCE=3 -fstack-protector-strong \
-std=gnu11 -Wall -Wextra -Wconversion -Wmissing-prototypes \
-Wstrict-prototypes -Wunused-parameter -Wuninitialized -Wshadow \
-Wbad-function-cast -Wcast-qual -Wdouble-promotion -Wformat=2 \
-Wformat-overflow=2 -Wformat-signedness -Wformat-truncation=2 \
-Wnull-dereference -Winit-self -Wmissing-include-dirs -Wswitch-default \
-Wstrict-overflow=4 -Warith-conversion -Wduplicated-branches -Wduplicated-cond \
-Wlogical-op -Wold-style-definition -Winvalid-utf8 -Wvla -Wwrite-strings \
-Wunused-macros -Wundef -Wpointer-arith -Wfloat-equal -Walloc-zero -Wunused \
-Werror -Wno-error=unused -Wno-error=unused-macros -Wno-error=float-equal \
-Wno-error=unused-but-set-variable \
-funsigned-char -fwrapv \
-finput-charset=UTF-8 \
-Os
```
