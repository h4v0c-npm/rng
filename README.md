# @h4v0c/rng
A random number generator based on https://github.com/bryc/code/blob/master/jshash/PRNGs.md#mulberry32

## Install:
`npm install @h4v0c/rng`

## Usage:
1. Instantiate the `RandomNumberGenerator` class:
    ```javascript
    import { RandomNumberGenerator } from "@h4v0c/rng";

    const rng = new RandomNumberGenerator();

    // Set the rng seed:
    rng.seed(42);

    // Get the current seed:
    let seed = rng.seed();
    console.log(seed);

    // Get a random float:
    console.log(rng.randomFloat());

    // Get a random integer:
    console.log(rng.randomInt());

    // Get a random integer in range 0 to 100 (min: inclusive, max: exclusive):
    console.log(rng.randomRange(0, 100));

    // Get a random element/character from an array/string:
    console.log(rng.choose([ 1, 2, 3, 4 ]));
    console.log(rng.choose("ABCD"));

    // Shuffle an array or string:
    rng.shuffle([ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]);
    rng.shuffle("123456789");

    // Get a random 2D point in a circle by it's radius:
    let point = rng.randomPointInCircle(1.0);
    ```
2. Use the same methods from the instanced scope:

    One of the great benefits of using the instanced scope is that when they are required/imported in other source files, the seed remains intact.

    ```javascript
    import { seed, randomFloat, randomInt, randomRange, choose, shuffle, randomPointInCircle } from "@h4v0c/rng";

    // Set the rng seed:
    seed(42);

    // Get the current seed:
    console.log(seed());

    // Get a random float:
    console.log(randomFloat());

    // Get a random integer:
    console.log(randomInt());

    // Get a random integer in range 0 to 100 (min: inclusive, max: exclusive):
    console.log(randomRange(0, 100));

    // Get a random element/character from an array/string:
    console.log(choose([ 1, 2, 3, 4 ]));
    console.log(choose("ABCD"));

    // Shuffle an array or string:
    shuffle([ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]);
    shuffle("123456789");

    // Get a random 2D point in a circle by it's radius:
    let point = randomPointInCircle(1.0);
    ```