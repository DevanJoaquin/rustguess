# rustguess

`rustguess` is a Linux kernel module that runs a number guessing game at `/dev/rustguess`.

Users write guesses into the device, and reading from the device returns hints such as `"too high"`, `"too low"`, or `"correct"`. After the correct guess, the module remembers that the player has won.

The secret number is currently hardcoded as `42`.

## Build

```bash
make clean
make RUSTC=/usr/bin/rustc
```

## Run

```bash
sudo insmod rustguess.ko
sudo cat /dev/rustguess
```

## Future Work

Use a random secret by using the kernel RNG, such as `kernel::random::getrandom`, to pick a fresh secret at module load.

## Demo

[Watch the rustguess demo on asciinema](https://asciinema.org/a/hboPquKKZx7nLdF3)
