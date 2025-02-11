# Morpheus Apollo 1

## Chain data
| Data | Value | 
| :--- | :---: |
| Genesis file |  [genesis file](genesis.json) |
| Chain ID | `morpheus-apollo-1` |
| Genesis time | `2021-04-27T13:00:00Z` |

## Desmos Version
```sh
$ desmos version --long
name: Desmos
server_name: desmos
version: 64b644bd
commit: 64b644bdc861988d2f8ef5b4356a1a5773b85c56
```

To checkout this version run: 

```
git checkout tags/v0.16.1
```

## Genesis state

## Genesis file hash
You can verify the validity of the genesis file by running:

```sh
jq -S -c -M '' genesis.json | shasum -a 256
```

It should return:

```
0f531ba4298a0c23e5ba13fa0a6c1aee62c5a9f1204e98b9ba792cf825b1aaa0  -
```

## Seed Nodes
```sh
be3db0fe5ee7f764902dbcc75126a2e082cbf00c@seed-1.morpheus.desmos.network:26656
4659ab47eef540e99c3ee4009ecbe3fbf4e3eaff@seed-2.morpheus.desmos.network:26656
1d9cc23eedb2d812d30d99ed12d5c5f21ff40c23@seed-3.morpheus.desmos.network:26656
```

## State sync nodes
```sh
67dcef828fc2be3c3bcc19c9542d2b228bd7cff9@seed-4.morpheus.desmos.network:26656
fcf8207fb84a7238089bd0cd8db994e0af9016b6@seed-5.morpheus.desmos.network:26656
```

## Parameters

### `x/evidence`
The `max_age_duration` in `x/evidence` is set to match the `unbonding_time` in `x/staking` which is `3 days`.

### `x/mint`
The **initial annual inflation** is set to `50%`. 
The **annual inflation range** is set to `40%`-`80%`, and **annual inflation change rate** to `40%`. 
The **bonded goal** is `80%`. 

**Blocks per year** are `5006000` based on the average `6.3s` block time on `morpheus-13001`.

### `x/slashing`
The `signed_blocks_window` is set to `7200` and `min_signed_per_window` to `0.05` based on `6.3s` average block time
on `morpheus-13001`. This translates to: 

> a validator will be slashed with 0.01% tokens because of around 12 hours downtime 
> (7200 blocks signing window * 95% misses * 6.3 / 60 mins / 60 seconds).

## Tokens
`udaric`

## Faucet
https://faucet.desmos.network
