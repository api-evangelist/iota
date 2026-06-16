# IOTA (iota)

IOTA is an open-source distributed ledger technology built to bring real-world applications on-chain. It is the first internet-scale programmable blockchain platform powered by the Move programming language with horizontal scaling, feeless transactions, and a unique parallel transaction processing model. IOTA exposes a JSON-RPC 2.0 API over HTTP and a GraphQL RPC for querying objects, checkpoints, transactions, coins, events, and on-chain state on Mainnet, Testnet, and Devnet networks. The platform targets trade and supply chains, decentralized finance, digital identity, real-world asset tokenization, and product lifecycle management.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/iota/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/iota/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Blockchain
- Distributed Ledger
- Web3
- DeFi
- Cryptocurrency
- Move
- Tangle

## Timestamps

- **Created:** 2026-06-14
- **Modified:** 2026-06-14

## APIs

### IOTA Coin Query API

Coin and balance-oriented JSON-RPC methods for the IOTA blockchain. Provides iotax_getAllBalances to retrieve total balances across all coin types for an address, iotax_getAllCoins to list all coin objects owned by an address, iotax_getBalance for the balance of a specific coin type, iotax_getCirculatingSupply to retrieve circulating supply summary, iotax_getCoinMetadata for token symbol, decimals and description, iotax_getCoins to list coins of a specific type with pagination, and iotax_getTotalSupply to return the total supply for a given coin type.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Coins
- Balances
- Tokens
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Read API

Core read-oriented JSON-RPC methods for the IOTA blockchain. Includes iota_getChainIdentifier to retrieve the genesis checkpoint digest, iota_getCheckpoint and iota_getCheckpoints for checkpoint data with pagination, iota_getObject and iota_multiGetObjects for on-chain object retrieval, iota_getTransactionBlock for individual transaction details, iota_multiGetTransactionBlocks for batch transaction lookup, iota_getEvents to query on-chain events by filter criteria, iota_getProtocolConfig for current protocol configuration, iota_getLatestCheckpointSequenceNumber, iota_getTotalTransactionBlocks, and iota_tryGetPastObject for historical object state.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Objects
- Checkpoints
- Transactions
- Events
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Extended API

Advanced indexer-exclusive JSON-RPC methods for the IOTA blockchain. Provides address metrics via iotax_getAllEpochAddressMetrics and iotax_getLatestAddressMetrics, epoch data via iotax_getCurrentEpoch and iotax_getEpochMetrics, dynamic field access via iotax_getDynamicFieldObject and iotax_getDynamicFields, network metrics, event and transaction queries with rich filtering, IOTA Names (SuiNS-compatible) resolution, and validator APY data. Approximately 18 methods available exclusively through the indexer endpoint rather than full nodes.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://indexer.mainnet.iota.cafe:443`

#### Tags

- Epochs
- Metrics
- Events
- Dynamic Fields
- Indexer
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Governance Read API

Governance and staking JSON-RPC methods for the IOTA blockchain. Includes iotax_getCommitteeInfo to retrieve committee data for specific epochs, iotax_getLatestIotaSystemState to return the full system state object, iotax_getReferenceGasPrice for the current network gas price, iotax_getStakes and iotax_getStakesByIds to query staking positions, iotax_getValidatorsApy for validator annual percentage yields, iotax_getCheckpointSummaryByEpoch, and additional epoch-scoped governance queries totaling 9 methods.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Governance
- Validators
- Staking
- System State
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Move Utils API

Move language introspection JSON-RPC methods for the IOTA blockchain. Provides iota_getMoveFunctionArgTypes to retrieve function argument types for a Move function, iota_getNormalizedMoveFunction for full function structure including visibility and generics, iota_getNormalizedMoveModule to retrieve a normalized Move module, iota_getNormalizedMoveModulesByPackage to list all modules in a package, and iota_getNormalizedMoveStruct for detailed struct representation including fields and abilities. These 5 methods enable smart contract introspection and on-chain ABI discovery.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Move
- Smart Contracts
- Modules
- Introspection
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Transaction Builder API

Transaction construction JSON-RPC methods for the IOTA blockchain. Includes methods for building unsigned transactions such as unsafe_transferObject, unsafe_transferIota, unsafe_payIota, unsafe_pay, unsafe_payAllIota, unsafe_moveCall for Move function invocations, unsafe_requestAddStake and unsafe_requestWithdrawStake for staking operations, and additional batch transfer and publish methods. These 16 unsafe transaction builder methods produce serialized unsigned transactions requiring subsequent signing and submission via the Write API.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Transactions
- Transfer
- Staking
- Construction
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA Write API

Transaction execution and simulation JSON-RPC methods for the IOTA blockchain. Provides iota_executeTransactionBlock to submit a signed transaction to the network and return results, iota_dryRunTransactionBlock to simulate a transaction without broadcasting and receive full effects and events, iota_devInspectTransactionBlock for development inspection of transaction execution with arbitrary gas budgets, and iotax_estimateGasBudget for gas budget estimation. These 4 methods handle all state-mutating operations on the IOTA network.

- **Human URL:** [https://docs.iota.org/iota-api-ref](https://docs.iota.org/iota-api-ref)
- **Base URL:** `https://api.mainnet.iota.cafe:443`

#### Tags

- Transactions
- Execution
- Simulation
- Submit
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/iota-api-ref)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### IOTA GraphQL API

GraphQL RPC interface for the IOTA blockchain, providing an alternative to the JSON-RPC API. Supports querying transaction blocks, objects, checkpoints, events, and on-chain state using GraphQL query syntax. Available on all IOTA networks including Mainnet at graphql.mainnet.iota.cafe, Testnet at graphql.testnet.iota.cafe, and Devnet at graphql.devnet.iota.cafe. Cursor-based pagination is supported for list operations.

- **Human URL:** [https://docs.iota.org/developer/references/iota-api](https://docs.iota.org/developer/references/iota-api)
- **Base URL:** `https://graphql.mainnet.iota.cafe`

#### Tags

- GraphQL
- Queries
- Objects
- Transactions
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/developer/references/iota-api)
- [API Reference](https://graphql.mainnet.iota.cafe)
- [Graph Q L](graphql/iota-graphql.md)

### IOTA EVM JSON-RPC API

Ethereum-compatible JSON-RPC API for the IOTA EVM Layer 2. Supports standard Ethereum JSON-RPC methods enabling Solidity smart contract deployment and interaction via EVM-compatible tooling including Hardhat, Foundry, and MetaMask. Provides HTTP and WebSocket transports for state queries and event subscriptions. The IOTA EVM is a WASP-based smart contract chain with an Ethereum-compatible interface for cross-chain interoperability and developer migration from EVM ecosystems.

- **Human URL:** [https://docs.iota.org/developer/iota-evm/references/json-rpc-spec](https://docs.iota.org/developer/iota-evm/references/json-rpc-spec)
- **Base URL:** `https://json-rpc.evm.testnet.iotaledger.net`

#### Tags

- EVM
- Ethereum
- Smart Contracts
- L2
- Blockchain

#### Properties

- [Documentation](https://docs.iota.org/developer/iota-evm/references/json-rpc-spec)
- [API Reference](https://docs.iota.org/developer/iota-evm/references/openapi/ethereum-json-rpc)
- [OpenAPI](openapi/iota-evm-wasp-openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.iota.org/)
- [Portal](https://docs.iota.org/)
- [Documentation](https://docs.iota.org/)
- [Getting Started](https://docs.iota.org/developer/getting-started)
- [API Reference](https://docs.iota.org/iota-api-ref)
- [Authentication](https://docs.iota.org/developer/network-overview)
- [SDK](https://docs.iota.org/developer/ts-sdk/)
- [SDK](https://github.com/iotaledger/iota/tree/develop/crates/iota-sdk)
- [SDK](https://docs.iota.org/developer/references/iota-api)
- [C L I](https://docs.iota.org/developer/getting-started)
- [GitHub Organization](https://github.com/iotaledger)
- [GitHub Repository](https://github.com/iotaledger/iota)
- [Explorer](https://explorer.iota.org/)
- [Faucet](https://faucet.testnet.iota.cafe)
- [Blog](https://blog.iota.org/)
- [Network Overview](https://docs.iota.org/developer/network-overview)
- [Terms of Service](https://www.iota.org/privacy-policy)
- [Privacy Policy](https://www.iota.org/privacy-policy)
- [Rate Limits](rate-limits/iota-rate-limits.yml)
- [Plans](plans/iota-plans.yml)
- [Fin Ops](finops/iota-finops.yml)
- [OpenAPI](openapi/iota-jsonrpc-openapi.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/iota-evm-wasp-openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Open R P C](openapi/iota-openrpc.json)
- [J S O N L D Context](json-ld/iota-context.jsonld)
- [Use Cases](undefined)
- [Features](undefined)
- [Graph Q L](graphql/iota-graphql.md)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
