# Multiply-With-Carry Random Number Generator

This library implements the [complementary multiply-with-carry algorithm](https://en.wikipedia.org/wiki/Multiply-with-carry) created by [George Marsaglia](https://en.wikipedia.org/wiki/George_Marsaglia) as a LuaRock.

It is designed for use in games. It is meant to be deterministic: given a certain intial seed, the sequence of results provided by the library should be the same.

## mwcrng.init(seed)

Initializes the library, and must be called before any other function. The argument must be an integer. The result of `os.time()` is a good choice of seed if you don't have a particular one you wish to use.

## mwcrng.coin()

Simulates a coin toss. Has a 50% chance of returning true, and a 50% chance of returning false.

## mwcrng.dice(throws, sides)

Simulates throws `throws` dice, each with an equal chance of providing any result from 1 to `sides` inclusive. The result is the sum of all the values of all the simulated dice.

For example, `dice(1,6)` would return any value from 1 to 6 inclusive with equal probability.

`dice(2,4)` would return any value from 2 to 8 inclusive, but not with equal probability: values of exactly 2 and 8 would be unlikely.
