# @shinbashi/dcent

## Wallet module for connecting D'CENT hardware wallets to web3-onboard

### Install

`npm i @shinbashi/dcent`

### Usage

```typescript
import Onboard from '@shinbashi/core'
import dcentModule from '@shinbashi/dcent'

const dcent = dcentModule()

const onboard = Onboard({
  // ... other Onboard options
  wallets: [
    dcent
    //... other wallets
  ]
})

const connectedWallets = await onboard.connectWallet()
console.log(connectedWallets)
```

### Filtering Platforms

You may decide that on certain platforms you do not want to display this wallet as a selectable option. To do that you can use the `filter` init option which is an array of platforms that you would like this wallet to **not** be displayed to the end user:

```typescript
import Onboard from '@shinbashi/core'
import dcentModule from '@shinbashi/dcent'

const dcent = dcentModule({ filter: ['Safari'] })

const onboard = Onboard({
  // ... other Onboard options
  wallets: [
    dcent
    //... other wallets
  ]
})

const connectedWallets = await onboard.connectWallet()
console.log(connectedWallets)
```

Initialization options:

```typescript
type dcentInitOptions = {
  customNetwork?: CustomNetwork
  filter?: Platform[]
  containerElement?: string
}
```

The following is a list of the platforms that can be filtered:

```typescript
type Platform = DeviceOSName | DeviceBrowserName | DeviceType | 'all'

type Platform =
  | 'Windows Phone'
  | 'Windows'
  | 'macOS'
  | 'iOS'
  | 'Android'
  | 'Linux'
  | 'Chrome OS'
  | 'Android Browser'
  | 'Chrome'
  | 'Chromium'
  | 'Firefox'
  | 'Microsoft Edge'
  | 'Opera'
  | 'Safari'
  | 'desktop'
  | 'mobile'
  | 'tablet'
```
