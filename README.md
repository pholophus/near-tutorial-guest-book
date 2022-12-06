Guest Book
==========

Our Guest Book example is a simple app composed by two main components:

1.  A smart contract that stores messages from users, allowing to attach money to them.
2.  A simple web-based frontend that displays the last 10 messages posted.

![img](https://docs.near.org/assets/images/guest-book-b305a87a35cbef2b632ebe289d44f7b2.png)

* * *

Starting the Project[​](#starting-the-project "Direct link to heading")
-----------------------------------------------------------------------

You have two options to start using the project. The first and recommended is to use the app through Gitpod, which will open a web-based interactive environment. The second option is to clone the repository locally, for which you will need to install all the [Prerequisites](/develop/prerequisites).

*   🌐 JavaScript
*   🦀 Rust
*   🚀 AssemblyScript

Gitpod

Clone locally

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/guest-book-js.git)

🌐 `https://github.com/near-examples/guest-book-js`

Gitpod

Clone locally

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/guest-book-rust.git)

🦀 `https://github.com/near-examples/guest-book-rust`

Gitpod

Clone locally

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/near-examples/guest-book.git)

🚀 `https://github.com/near-examples/guest-book`

If you choose Gitpod a new browser window will open automatically with the code, give it a minute and the frontend will pop-up (make sure the pop-up window is not blocked).

If you are running the app locally, enter the directory where you cloned it and use `yarn` to install dependencies, and `yarn start` to start it.

    cd guest-bookyarnyarn deployyarn start

Your contract will then be **compiled** and **deployed** to an **account** in the `testnet` network. When done, a browser window should open.

* * *

Interacting With the Guest Book[​](#interacting-with-the-guest-book "Direct link to heading")
---------------------------------------------------------------------------------------------

![img](https://docs.near.org/assets/images/guest-book-b305a87a35cbef2b632ebe289d44f7b2.png) _Frontend of the Guest Book app_

Go ahead and login with your NEAR account. If you don't have one, you will be able to create one in the moment. Once logged in, you will be able to sign a message in the guest book. You can further send some money alongside your message. If you attach more than 0.01Ⓝ then your message will be marked as "premium".

* * *

Structure of a dApp[​](#structure-of-a-dapp "Direct link to heading")
---------------------------------------------------------------------

Now that you understand what the dApp does, let us take a closer look to its structure:

1.  The frontend code lives in the `/frontend` folder.
2.  The smart contract code is in the `/contract` folder.

### Contract[​](#contract "Direct link to heading")

The contract presents 2 methods: `add_message` and `get_message`.

*   🌐 JavaScript
*   🦀 Rust

contract/src/contract.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/guest-book-js/blob/master/contract/src/contract.ts#L4-L24#)

contract/src/lib.rs

    loading...

[See full example on GitHub](https://github.com/near-examples/guest-book-rust/blob/main/contract/src/lib.rs#L29-L50#)

### Frontend[​](#frontend "Direct link to heading")

The frontend is composed by a single HTML file (`/index.html`) and uses REACT. Check `/App.js` and `/index.js` to understand how components are displayed in the screen.

You will notice in `/assets/js/index.js` the following code:

*   🌐 JavaScript

frontend/index.js

    loading...

[See full example on GitHub](https://github.com/near-examples/guest-book-rust/blob/main/frontend/index.js#L15-L25#)

It setups the necessary variables and starts the app.

* * *

Testing[​](#testing "Direct link to heading")
---------------------------------------------

When writing smart contracts it is very important to test all methods exhaustively. In this project you have two types of tests: unit and integration. Before digging in them, go ahead and perform the tests present in the dApp through the command `yarn test`.

### Unit test[​](#unit-test "Direct link to heading")

Unit tests check individual functions in the smart contract. Right now only rust implements unit testing.

*   🦀 Rust

contract/src/lib.rs

    loading...

[See full example on GitHub](https://github.com/near-examples/guest-book-rust/blob/main/contract/src/lib.rs#L63-L86#)

### Integration test[​](#integration-test "Direct link to heading")

Integration tests are generally written in JavaScript. They automatically deploy your contract and execute methods on it. In this way, integration tests simulate interactions between the contract and the users in a realistic scenario. You will find the integration tests for `hello-near` in `integration-tests/`.

*   🌐 JavaScript

integration-tests/src/main.ava.ts

    loading...

[See full example on GitHub](https://github.com/near-examples/guest-book-js/blob/master/integration-tests/src/main.ava.ts#L39-L59#)
