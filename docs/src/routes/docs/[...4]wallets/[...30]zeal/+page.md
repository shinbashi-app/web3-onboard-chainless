---
title: Zeal
---

# {$frontmatter.title}

## Wallet module for connecting Zeal to web3-onboard

See [Zeal](https://www.zeal.app/) for details.

For any questions or issues related to integration with Zeal wallet do not hesitate to contact our builders via [hi@zeal.app](mailto:hi@zeal.app) OR ping us on twitter [@withzeal](https://twitter.com/withzeal)

## Install

<Tabs values={['yarn', 'npm']}>
<TabPanel value="yarn">

```sh copy
yarn add @shinbashi/core @shinbashi/zeal
```

  </TabPanel>
  <TabPanel value="npm">

```sh copy
npm install @shinbashi/core @shinbashi/zeal
```

  </TabPanel>
</Tabs>

## Usage

```typescript
import Onboard from '@shinbashi/core'
import zealWalletModule from '@shinbashi/zeal'

// initialize the module with options
const zealWalletSdk = zealWalletModule()

const onboard = Onboard({
  // ... other Onboard options
  wallets: [
    zealWalletModule()
    //... other wallets
  ]
})

const connectedWallets = await onboard.connectWallet()
console.log(connectedWallets)
```
