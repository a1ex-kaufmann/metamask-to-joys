## Connect your Metamask to Joys Digital in one click

[Deployed on github-pages](https://alexey-zhdanov.github.io/metamask-to-joys/)

## How it works

See [eip-3085](https://eips.ethereum.org/EIPS/eip-3085) and [metamask method](https://docs.metamask.io/guide/rpc-api.html#wallet-addethereumchain)

For security use [chains.json](https://chainid.network/chains.json) (https://chainid.network/)

```javascript
const chain = {
    chainId: "0x2231c60",
    chainName: "Joys Digital Mainnet",
    nativeCurrency: {
        name: "JOYS",
        symbol: "JOYS",
        decimals: 18,
    },
    rpcUrls: ["https://node.joys.digital"],
    blockExplorerUrls: ["https://explorer.joys.digital/"],
    iconUrls: []
};
window.ethereum
  .request({
    method: "wallet_addEthereumChain",
    params: [chain],
  })
  .catch((error) => {
    console.log(error);
    alert(
      "An error has occurred. Please make sure the metamask is ready to go. See error in log"
    );
  });
```
