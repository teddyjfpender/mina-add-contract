# Mina zkApp: Mina Add Contract

This project demonstrates the basic usage of zkApps in Mina Protocol by implementing a simple smart contract named 'Add'. The 'Add' contract holds a state variable 'num', which is a field initialized to 1 by default when the contract is deployed. Upon calling the 'update' method, it adds 2 to the current 'num' state.

The project is written in TypeScript and uses the snarkyjs library.

### Architecture

The project mainly consists of two parts:

- The Add Contract (`Add.ts`)
- Interaction Script (`interact.ts`)

The 'Add' contract is a very basic smart contract example and the 'interact.ts' script is used to interact with the 'Add' contract by deploying and updating it.

Here is a basic diagram that outlines the interaction between the components:

```mermaid
sequenceDiagram
    participant Deployer
    participant zkApp
    participant Sender
    Deployer->>zkApp: compile and deploy contract
    Note over zkApp: num state is Field(1)
    Deployer->>zkApp: sign and send deployment transaction
    zkApp->>Deployer: log initial state num: Field(1)
    Sender->>zkApp: create update transaction
    zkApp->>Sender: process update transaction
    Note over zkApp: num state is updated to Field(3)
    Sender->>zkApp: prove and sign transaction, then send
    zkApp->>Sender: log updated state num: Field(3)
```

## How to build

```sh
npm run build
```

## How to run tests

```sh
npm run test
npm run testw # watch mode
```

## How to run coverage

```sh
npm run coverage
```

## License

[Apache-2.0](LICENSE)
