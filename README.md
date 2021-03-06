[![Build Status](https://travis-ci.org/timmyjose/hangman.svg?branch=master)](https://travis-ci.org/timmyjose/hangman)

A simple hangman game in Rust.

The game will try and detect if the OS is a Unix-like OS and try to see if `/usr/share/dict/words` can be used. If not, the bundled file, `words.txt` will be used instead.
The game will automatically load the entire file in memory, and randomly pick the words fulfilling the minimum and maximum word length constraints. If you so desire, you can replace the `words.txt` file with your own `words.txt` file (note that the name must be the same).

## Usage
```
$ ./hangman [max-word-length = 24] [number-of-attempts = 10] (on UNIX-like systems)
```
or

```
$ hangman.exe [max-word-length = 24] [number-of-attempts = 10] (on Windows)
```

The minimum word length is set at 5 (not changeable). The minimum number of attempts is set at 10 (can be changed), and the maximum at 100 (not changeable).


## Build instructions

Download the zip file or clone the project. Then from the command-line, change into the project's root directory.


```
$ cd hangman
$ cargo build
$ cargo run [max-word-length = 24] [number-of-attempts = 10]
```

Alternatively, the executable located in target/debug/ can be used in the manner shown in the `Usage` section.

## Sample gameplay

```
Macushla:hangman z0ltan$ cargo run 5 20
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hangman 5 20`

Welcome to hangman! You have 20 attempts!
_ _ _ _ _

Enter your guess: a
_ _ _ _ _

Enter your guess: e
_ _ _ _ _

Enter your guess: i
_ _ _ _ _

Enter your guess: o
_ o _ _ _

Enter your guess: u
_ o u _ _

Enter your guess: f
_ o u _ _

Enter your guess: t
_ o u _ _

Enter your guess: b
_ o u _ _

Enter your guess: n
_ o u _ _

Enter your guess: l
l o u _ _

Enter your guess: d
l o u _ _

Enter your guess: p
l o u p _

Enter your guess: e
l o u p _

Enter your guess: y
l o u p _

Enter your guess: s

You win! You took 15 attempts to crack the word "loups"!

Do you want to continue? [y/n]: n

Thank you for playing Hangman!
```


