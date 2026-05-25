# Phantom (phantom)
Phantom is a self-custodial multi-chain crypto wallet for Solana, Ethereum, Polygon, Base, Bitcoin, Sui, Monad, and HyperEVM, distributed as a mobile app (iOS/Android) and browser extension with more than 20 million users. For developers, Phantom exposes injected Provider APIs per chain on `window.phantom` (Solana, EVM, Bitcoin, Sui) following the Wallet Standard and EIP-1193, a Universal Link / `phantom://` Deeplinks API for mobile dApp integration with encrypted session handshakes, a multi-platform Connect SDK suite (React, React Native, Browser SDKs) with embedded wallet support and OAuth social login (Google, Apple), and a Phantom MCP Server that exposes 27 tools across wallet operations, swaps, portfolio rebalancing, and Hyperliquid perpetuals for AI agents — each agent receives its own wallet via device-code authentication. Apps register through the Phantom Portal to obtain an App ID, configure redirect URLs, verify domains, and opt into auto-confirm contracts.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/phantom/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Base, Bitcoin, Blockchain, Crypto, Cryptocurrency, Deeplinks, Embedded Wallet, Ethereum, EVM, Monad, MCP, Mobile, Polygon, Self-Custody, Solana, Sui, Wallet, Web3

## Timestamps

- **Created:** 2026-05-24
- **Modified:** 2026-05-24

## Supported Chains

| Chain | Provider Namespace | Notes |
|---|---|---|
| Solana | `window.phantom.solana` | Wallet Standard, Sign-In With Solana, Versioned Transactions, Token-2022, Actions & Blinks |
| Ethereum | `window.ethereum` / `window.phantom.ethereum` | EIP-1193 |
| Polygon | `window.ethereum` | EIP-1193 |
| Base | `window.ethereum` | EIP-1193 |
| Monad (testnet) | `window.ethereum` | EIP-1193 |
| HyperEVM | `window.ethereum` | EIP-1193 |
| Bitcoin | `window.phantom.bitcoin` | Taproot, SegWit, p2sh, p2pkh — provider deprecation announced |
| Sui | `window.phantom` | Move; `signTransactionBlock`, `signMessage` |

## APIs

### Phantom Solana Provider API
Solana wallet provider injected at `window.phantom.solana` exposing connect, disconnect, signMessage, signIn (Sign-In With Solana), signTransaction, signAllTransactions, and signAndSendTransaction. Implements the Solana Wallet Standard so dApps can also integrate through `@solana/wallet-adapter`. Supports versioned transactions, priority fees, Token-2022 extensions, and Solana Actions & Blinks.

**Human URL:** [https://docs.phantom.com/solana/integrating-phantom](https://docs.phantom.com/solana/integrating-phantom)

- [Documentation — Integrating Phantom](https://docs.phantom.com/solana/integrating-phantom)
- [Documentation — Wallet Standard](https://docs.phantom.com/developer-powertools/wallet-standard)
- [Documentation — Sign-In With Standards](https://docs.phantom.com/developer-powertools/sign-in-with-standards)
- [Documentation — Versioned Transactions](https://docs.phantom.com/developer-powertools/solana-versioned-transactions)
- [Documentation — Token Extensions (Token22)](https://docs.phantom.com/developer-powertools/solana-token-extensions-token22)
- [Documentation — Priority Fees](https://docs.phantom.com/developer-powertools/solana-priority-fees)
- [Documentation — Actions & Blinks](https://docs.phantom.com/developer-powertools/solana-actions-and-blinks)

### Phantom EVM Provider API
EIP-1193 compliant Ethereum Provider API injected at `window.ethereum` and `window.phantom.ethereum` for Ethereum, Polygon, Base, Monad testnet, and HyperEVM. Supports the full Ethereum RPC surface for connecting accounts, reading chain state, signing messages and typed data, sending transactions, switching and adding chains, and watching assets.

**Human URL:** [https://docs.phantom.com/ethereum-monad-testnet-base-and-polygon/provider-api-reference](https://docs.phantom.com/ethereum-monad-testnet-base-and-polygon/provider-api-reference)

- [Documentation — EVM Provider Reference](https://docs.phantom.com/ethereum-monad-testnet-base-and-polygon/provider-api-reference)

### Phantom Bitcoin Provider API
Bitcoin provider injected at `window.phantom.bitcoin` exposing `requestAccounts`, `signMessage`, and `signPSBT`. Returns `BtcAccount` objects with `address`, `publicKey`, `addressType`, and `purpose` ("payment" vs. "ordinals"). Supports Taproot (p2tr), SegWit (p2wpkh), p2sh, and p2pkh address types. The `window.phantom.bitcoin` provider is scheduled for deprecation in an upcoming release.

**Human URL:** [https://docs.phantom.com/bitcoin/provider-api-reference](https://docs.phantom.com/bitcoin/provider-api-reference)

- [Documentation — Bitcoin Provider Reference](https://docs.phantom.com/bitcoin/provider-api-reference)

### Phantom Sui Provider API
Sui provider exposed via `window.phantom` for browser and mobile platforms, offering `connect`, `signTransactionBlock`, and `signMessage` so Sui dApps can integrate Phantom alongside their existing EVM/Solana flows.

**Human URL:** [https://docs.phantom.com/sui/getting-started-with-sui](https://docs.phantom.com/sui/getting-started-with-sui)

- [Documentation — Getting Started with Sui](https://docs.phantom.com/sui/getting-started-with-sui)

### Phantom Deeplinks API
Universal Link (`https://phantom.app/ul/v1/<method>`) and custom protocol (`phantom://v1/<method>`) deeplinks for iOS and Android lets mobile dApps trigger Phantom for `connect`, `disconnect`, `signMessage`, `signTransaction`, `signAllTransactions`, `signAndSendTransaction`, and `browse` (open URL in the in-app browser). Uses an X25519 / TweetNaCl box encryption handshake with shared-secret-encrypted payloads and a returned session token. Currently scoped to Solana. Universal Links are the recommended scheme.

**Human URL:** [https://docs.phantom.com/phantom-deeplinks/deeplinks-ios-and-android](https://docs.phantom.com/phantom-deeplinks/deeplinks-ios-and-android)

**Base URL:** `https://phantom.app/ul/v1`

- [Documentation — Deeplinks (iOS / Android)](https://docs.phantom.com/phantom-deeplinks/deeplinks-ios-and-android)
- [Documentation — Handling Sessions](https://docs.phantom.com/phantom-deeplinks/handling-sessions)
- [Documentation — Specifying Redirects](https://docs.phantom.com/phantom-deeplinks/specifying-redirects)
- [Documentation — Encryption](https://docs.phantom.com/phantom-deeplinks/encryption)
- [Documentation — Limitations](https://docs.phantom.com/phantom-deeplinks/limitations)

### Phantom React SDK
React SDK (`@phantom/react-sdk`) for integrating Phantom across Solana and EVM chains with embedded wallet support and OAuth social login (Google, Apple) alongside the browser extension path. Provides hooks (`usePhantom`, `useSolana`, `useEthereum`) and components (`ConnectButton`, `ConnectBox`) plus peer dependencies on `@solana/web3.js` and `viem`.

**Human URL:** [https://docs.phantom.com/sdks/react-sdk](https://docs.phantom.com/sdks/react-sdk)

- [Documentation — React SDK](https://docs.phantom.com/sdks/react-sdk)
- [SDK — npm @phantom/react-sdk](https://www.npmjs.com/package/@phantom/react-sdk)
- [Source — phantom-connect-sdk](https://github.com/phantom/phantom-connect-sdk)

### Phantom React Native SDK
React Native SDK that lets iOS and Android apps embed Phantom wallet functionality, including embedded wallets, social login, and connection to the installed Phantom mobile app via deeplinks.

**Human URL:** [https://docs.phantom.com/sdks/react-native-sdk](https://docs.phantom.com/sdks/react-native-sdk)

- [Documentation — React Native SDK](https://docs.phantom.com/sdks/react-native-sdk)
- [Source — phantom-connect-sdk](https://github.com/phantom/phantom-connect-sdk)
- [Sample — React Native Wallet SDK Demo App](https://github.com/phantom/react-native-wallet-sdk-demo-app)
- [Sample — Bare React Native Wallet SDK Demo App](https://github.com/phantom/bare-react-native-wallet-sdk-demo-app)

### Phantom Browser SDK
Framework-agnostic Browser SDK for integrating Phantom into vanilla JavaScript or TypeScript web apps. Wraps the injected providers and embedded wallet flows so non-React applications can take advantage of the same connect/sign/transaction surface.

**Human URL:** [https://docs.phantom.com/sdks/browser-sdk](https://docs.phantom.com/sdks/browser-sdk)

- [Documentation — Browser SDK](https://docs.phantom.com/sdks/browser-sdk)
- [Source — phantom-connect-sdk](https://github.com/phantom/phantom-connect-sdk)

### Phantom MCP Server
Model Context Protocol server (`@phantom/mcp-server`) that exposes 27 tools to AI agents across wallet operations (connection status, addresses, balances, transfers, transaction sending, message and typed-data signing, simulation, allowances, login, pay), swap and portfolio (`buy_token`, `portfolio_rebalance`), and Hyperliquid perpetuals (market data, positions, orders, deposits, leverage, spot-to-perps transfers). Each agent gets its own wallet via device-code Phantom sign-in; sessions are stored at `~/.phantom-mcp/session.json` with OIDC-stamped KMS request signing. Supports Solana, Ethereum, Bitcoin, and Sui.

**Human URL:** [https://docs.phantom.com/phantom-mcp-server](https://docs.phantom.com/phantom-mcp-server)

- [Documentation — MCP Server Overview](https://docs.phantom.com/phantom-mcp-server)
- [Documentation — MCP Server Setup](https://docs.phantom.com/phantom-mcp-server/setup)
- [Documentation — MCP Server Resource](https://docs.phantom.com/resources/mcp-server)
- [SDK — npm @phantom/mcp-server](https://www.npmjs.com/package/@phantom/mcp-server)

### Phantom Portal
Developer portal for registering apps that integrate Phantom. Provides account creation, app creation with App IDs, domain verification, redirect URL configuration, app metadata editing, and contract allowlisting for auto-confirm flows that streamline repeat signing.

**Human URL:** [https://docs.phantom.com/phantom-portal/portal](https://docs.phantom.com/phantom-portal/portal)

- [Documentation — Portal Overview](https://docs.phantom.com/phantom-portal/portal)
- [Documentation — Getting Started](https://docs.phantom.com/phantom-portal/getting-started)
- [Documentation — Create Account](https://docs.phantom.com/phantom-portal/create-account)
- [Documentation — Create App](https://docs.phantom.com/phantom-portal/create-app)
- [Documentation — Verify Domain](https://docs.phantom.com/phantom-portal/verify-domain)
- [Documentation — Configure URLs](https://docs.phantom.com/phantom-portal/configure-urls)
- [Documentation — App Information](https://docs.phantom.com/phantom-portal/edit-app-info)
- [Documentation — Get App ID](https://docs.phantom.com/phantom-portal/get-app-id)
- [Documentation — Contracts & Auto-Confirm](https://docs.phantom.com/phantom-portal/contracts)

## Common

- [Website](https://phantom.com)
- [Developer Portal](https://docs.phantom.com)
- [Docs Index (llms.txt)](https://docs.phantom.com/llms.txt)
- [Developers Hub](https://phantom.com/learn/developers)
- [Download / Sign Up](https://phantom.com/download)
- [GitHub Org](https://github.com/phantom)
- [Changelog / Updates](https://docs.phantom.com/updates)
- [Status Page](https://status.phantom.com)
- [User Limits](https://docs.phantom.com/user-limits)
- [Go-Live Checklist](https://docs.phantom.com/best-practices/go-live-checklist)
- [Testnet Mode](https://docs.phantom.com/developer-powertools/testnet-mode)
- [Mobile Web Debugging](https://docs.phantom.com/developer-powertools/mobile-web-debugging)
- [Domain & Transaction Warnings](https://docs.phantom.com/developer-powertools/domain-and-transaction-warnings)
- [Lighthouse Transaction Validation](https://docs.phantom.com/developer-powertools/lighthouse)
- [AI-Assisted Development](https://docs.phantom.com/developer-powertools/ai-tools)
- [Cursor AI Prompts](https://docs.phantom.com/resources/cursor-prompts)
- [Demo Apps & Sandboxes](https://docs.phantom.com/resources/sandbox)
- [Logos & Brand Assets](https://docs.phantom.com/resources/logos-and-assets)
- [Developer FAQ](https://docs.phantom.com/resources/faq)
- [Blog](https://phantom.com/learn/blog)
- [Support](https://help.phantom.com/hc/en-us)
- [Feedback / Feature Requests](https://feedback.phantom.com/feature-requests)
- [Press Kit](https://phantom.com/press-kit)
- [Careers](https://phantom.com/careers)
- [Terms of Service](https://phantom.com/terms-of-service)
- [Privacy Policy](https://phantom.com/privacy-policy)
- [Security](https://phantom.com/security)
- [X / Twitter](https://x.com/phantom)
- [LinkedIn](https://www.linkedin.com/company/phantom-app)
- [YouTube](https://www.youtube.com/@phantom)
- [Reddit](https://www.reddit.com/r/phantom_wallet)
- [Instagram](https://www.instagram.com/phantom)

## Source Code & Samples

- [Phantom Connect SDK](https://github.com/phantom/phantom-connect-sdk)
- [Deep Link Demo App](https://github.com/phantom/deep-link-demo-app)
- [Multi-Chain Sandbox](https://github.com/phantom/multi-chain-sandbox)
- [Browser Sandbox](https://github.com/phantom/sandbox)
- [EVM Sandbox](https://github.com/phantom/eth_sandbox)
- [Shortcuts Sandbox](https://github.com/phantom/shortcuts-sandbox)
- [Deeplinks Movie Tutorial](https://github.com/phantom/deep-links-movie-tutorial)
- [Phantom Wagmi Connector](https://github.com/phantom/phantom-wagmi-connector)
- [Sign In With Solana](https://github.com/phantom/sign-in-with-solana)
- [Bitcoin Wallet Standard](https://github.com/phantom/bitcoin-wallet-standard)
- [Sol Wallet Adapter](https://github.com/phantom/sol-wallet-adapter)
- [Solana Blinks](https://github.com/phantom/blinks)
- [Phantom Agent Kit](https://github.com/phantom/phantom-agent-kit)
- [Phantom Skill Generator](https://github.com/phantom/phantom-skill-generator)
- [Phantom Blocklist](https://github.com/phantom/blocklist)
- [Solana Token List](https://github.com/phantom/token-list)
- [NFT Shortcuts](https://github.com/phantom/shortcuts)
- [Synpress E2E Fork](https://github.com/phantom/synpress)
