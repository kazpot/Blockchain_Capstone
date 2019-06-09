# Real Estate Token
Mint non-fungible tokens to represent the real estate properties and use zk-SNARKs to create a verification system which can prove the title to the property without revealing that specific information on the property. After verification, the tokens will be placed into the blockchain market place named OpenSea. 

# Version

`Truffle v5.0.8 (core: 5.0.8)`

`Solidity - ^0.4.24 (solc-js)`

`Node v11.8.0`

`Web3.js v1.0.0-beta.37`

# Install
`npm install`

# Implement Zokrates

### Step 1: Run ZoKrates
`docker run -v <path to your project folder>:/home/zokrates/code -ti zokrates/zokrates /bin/bash`

### Step 2: Create <program name>.code using Zokrates DSL
Create simple square.code 

### Step 3: Compile the program written in ZoKrates DSL
`cd ~/zokrates/code/square`

`~/zokrates compile -i square.code`

```
def main(private field a, field b) -> (field):
  field result = if a * a == b then 1 else 0 fi
  return result

```

### Step 4: Generate the Trusted Setup

`~/zokrates setup`

### Step 5: Compute Witness
Pass answer to square.code as arguments (3^2 == 9) and it generates a witness file

`~/zokrates compute-witness -a 3 9`


### Step 6: Generate Proof
Generate proof based on the above witness. A proof.json file is generated in this step

`~/zokrates generate-proof`


### Step 7: Export Verifier
Create smart contract named verifier.sol

`~/zokrates export-verifier`

### Helpful Document
[How to prove knowledge using Zokrates](https://zokrates.github.io/sha256example.html)

# Compile contracts

`cd eth-contract`

`truffle compile`

# Test

`ganache-cli -m "candy maple cake sugar pudding cream honey rich smooth crumble sweet treat"`

`cd eth-contract`

`truffle test`


# Project Resources

* [Remix - Solidity IDE](https://remix.ethereum.org/)
* [Visual Studio Code](https://code.visualstudio.com/)
* [Truffle Framework](https://truffleframework.com/)
* [Ganache - One Click Blockchain](https://truffleframework.com/ganache)
* [Open Zeppelin ](https://openzeppelin.org/)
* [Interactive zero knowledge 3-colorability demonstration](http://web.mit.edu/~ezyang/Public/graph/svg.html)
* [Docker](https://docs.docker.com/install/)
* [ZoKrates](https://github.com/Zokrates/ZoKrates)
