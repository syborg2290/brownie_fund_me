To change global compiler version => right click on solidity version and select version from change global compiler(Remote)

Add a new network to brownie for keep remember as ethereum not as a development network.Bcz in Build deployments folder isn't saving for local or development network => ,
** brownie networks add Ethereum ganache-local host=http://127.0.0.1:7545 chainid=5777
** The check networks list => brownie networks list(ganache-local in there)

    ** brownie run scripts/deploy.py --network ganache-local

    ** Also check on build folder that mock_contract is also there.(deployments as 5777 of chain id)

brownie run scripts/fund_and_withdraw.py --network ganache-local

**//** If you accidently close the ganache ui that your all the testing transactions and deployments are automatically deleted by ganache ui.Keep in mind you have to delete all the contracts and deployments in the build folder before re deploy or run scripts(Work with locally deployed contract).

To run test cases => brownie test(Green means test cases are passed)

To run test one by one => brownie test -k test_function_name --network development(or any testnet or mainnet)

To use mainnet-fork blockchain as local(Copy of a real network) => brownie networks add development mainnet-fork-dev cmd=ganache-cli host=http://127.0.0.1:7545 fork=https://eth-mainnet.alchemyapi.io/v2/1Ud_98XjGfaUjHso53oca-91uzFQr8nx accounts=10 mnemonic=brownie port=8545

**//**After that => brownie run scripts/deploy.py --network mainnet-fork-dev

To delete a network => brownie networks delete mainnet-fork-dev

git rm --cached .env => To remove locally added file before push to server
