# Contract ABIs

This page includes JSON ABIs for the core Ignite contracts.

## Vault ABI

```json
[
  {
    "type": "function",
    "name": "deposit",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "token",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "withdraw",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "token",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "lockMargin",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "user",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "unlockMargin",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "user",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "balances",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "user",
        "type": "address"
      },
      {
        "name": "token",
        "type": "address"
      }
    ],
    "outputs": [
      {
        "name": "",
        "type": "uint256"
      }
    ]
  },
  {
    "type": "event",
    "name": "Deposited",
    "inputs": [
      {
        "name": "user",
        "type": "address",
        "indexed": true
      },
      {
        "name": "token",
        "type": "address",
        "indexed": true
      },
      {
        "name": "amount",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  },
  {
    "type": "event",
    "name": "Withdrawn",
    "inputs": [
      {
        "name": "user",
        "type": "address",
        "indexed": true
      },
      {
        "name": "token",
        "type": "address",
        "indexed": true
      },
      {
        "name": "amount",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  }
]
```

## Perps Clearing ABI

```json
[
  {
    "type": "function",
    "name": "settleTrade",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "trader",
        "type": "address"
      },
      {
        "name": "pnl",
        "type": "int256"
      },
      {
        "name": "fee",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "positions",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "trader",
        "type": "address"
      },
      {
        "name": "marketId",
        "type": "bytes32"
      }
    ],
    "outputs": [
      {
        "name": "size",
        "type": "int256"
      },
      {
        "name": "entryPrice",
        "type": "uint256"
      },
      {
        "name": "margin",
        "type": "uint256"
      }
    ]
  },
  {
    "type": "event",
    "name": "TradeSettled",
    "inputs": [
      {
        "name": "trader",
        "type": "address",
        "indexed": true
      },
      {
        "name": "pnl",
        "type": "int256",
        "indexed": false
      },
      {
        "name": "fee",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  }
]
```

## Fee Router ABI

```json
[
  {
    "type": "function",
    "name": "distribute",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "setShares",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "treasuryBps",
        "type": "uint16"
      },
      {
        "name": "stakingBps",
        "type": "uint16"
      },
      {
        "name": "incentivesBps",
        "type": "uint16"
      },
      {
        "name": "burnBps",
        "type": "uint16"
      }
    ],
    "outputs": []
  },
  {
    "type": "event",
    "name": "FeesDistributed",
    "inputs": [
      {
        "name": "amount",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  }
]
```

## Staking ABI

```json
[
  {
    "type": "function",
    "name": "stakeTokens",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "unstake",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "claimRewards",
    "stateMutability": "nonpayable",
    "inputs": [],
    "outputs": []
  },
  {
    "type": "function",
    "name": "stakeOf",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "user",
        "type": "address"
      }
    ],
    "outputs": [
      {
        "name": "",
        "type": "uint256"
      }
    ]
  },
  {
    "type": "event",
    "name": "Staked",
    "inputs": [
      {
        "name": "user",
        "type": "address",
        "indexed": true
      },
      {
        "name": "amount",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  },
  {
    "type": "event",
    "name": "RewardsClaimed",
    "inputs": [
      {
        "name": "user",
        "type": "address",
        "indexed": true
      },
      {
        "name": "amount",
        "type": "uint256",
        "indexed": false
      }
    ],
    "anonymous": false
  }
]
```

## IGNT Token ABI

```json
[
  {
    "type": "function",
    "name": "name",
    "stateMutability": "view",
    "inputs": [],
    "outputs": [
      {
        "type": "string"
      }
    ]
  },
  {
    "type": "function",
    "name": "symbol",
    "stateMutability": "view",
    "inputs": [],
    "outputs": [
      {
        "type": "string"
      }
    ]
  },
  {
    "type": "function",
    "name": "decimals",
    "stateMutability": "view",
    "inputs": [],
    "outputs": [
      {
        "type": "uint8"
      }
    ]
  },
  {
    "type": "function",
    "name": "totalSupply",
    "stateMutability": "view",
    "inputs": [],
    "outputs": [
      {
        "type": "uint256"
      }
    ]
  },
  {
    "type": "function",
    "name": "balanceOf",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "account",
        "type": "address"
      }
    ],
    "outputs": [
      {
        "type": "uint256"
      }
    ]
  },
  {
    "type": "function",
    "name": "transfer",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "to",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": [
      {
        "type": "bool"
      }
    ]
  },
  {
    "type": "function",
    "name": "approve",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "spender",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": [
      {
        "type": "bool"
      }
    ]
  },
  {
    "type": "function",
    "name": "allowance",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "owner",
        "type": "address"
      },
      {
        "name": "spender",
        "type": "address"
      }
    ],
    "outputs": [
      {
        "type": "uint256"
      }
    ]
  },
  {
    "type": "function",
    "name": "transferFrom",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "from",
        "type": "address"
      },
      {
        "name": "to",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      }
    ],
    "outputs": [
      {
        "type": "bool"
      }
    ]
  }
]
```

## Bridge Mint/Burn ABI

```json
[
  {
    "type": "function",
    "name": "bridgeOut",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "token",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      },
      {
        "name": "dstChainId",
        "type": "uint256"
      },
      {
        "name": "recipient",
        "type": "address"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "bridgeIn",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "messageHash",
        "type": "bytes32"
      },
      {
        "name": "token",
        "type": "address"
      },
      {
        "name": "amount",
        "type": "uint256"
      },
      {
        "name": "recipient",
        "type": "address"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "processed",
    "stateMutability": "view",
    "inputs": [
      {
        "name": "messageHash",
        "type": "bytes32"
      }
    ],
    "outputs": [
      {
        "type": "bool"
      }
    ]
  }
]
```

## Governance ABI

```json
[
  {
    "type": "function",
    "name": "propose",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "proposal",
        "type": "bytes"
      }
    ],
    "outputs": [
      {
        "type": "uint256"
      }
    ]
  },
  {
    "type": "function",
    "name": "vote",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "proposalId",
        "type": "uint256"
      },
      {
        "name": "support",
        "type": "bool"
      }
    ],
    "outputs": []
  },
  {
    "type": "function",
    "name": "execute",
    "stateMutability": "nonpayable",
    "inputs": [
      {
        "name": "proposalId",
        "type": "uint256"
      }
    ],
    "outputs": []
  }
]
```
