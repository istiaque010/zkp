# ZKP-Zero Knowledge Proof <br />
## zkp3 is the right one and it is modified from the following link <br />
https://codethechange.stanford.edu/guides/guide_zk.html<br />
## For the installation of library look following<br />
https://itslinuxfoss.com/module-not-found-error-no-module-named-crypto-python/<br />


## Steps:
## Look at these steps too from chatGPT
Here is a step-by-step guide to implementing a simple ZKP protocol:<br/>

1. Choose a problem to prove: In this example, we will use the Discrete Logarithm Problem (DLP). This is a mathematical problem that is difficult to solve, but easy to verify. Specifically, given a prime number p, a generator g of the group Zp* and an element y in Zp*, the goal is to find an integer x such that g^x mod p = y. This problem is believed to be hard to solve, but given x, it is easy to verify that g^x mod p = y.<br/>

2. Set up the protocol: In this example, we will use the Schnorr protocol. This is a simple protocol that allows you to prove knowledge of a DLP solution. The protocol involves three steps: commitment, challenge, and response.

3. Commitment: The prover chooses a random value r and computes c = g^r mod p. This value c is called the commitment and is sent to the verifier.<br/>

4. Challenge: The verifier chooses a random value e and sends it to the prover.<br/>

5. Response: The prover computes s = r + ex mod (p-1), where x is the solution to the DLP, and sends it to the verifier.<br/>

6. Verification: The verifier checks that g^s mod p = y^c * c^e mod p. If this equation holds, then the prover has successfully proven knowledge of the DLP solution without revealing the value of x.
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

## More resource <br/>
Implement ZKP with ZoKrates <br/>
https://www.youtube.com/watch?v=_ZvGZxhCFfE <br/>
https://medium.com/coinmonks/zokrates-zksnarks-on-ethereum-made-easy-8022300f8ba6 <br/>
https://zokrates.github.io/print.html
