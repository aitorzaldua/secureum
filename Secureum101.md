## Accounts:
Ethereum state is made up of objects called "accounts", with each account having a 20-byte address and state transitions being direct transfers of value and information between accounts. (See here)

Ethereum account contains four fields:

    The nonce, a counter used to make sure each transaction can only be processed once

    The account's current ether balance

    The account's contract code, if present

    The account's storage (empty by default)

    Ethereum has two different types of accounts:

    Externally Owned Accounts (EOAs) controlled by private keys

    Contract Accounts controlled by their contract code

## Transactions:

Transactions are signed messages originated by an externally owned account (EOA), transmitted by the Ethereum network, and recorded on the Ethereum blockchain. Only transactions can trigger a change of state. Ethereum is a transaction-based state machine. (See here)

Transaction properties:

    Atomic: it is all or nothing i.e. cannot be divided or interrupted by other transactions

    Serial: Transactions are processed sequentially one after the other without any overlapping by other transactions

    Inclusion: Transaction inclusion is not guaranteed and depends on network congestion and gasPrice among other things. Miners determine inclusion.

    Order: Transaction order is not guaranteed and depends on network congestion and gasPrice among other things. Miners determine order.

A transaction is a serialized binary message that contains the following components (See here):

    nonce: A sequence number, issued by the originating EOA, used to prevent message replay

    gasPrice: The amount of ether (in wei) that the originator is willing to pay for each unit of gas

    gasLimit: The maximum amount of gas the originator is willing to pay for this transaction

    recipient: The destination Ethereum address

    value: The amount of ether (in wei) to send to the destination

    data: The variable-length binary data payload

    v,r,s: The three components of an ECDSA digital signature of the originating EOA


Contract creation transactions are sent to a special destination address called the zero address i.e. 0x0. A contract creation transaction contains a data payload with the compiled bytecode to create the contract. An optional ether amount in the value field will create the new contract with a starting balance.