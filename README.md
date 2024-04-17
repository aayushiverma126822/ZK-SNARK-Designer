# ZK-SNARK-Designer

Welcome to the  project's repository! This readme guides you through the steps to correctly implement and verify a circuit using Circuit.Circom, generate a proof, and deploy a Solidity verifier to the Sepolia or Mumbai Testnet.

## Circuit Implementation

1. Begin by writing a correct implementation of the circuit in `circuit.circom`. Ensure the circuit accurately represents the logic you intend to verify.

## Compiling the Circuit

2. Compile the circuit using the Circom compiler to generate circuit intermediaries. Execute the following command in your terminal:

```shell
circom circuit.circom -o circuit
```

This command compiles `circuit.circom` and stores the intermediaries in the `circuit` directory.

## Generating a Proof

3. Generate a proof using inputs A=0 and B=1. You can achieve this by running the following command:

```shell
snarkjs groth16 prove circuit/proving.key input.json witness.wtns proof.json public.json
```

Ensure `input.json` contains the input values for A and B.

## Deploying the Solidity Verifier

4. Deploy a Solidity verifier contract to the Sepolia or Mumbai Testnet. Modify the verifier contract according to your specific circuit and verification requirements.

## Calling the VerifyProof() Method

5. After deploying the verifier contract, call the `verifyProof()` method on the deployed contract, providing the proof generated in step 3. Assert that the output is `true` to confirm the validity of the proof.

That's it! You've successfully implemented, verified, and deployed a circuit using FxPortal. For further details and troubleshooting, refer to the respective documentation and resources. Happy verifying!

- - -
