# Ethereum transaction to UML sequence diagram generator

[![npm version](https://badge.fury.io/js/tx2uml.svg)](https://badge.fury.io/js/tx2uml)

[Unified Modeling Language (UML)](https://en.wikipedia.org/wiki/Unified_Modeling_Language) sequence diagram generator for Ethereum transaction.

# Install

The following installation assumes [Node.js](https://nodejs.org/en/download/) has already been installed which comes with [Node Package Manager (NPM)](https://www.npmjs.com/).

To install globally so you can run `tx2uml` from anywhere

```bash
npm link tx2uml --only=production
```

To upgrade run

```bash
npm upgrade tx2uml -g
```

To see which version you are using

```bash
npm ls tx2uml
```

## Alethio

All the contract calls are sourced from [Alethio](https://aleth.io/). Specifically, the [Contract Messages API](https://docs.aleth.io/api#tag/Contracts/paths/~1contracts~1{address}~1contractMessages/get) which as already done the hard work of parsing the transaction trace to extract the contract call details.

The Alethio API is free for volumes less than 10,000 calls a month. After that you'll need an API key from https://developers.aleth.io/. In order to trace large transactions, over a dozen Alethio calls can be made for one transaction as contract messages are limited to 100 messages per API call.

## Etherscan

The contract names are sourced from the verified contracts on [Etherscan](https://etherscan.io/), Specifically, the [get source code](https://etherscan.io/apis#contracts) API which includes the contract name if the contract has already been verified.

## PlantUML

[PlantUML](http://plantuml.com) is used to render the UML sequence diagrams.

The PlantUML files have the `.puml` file extension.

To generate files, use the [node-plantuml](https://www.npmjs.com/package/node-plantuml) package in the dev dependencies. Install from the project root

```
npm install node-plantuml
```

```
cd docs
npx puml generate ConditionalMultiSigWallet.puml -o .
```

### VS Code extension

[Jebbs PlantUML](https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml) extension for VS Code is used to authoring the PlantUML diagrams.

`Alt-D` on Windows, or `Option-D` on Mac, to stat PlantUML preview in VS Code.

# UML Syntax

Good online resources for learning UML

- [UML 2 Sequence Diagramming Guidelines](http://www.agilemodeling.com/style/sequenceDiagram.htm)
- [PlantUML Sequence diagrams](https://plantuml.com/sequence-diagram)

# Similar transaction visualisation tools

- (Parity Trace Decoder)[https://github.com/k06a/parity-trace-decoder]
- (Tenderly)[https://dashboard.tenderly.dev/]
- (EthTx info)[http://ethtx.info/]
- (Bloxy)[https://bloxy.info/]
- (Etherscan)[https://etherscan.io/txs]
