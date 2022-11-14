Hashing is one approach to providing integrity to data transmissions crossing a network. It involves taking a string of data such as a plaintext password and running it through an algorithm. The result of the algorithm is called a hash value or hash digest.

| Plaintext                        | Hash digest                      |
| -------------------------------- | -------------------------------- |
| hello world                      | 5eb63bbbe01eeed093cb22bb8f5acdc3 |
| 7                                | 8f14e45fceea167a5a36dedd4bea2543 |
| this is my note page for hashing | 5b51fb31c230eea61346c503ce7b0b6f                                 |

The above examples are all MD5 hashes. It is worth noticing that all of the hash digests are the same length, regardless of the length of the original input.

# What is it?
Hashing is the process of scrambling a piece of information or data beyond recognition, designed to be irreversible. The input is passed through a hash function to calculate the hash value or hash digest.

A hash function is basically algorithms that perform mathematical operations on the main plantext.

# How are they used?
When a user makes a new account, their password is passed through the hash function and the hash digest is stored on the server.

When a user logs into that website, the password they enter is hashed and then compared to the stored hash digest. If they are the same, the password is correct.