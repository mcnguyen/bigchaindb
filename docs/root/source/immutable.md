# How BigchainDB is Immutable

The word _immutable_ means "unchanging over time or unable to be changed." For example, the decimal digits of π are immutable (3.14159…).

The blockchain community often describes blockchains as “immutable.” If we interpret that word literally, it means that blockchain data is unchangeable or permanent, which is absurd. The data _can_ be changed. For example, a plague might drive humanity extinct; the data would then get corrupted over time due to water damage, thermal noise, and the general increase of entropy. In the case of Bitcoin, nothing so drastic is required: a 51% attack will suffice.

It’s true that blockchain data is more difficult to change (or delete) than usual. It's more than just "tamper-resistant" (which implies intent), blockchain data also resists random changes that can happen without any intent, such as data corruption on a hard drive. Therefore, in the context of blockchains, we interpret the word “immutable” to mean *practically* immutable, for all intents and purposes. (Linguists would say that the word “immutable” is a _term of art_ in the blockchain community.)

Blockchain data can achieve immutability in several ways:

1. **Replication.** All data is replicated (copied) to several different places. The replication factor can be set by the consortium. The higher the replication factor, the more difficult it becomes to change or delete all replicas.
1. **Internal watchdogs.** All nodes monitor all changes and if some unallowed change happens, then appropriate action can be taken.
1. **External watchdogs.** A consortium may opt to have trusted third-parties to monitor and audit their data, looking for irregularities. For a consortium with publicly-readable data, the public can act as an auditor.
1. **Economic incentives.** Some blockchain systems make it very expensive to change old stored data. Examples include proof-of-work and proof-of-stake systems. BigchainDB doesn't use explicit incentives like those.
1. Data can be stored using fancy techniques, such as error-correction codes, to make some kinds of changes easier to undo.
1. **Cryptographic signatures** are often used as a way to check if messages (e.g. transactions, blocks or votes) have been tampered with enroute, and as a way to verify who signed the messages. In BigchainDB, each transaction must be signed (by one or more parties), each block is signed by the node that created it, and each vote is signed by the node that cast it.
1. **Full or partial backups** may be recorded from time to time, possibly on magnetic tape storage, other blockchains, printouts, etc.
1. **Strong security.** Node owners can adopt and enforce strong security policies.
1. **Node diversity.** Diversity makes it so that no one thing (e.g. natural disaster or operating system bug) can compromise enough of the nodes. See [the section on the kinds of node diversity](diversity.html).

Some of these things come "for free" as part of the BigchainDB software, and others require some extra effort from the consortium and node owners.
