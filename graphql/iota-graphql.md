# IOTA GraphQL API

## Description

The IOTA GraphQL RPC provides a flexible, typed interface for querying on-chain state on the IOTA blockchain. It serves as an alternative to the JSON-RPC 2.0 API and is served by the IOTA indexer. The schema exposes 186 types covering queries, mutations, and subscriptions for objects, transactions, checkpoints, epochs, validators, Move packages, coins, events, and governance data.

The schema was introspected live from the mainnet endpoint and includes:

- **136 object types** (Address, TransactionBlock, Object, Checkpoint, Epoch, Validator, Coin, MovePackage, MoveModule, MoveStruct, MoveFunction, StakedIota, DynamicField, Event, Balance, etc.)
- **12 input types** (ObjectFilter, TransactionBlockFilter, EventFilter, DynamicFieldName, CheckpointId, etc.)
- **10 union types** (ObjectOwner, TransactionBlockKind, ProgrammableTransaction, TransactionInput, EndOfEpochTransactionKind, DynamicFieldValue, etc.)
- **4 interface types** (IObject, IOwner, IMoveObject, IMoveDatatype)
- **9 enum types** (ExecutionStatus, ObjectKind, StakeStatus, MoveVisibility, MoveAbility, Feature, NameFormat, AddressTransactionBlockRelationship, TransactionBlockKindInput)
- **15 scalar types** (IotaAddress, Base64, BigInt, DateTime, MoveData, MoveTypeLayout, MoveTypeSignature, OpenMoveTypeSignature, UInt53, JSON, etc.)

## Endpoints

| Network  | GraphQL Endpoint                         |
|----------|------------------------------------------|
| Mainnet  | https://graphql.mainnet.iota.cafe        |
| Testnet  | https://graphql.testnet.iota.cafe        |
| Devnet   | https://graphql.devnet.iota.cafe         |

All endpoints require no API key. Cursor-based pagination is supported for all list fields.

## Documentation

- API Reference: https://docs.iota.org/developer/references/iota-api
- Developer Portal: https://docs.iota.org/
- GraphQL Playground: https://graphql.mainnet.iota.cafe (supports in-browser introspection and query execution)

## Schema Source

The SDL in `iota-schema.graphql` was generated via live introspection of `https://graphql.mainnet.iota.cafe` on 2026-06-14 using a `__schema` introspection query.

## Example Queries

### Get latest checkpoint

```graphql
{
  checkpoint {
    sequenceNumber
    timestamp
    transactionBlocks {
      totalCount
    }
  }
}
```

### Get object by ID

```graphql
{
  object(address: "0x...") {
    address
    version
    digest
    owner {
      ... on AddressOwner {
        owner {
          address
        }
      }
    }
  }
}
```

### Query transaction block

```graphql
{
  transactionBlock(digest: "...") {
    digest
    sender {
      address
    }
    effects {
      status
      gasEffects {
        gasSummary {
          computationCost
          storageCost
          storageRebate
        }
      }
    }
  }
}
```

### Query coin balances for an address

```graphql
{
  address(address: "0x...") {
    address
    balance(type: "0x2::iota::IOTA") {
      coinType {
        repr
      }
      totalBalance
    }
  }
}
```

## Key Root Query Fields

| Field | Description |
|-------|-------------|
| `address(address: IotaAddress!)` | Look up an address and its owned objects/coins |
| `object(address: IotaAddress!, version: UInt53)` | Fetch a single on-chain object |
| `objects(filter: ObjectFilter)` | Query objects with filtering |
| `transactionBlock(digest: String!)` | Fetch a transaction block by digest |
| `transactionBlocks(filter: TransactionBlockFilter)` | Query transaction blocks |
| `checkpoint(id: CheckpointId)` | Fetch a checkpoint (default: latest) |
| `checkpoints` | Paginate all checkpoints |
| `epoch(id: UInt53)` | Fetch an epoch (default: current) |
| `coinMetadata(coinType: String!)` | Metadata for a coin type |
| `movePackage(address: IotaAddress!)` | Fetch a Move package |
| `protocolConfig(protocolVersion: UInt53)` | Protocol configuration |
| `serviceConfig` | GraphQL service configuration and limits |

## Key Mutation Fields

| Field | Description |
|-------|-------------|
| `executeTransactionBlock` | Submit a signed transaction to the network |
| `dryRunTransactionBlock` | Simulate a transaction without broadcasting |
