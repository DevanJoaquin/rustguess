# rustguess 

`rustguess` Linux kernel module that runs a number guessing game at /dev/rustguess

Users write guesses into the device, and reading from the device returns hints such as "too high," "too low," or "correct." After the correct guess, the module remembers that the player has won and tells them to reload the module to play again.

The secret number is currently hardcoded as `42`.

## Build

```bash
make clean
make RUSTC=/usr/bin/rustc

### Future Work


A random secret, using kernel RNG (kernel::random::getrandom) to pick a fresh secret at module load.
