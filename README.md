ddp-random
=====

[![Build Status](https://travis-ci.org/oortcloud/ddp-random.svg)](https://travis-ci.org/oortcloud/ddp-random)

Random number generator and utilities; used in [Meteor](http://meteor.com).


The random package provides several functions for generating random numbers. It uses a cryptographically strong pseudorandom number generator when possible, but falls back to a weaker random number generator when cryptographically strong randomness is not available (on older browsers or on servers that don't have enough entropy to seed the cryptographically strong generator).

###`Random.id([n])`
Returns a unique identifier, such as "Jjwjg6gouWLXhMGKW", that is likely to be unique in the whole world. The optional argument `n` specifies the length of the identifier in characters and defaults to 17.

###`Random.secret([n])`
Returns a random string of printable characters with 6 bits of entropy per character. The optional argument `n` specifies the length of the secret string and defaults to 43 characters, or 256 bits of entropy. Use `Random.secret` for security-critical secrets that are intended for machine, rather than human, consumption.

###`Random.fraction()`
Returns a number between 0 and 1, like Math.random.

###`Random.choice(arrayOrString)`
Returns a random element of the given array or string.

###`Random.hexString(n)`
Returns a random string of `n` hexadecimal digits.

###`Random.createWithSeeds(arrayOrString)`
Returns a random number generator. This value passed in is used to seed pseudo-random number generation. By using the same seed with the same algorithm, the same pseudo-random values can be generated on the client and the server. In particular, this is used for generating ids for newly created documents.