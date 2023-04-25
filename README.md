# zkp3 is the right one and it is modified from the following link
https://codethechange.stanford.edu/guides/guide_zk.html
#For the installation of library look following
https://itslinuxfoss.com/module-not-found-error-no-module-named-crypto-python/


#Steps:
There are several reasons why the proof might not be verified:

1.The values p, g, x, y, and z were not calculated correctly. It's important to ensure that these values are calculated using the same parameters and formulas as the verifier.

2. The challenge value c was not chosen randomly and uniformly by the verifier. The verifier must choose a new random value of c for each proof, and it must be chosen uniformly at random from a large enough range.

3. There is a bug in the implementation of the equation g^z * y^-c mod p = g. It's important to make sure that this equation is implemented correctly, taking into account the order of operations and the rules of modular arithmetic.

4. There is an error in the implementation of the hash function. It's important to use a hash function that is cryptographically secure and produces a uniform output for different inputs.

5. If the proof is not verified, it's important to check each step of the protocol carefully and look for any errors or discrepancies. It may also be helpful to compare the implementation to a reference implementation or to consult with a cryptography expert.
