# ZKP-Zero Knowledge Proof <br />
## zkp3 is the right one and it is modified from the following link <br />
https://codethechange.stanford.edu/guides/guide_zk.html<br />
## For the installation of library look following<br />
https://itslinuxfoss.com/module-not-found-error-no-module-named-crypto-python/<br />


## Steps:
### Here are the steps for proving a ZKP using the Schnorr protocol:

1. Choose a prime number p and a generator g of a cyclic group of order p. Choose a random value x as the secret you want to prove knowledge of.<br />

2. Generate a random value r and calculate y = g^r mod p.<br />

3. Receive a challenge value c from the verifier.<br />

4. Calculate z = (r + c*x) mod (p-1).<br />

5. Send y and z to the verifier.<br />

6. Wait for the verifier's response.<br />

7. If the verifier accepts the proof, the prover is considered to have successfully proved knowledge of the secret x without revealing it. If the verifier rejects the proof, the prover has failed to prove knowledge of x and must start over with a new r.<br />

The verifier's response involves checking that g^z * y^-c mod p = g. If this equation holds, the verifier accepts the proof as valid. If the equation does not hold, the verifier rejects the proof.<br />

Note that the ZKP protocol can be repeated multiple times to increase confidence in the validity of the proof. Additionally, the Schnorr protocol is just one example of a ZKP protocol, and there are many others with different security properties and computational requirements.<br />


### There are several reasons why the proof might not be verified:

1.The values p, g, x, y, and z were not calculated correctly. It's important to ensure that these values are calculated using the same parameters and formulas as the verifier.

2. The challenge value c was not chosen randomly and uniformly by the verifier. The verifier must choose a new random value of c for each proof, and it must be chosen uniformly at random from a large enough range.

3. There is a bug in the implementation of the equation g^z * y^-c mod p = g. It's important to make sure that this equation is implemented correctly, taking into account the order of operations and the rules of modular arithmetic.

4. There is an error in the implementation of the hash function. It's important to use a hash function that is cryptographically secure and produces a uniform output for different inputs.

5. If the proof is not verified, it's important to check each step of the protocol carefully and look for any errors or discrepancies. It may also be helpful to compare the implementation to a reference implementation or to consult with a cryptography expert.
