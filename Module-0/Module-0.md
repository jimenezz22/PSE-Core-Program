# Modulo 0

https://github.com/privacy-scaling-explorations/core-program/blob/main/2024/week0_course_primer.md

## What is ZK

Zero-knowledge proof protocols. In cryptography, a zero-knowledge proof (ZKP) allows one party (the prover) to demonstrate to another party (the verifier) that a statement is true without revealing any additional information beyond the veracity of the statement itself.

## Principles of ZKPs

For a proof to be considered zero-knowledge, it must satisfy the following properties:

1. **Completeness**: If the statement is true, the prover can convince the verifier that it is true.
2. **Soundness**: If the statement is false, no dishonest prover can convince the verifier that it is true, except with a very low probability.
3. **Zero-Knowledge**: If the statement is true, the verifier learns nothing beyond the veracity of the statement. They obtain no additional information about the underlying secret or data.


## Types of ZKPs

1. **Interactive Proofs**: These require interaction between the prover and the verifier. A classic example is the Feige-Fiat-Shamir protocol.
2. **Non-Interactive Proofs (NIZK)**: These do not require interaction and are typically used in scenarios where interaction is impractical. An important example is the zk-SNARK (Succinct Non-interactive Argument of Knowledge) scheme.

    ### Feige-Fiat-Shamir
    
    The Feige-Fiat-Shamir protocol is indeed a type of zero-knowledge proof. It adheres to the same basic principles of zero-knowledge proofs, where the prover can prove the truth of a statement (in this case, their identity or knowledge of a secret) without revealing any additional information about the secret itself. Therefore, it can be considered a traditional zero-knowledge proof.
    
    ### ZK-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge)
    
    zk-SNARKs are crucial for improving the privacy and scalability of transactions.
    
    zk-SNARKs are a specific type of zero-knowledge proof that is succinct and non-interactive. This means the proof can be verified quickly and does not require multiple interactions between the prover and the verifier.
    
    **In Ethereum:** With the introduction of zk-rollups, multiple transactions can be grouped into a single zk-SNARK proof, improving scalability and maintaining privacy.
    
    ### STARKs **S**calable, **T**ransparent **AR**gument of **K**nowledge → Starknet
    
    STARKs are a cryptographic technology developed by STARKWARE and implemented in Starknet. They are used to create zero-knowledge proofs that are scalable and transparent, allowing for efficient and secure proof and verification of computations.
    
    ### How do STARKs work?
    
    1. **Offchain Calculations**: Large amounts of computations are performed off the main Ethereum chain, which is cheaper.
    2. **Proof Generation**: A proof is generated that validates these computations are correct.
    3. **Onchain Verification**: Only the verification of this proof, which is much faster and cheaper, is performed on the main chain.
    
    ### Key Features of STARKs:
    
    1. **Scalability**: STARKs are designed to be highly scalable, allowing for efficient processing of large volumes of data and transactions.
    2. **Transparency**: Unlike other zero-knowledge proof methods, such as zk-SNARKs, STARKs do not require a trusted setup. This enhances transparency and security, as there is no dependency on an initial setup that could be vulnerable.
    
    ### Benefits for Blockchain
    
    - **Greater Scalability**: They enable processing many more transactions per second (TPS).
    - **Reduced Costs**: Performing calculations offchain and only verifying onchain significantly reduces fees.
    - **Ethereum Security**: Transactions maintain Ethereum's security.
    
    ### Why transactions are cheaper using STARKs:
    
    ### 1. **Transaction Batching**
    
    In StarkNet, multiple transactions are grouped into a single zero-knowledge proof (in this case, a STARK proof). This proof is verified on the main Ethereum chain, meaning that instead of paying for each transaction individually, a combined fee is paid for verifying the proof that batches many transactions. This significantly reduces the cost per transaction.
    
    ### 2. **Data Compression**
    
    STARK proofs allow for efficient data compression. The amount of data that needs to be stored and processed on the main Ethereum chain is much smaller, as only the proof is included instead of all individual transactions. Less data means lower costs.
    
    ### 3. **Computational Optimization**
    
    Intensive computational operations are performed off the main chain, on the layer two (StarkNet). Only the final result (the STARK proof) is sent to the main chain. This alleviates the workload of the main Ethereum network and reduces gas fees associated with smart contract execution and transaction processing.
    
    ### 4. **Main Network Decongestion**
    
    By moving a large volume of transactions to layer two, congestion on the main Ethereum network decreases. Less congestion means that gas fees can drop, as the demand for block space on the main chain is reduced.
    
    ### 5. **Scale Efficiency**
    
    StarkNet can handle thousands of transactions per second due to the scalable nature of STARK proofs. Having a higher capacity to process transactions distributes the costs more efficiently among users.
    
    ### Summary
    
    Moving transactions to StarkNet significantly reduces gas fees because:
    
    - Multiple transactions are batched into a single proof.
    - Data is compressed.
    - Intensive operations are performed offchain.
    - The main Ethereum network is decongested.
    - Higher processing capacity reduces costs per transaction.