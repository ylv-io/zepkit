# zepkit
A truffle box containing React, ZeppelinOS, OpenZeppelin, Truffle and Infura.

This box comes with everything you need to start using upgradeable Smart
contracts inside your applications. It also includes all the configuration
required to deploy to different networks.

## Requirements

Install ZeppelinOS:

```
npm install --g zos
```

Make sure `ganache-cli` is installed:

```
npm install -g ganache-cli
```

Run your local blockchain unlocking your first account:

```
ganache-cli --secure -u 0 -u 1 -u 2 --deterministic
```

## Installation

First ensure you are in a new and empty directory.

1. Run the `unbox` command via `npx` and skip to step 3. This will install all necessary dependencies. A Create-React-App is generated in the `client` directory.
   ```js
   npx truffle unbox zepkit
   ```

2. Alternatively, you can install Truffle globally and run the `unbox` command.
    ```javascript
    npm install -g truffle
    truffle unbox zepkit
    ```

3. Initialize the zeppelin os project
    ```javascript
    zos init zepkit
    ```

4. In the `client` directory, we run the React app. Smart contract changes must be manually recompiled and migrated.
    ```javascript
    // in another terminal (i.e. not in the truffle develop prompt)
    cd client
    npm run start
    ```

6. Truffle can run tests written in Solidity or JavaScript against your smart contracts. Note the command varies slightly if you're in or outside of the development console.
    ```javascript
    // inside the development console.
    test

    // outside the development console..
    truffle test
    ```

7. Jest is included for testing React components. Compile your contracts before running Jest, or you may receive some file not found errors.
    ```javascript
    // ensure you are inside the client directory when running this
    npm run test
    ```

8. To build the application for production, use the build script. A production build will be in the `client/build` folder.
    ```javascript
    // ensure you are inside the client directory when running this
    npm run build
    ```

## FAQ

* __How do I use this with the Ganache-CLI?__

    It's as easy as modifying the config file! [Check out our documentation on adding network configurations](http://truffleframework.com/docs/advanced/configuration#networks). Depending on the port you're using, you'll also need to update line 29 of `client/src/utils/getWeb3.js`.

* __Where is my production build?__

    The production build will be in the `client/build` folder after running `npm run build` in the `client` folder.

* __Where can I find more documentation?__

    This box is a marriage of [Truffle](http://truffleframework.com/) and a React setup created with [create-react-app](https://github.com/facebookincubator/create-react-app/blob/master/packages/react-scripts/template/README.md). Either one would be a great place to start!
