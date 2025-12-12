# Elliptic++ Bitcoin AML System

Use Case: Anti–money laundering on Bitcoin graphs

* **Graph Model:** Transactions, Addresses (Wallets), Entities (Exchange, Marketplace, Gambling, MiningPool, Mixer, Ponzi); relationships like INPUT_OF, OUTPUT_TO, OWNS, ASSOCIATED_WITH

* **API Features**

  * Risk scoring for a transaction or address (licit/illicit likelihood)
    * e.g. GET `/api/tx/{tx_id}/risk and GET /api/addresses/{address}/risk`

  * Funds flow tracing across transactions and addresses (forward/backward, k hops)
    * e.g. GET `/api/flows?from_tx={tx_id}&direction=forward&hops=3`

  * Entity attribution for wallets (exchange, marketplace, etc.)
    * e.g. GET `/api/addresses/{address}/entity`

  * Subgraph export for investigation (center node + radius)
    * e.g. GET /api/subgraph?center={tx_or_address}&radius=2

## Data Sources

**Elliptic++ Bitcoin Dataset**

* GitHub: https://github.com/git-disl/EllipticPlusPlus

* 203,000 Bitcoin transactions & 822,000 wallet addresses

* Entity types: Exchange, Marketplace, Gambling, Mining pools, Mixers, Ponzi schemes

* Tutorial notebooks included