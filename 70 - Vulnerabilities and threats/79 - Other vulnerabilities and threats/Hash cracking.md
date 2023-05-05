Even if passwords are stolen, they may still be [[Hashing|hashed]]. This creates a new problem for attackers, who need to find a way to break the hashes.

# Birthday attack
A type of attack that exploits hash collisions in weaker hashing and digital signature algorithms, allowing increased cracking speed.

# Rainbow table
If you have a large number of password hashes, you can attack them all at once using a precomputed table of possible hash values along with the passwords behind them. This may take time, but it is relatively effective.

# Pass the hash
Sometimes attackers may not need to crack hashes. In some systems, it's possible to compromise one system and steal its stored hashes, then use those stolen hashes to access resources on another computer on the network using the stolen credentials.