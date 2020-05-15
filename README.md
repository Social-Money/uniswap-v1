* Website: [uniswap.io/](https://uniswap.io/)
* Docs: [docs.uniswap.io/](https://docs.uniswap.io/)
* Twitter: [@UniswapExchange](https://twitter.com/UniswapExchange)
* Reddit: [/r/Uniswap/](https://www.reddit.com/r/UniSwap/)
* Email: [contact@uniswap.io](mailto:contact@uniswap.io)
* Slack: [uni-swap.slack.com/](https://join.slack.com/t/uni-swap/shared_invite/enQtNDYwMjg1ODc5ODA4LWEyYmU0OGU1ZGQ3NjE4YzhmNzcxMDAyM2ExNzNkZjZjZjcxYTkwNzU0MGE3M2JkNzMxOTA2MzE2ZWM0YWQwNjU)
* Whitepaper: [Link](https://hackmd.io/C-DvwDSfSxuh-Gd4WKE_ig)

## Installation:

#### Requires [Python 3](https://www.python.org/download/releases/3.0/)

1) Clone Uniswap
```
$ git clone https://github.com/Uniswap/contracts-vyper
$ cd contracts-vyper
```

2) Setup virtual environment
```
$ pip3 install virtualenv
$ virtualenv -p python3 env
$ source env/bin/activate
```

3) Install dependencies
```
pip install -r requirements.txt
```

4) (Optional) Switch Vyper compiler to version used in Uniswap [verification](https://github.com/runtimeverification/verified-smart-contracts/tree/uniswap/uniswap)  
```
cd vyper
git reset --hard 35038d20bd9946a35261c4c4fbcb27fe61e65f78
cd ..
```

5) Run tests
```
$ pytest -v tests/
```
### 合约部署
1. 项目clone，设置好python环境，详情见：https://github.com/Uniswap/contracts-vyper/blob/master/README.md
2. use vyper uniswap_factory.vy to get bytecode and vyper -f abi uniswap_factory.vy to get the ABI. Do the same for uniswap_exchange.vy
3. Deploy both contracts separately from their bytecode using https://mycrypto.com/contracts/deploy
4. Use factory ABI (step 2) + factory address (step 3) and https://mycrypto.com/contracts/interact to open an interface to the uniswap factory
5. call initializeFactory(templateAddress) and pass in the address of the deployed uniswap_exchange.vy contract (step 2)

- uniswap_factory: `0xc4d477bcf1578ebf4dee2318e19ab7649a83f5bb`
- uniswap_exchange: `0xb162ea33ad2ebf86033db73fcfc6b5f954c93e08`