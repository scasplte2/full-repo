# full-repo

Goals:
1. Remove the last two commits from `develop` branch and push to remote
2. Create a PR against `master` and resolve conflicts
3. Create a branch called `experimental` without file2 off `develop`. Take a snapshot of this branch and create another repo called `partial-repo`. `partial-repo` should only have 1 commit.
4. Make changes on `experimental` and make only the history made after `partial-repo` to reflect on `partial-repo`
5. Make changes on `develop`, make the these changes reflect on both `experimental` branch as well as on `partial-repo`.


# Topl Technology Outline

# Core
|                           | ## Consensus                                                                                                                                                        |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Ouroboros                                                                                                                                                           |
| Description               | The algorithm used for ensuring that all nodes share the same state across the network                                                                              |
| User stories or processes | - Should implement OB Praos functionality as defined in [this paper](https://www.dropbox.com/s/8godfmmd4cv8d6z/2017%20-%20Kiayias%20-%20Ouroboros%20Praos.pdf?dl=0) |
| Test and verification     | - **Testing of Ouroborous                                                                                                                                           |



|                           | ## Transaction layer                                                                                                                                                        |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                          |
| Description               | Defines all state transition functions within the blockchain                                                                                                                |
| User stories or processes | - Assets<br>  - Create new assets<br>  - Transfer Assets<br>  - Burn assets<br>  - Update certificates associated with assets<br>- Transfer Polys<br>- Transfer Arbits<br>- |
| Test and verification     |                                                                                                                                                                             |



|                           | ## Smart contract engine                                                             |
| ------------------------- | ------------------------------------------------------------------------------------ |
| Name                      | Jotun                                                                                |
| Description               | Smart contract execution engine within Bifrost. Built using Oracle’s Truffle project |
| User stories or processes | - Storing assets in smart contracts<br>- Layered protocol execution (batch?)         |
| Test and verification     |                                                                                      |



|                           | ## Node view manager                                                                                                                                                                            |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                                              |
| Description               | Protocols relating to the management and viewing of the current state (eg. UTxO selection, mempool management, block formation, etc.)                                                           |
| User stories or processes | - Implement efficient box filtering algorithm<br>- Bloom filters on transactions for inclusion in block headers<br>- Users should be able to request and read information from all public boxes |
| Test and verification     |                                                                                                                                                                                                 |



|                           | ## Network manager                                                                    |
| ------------------------- | ------------------------------------------------------------------------------------- |
| Name                      | --                                                                                    |
| Description               | Protocols relating to the receipt and transmission of data into the protocol runtime. |
| User stories or processes | - Something we will need to work on                                                   |
| Test and verification     |                                                                                       |



|                           | ## Cryptography                                                                                           |
| ------------------------- | --------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                        |
| Description               | Functionality used for securing the blockchain                                                            |
| User stories or processes | - User signature types<br>  - Forward evolving key schemes<br>  - Proxy signatures<br>  - Ring signatures |
| Test and verification     |                                                                                                           |



----------
# Constructs
|                           | ## Internal API Interface                                                                                            |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| Name                      | Gastrop                                                                                                              |
| Description               | The internal API which Bifrost exposes for Jotun to submit protocol level transactions                               |
| User stories or processes | - Provide a sanitized input layer for communication between the smart contract engine and the protocol runtime.<br>- |
| Test and verification     |                                                                                                                      |



|                           | ## External API Interface                                                                                                                             |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Loki Layer                                                                                                                                            |
| Description               | The external (network) API which Bifrost exposes for users to submit transactions.                                                                    |
| User stories or processes | - Support all API calls via a JSON RPC request type<br>- Sanitize user inputs to disallow malicious or malformed calls from causing side effects<br>- |
| Test and verification     |                                                                                                                                                       |



|                           | ## Stable Currency                                                           |
| ------------------------- | ---------------------------------------------------------------------------- |
| Name                      | Poly                                                                         |
| Description               | The system dedicated to maintaining the price of Topl’s Poly stable currency |
| User stories or processes |                                                                              |
| Test and verification     |                                                                              |



|                           | ## Transaction Fee Mechanism                                                         |
| ------------------------- | ------------------------------------------------------------------------------------ |
| Name                      | --                                                                                   |
| Description               | The system dedicated to collecting transaction fees from users and distributing them |
| User stories or processes |                                                                                      |
| Test and verification     |                                                                                      |



|                           | ## Smart Assets                                                                                                                                                                    |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                                 |
| Description               | Protocol level assets which are integrated with a smart contract that will track certificates and other information regarding the asset                                            |
| User stories or processes | - Fungible and non-fungible assets<br>- Divisible and indivisible assets<br>- Fully linked asset mutation and division<br>- Support for arbitrary growth of certificate collection |
| Test and verification     |                                                                                                                                                                                    |



|                           | ## Valkyrie functions                                                                                                                                          |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Valkyrie                                                                                                                                                       |
| Description               | Functionality that will be added into smart contracts to allow protocol level transactions. This may eventually evolve into the full domain specific language. |
| User stories or processes | - Time based locks and triggers<br>- Multi-signature triggers<br>- Conditional asset creation                                                                  |
| Test and verification     |                                                                                                                                                                |



|                           | ## Side chaining                                                                                                             |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Heimdallr                                                                                                                    |
| Description               | Allows for interoperability between large scale existing networks and Toplnet                                                |
| User stories or processes | - Issue and receive ERC20 assets on Ethereum<br>- Issue and receive ERC721 assets on Ethereum<br>- Issue and receive Bitcoin |
| Test and verification     |                                                                                                                              |



----------
# User-Interface
|                           | ## Reference full node application                                                                                                                   |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Freya                                                                                                                                                |
| Description               | Full node (Bifrost) bundled with a GUI front-end which will secure the network while also providing wallet and staking capabilities                  |
| User stories or processes | - ** Inherent all the capabilities of the lite wallet (refer to lite wallet)<br>- Users should be able to stake using an account local to their node |
| Test and verification     |                                                                                                                                                      |



|                           | ## Reference lite wallet application                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| ------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | Freya Lite                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| Description               | Light wallet GUI front-end which will rely on third party services to provide wallet information and staking capabilities.                                                                                                                                                                                                                                                                                                                                                                                              |
| User stories or processes | - Allow for new key generation<br>  - BIP44 compatible<br>- Allow for users to import keys via mnemonic or encrypted keyfile<br>- Allow users to export keys via mnemonic or encrypted keyfile<br>- Sign all transactions to Toplnet<br>- Send token transfer transaction<br>- Deployment of library contracts<br>- Interaction with deployed contracts on Toplnet<br>- Cold storage capabilities (offline signing of transactions)<br>- Allow for users to stake their coins or delegate their rights to another party |
| Test and verification     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |



|                           | ## SMS compatible wallet interface                                                                                                 |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                 |
| Description               | An interface to lite wallet like functionality through an SMS gateway                                                              |
| User stories or processes | - Register phone number with project leader<br>- Confirm or deny transactions for your wallet<br>- **need to expand further**<br>- |
| Test and verification     |                                                                                                                                    |



|                           | ## Standalone key generator                                                                                  |
| ------------------------- | ------------------------------------------------------------------------------------------------------------ |
| Name                      | --                                                                                                           |
| Description               | A BIP44 compatible mnemonic generator<br>** may not be important but thinking about how to distribute tokens |
| User stories or processes |                                                                                                              |
| Test and verification     |                                                                                                              |



|                           | ## Smart Contracts Library                                                    |
| ------------------------- | ----------------------------------------------------------------------------- |
| Name                      | --                                                                            |
| Description               | Approved smart contracts which Topl will sign and allow to be run on Toplnet. |
| User stories or processes | - Escrow<br>- Profit-sharing                                                  |
| Test and verification     |                                                                               |



|                           | ## Block explorer                                                                                                           |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                          |
| Description               | A hosted web service which enumerates the entire history of the blockchain and allows for more convenient queries by users. |
| User stories or processes | - **Needs work, basically the capabilites of any block explorer**                                                           |
| Test and verification     |                                                                                                                             |



----------
# System Operations


|                           | ## Documentation                                                                                                                                                                                          |
| ------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                                                        |
| Description               | A list of resources which outlines the use of required Topl functionality                                                                                                                                 |
| User stories or processes | - External API (Loki Layer)<br>  - should include description and examples for all routes defined in Loki Layer<br>- Outline of the Topl maintained test nets. How to connect and what should be expected |
| Test and verification     |                                                                                                                                                                                                           |



|                           | ## Node management                                                                                                                                                                          |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                                          |
| Description               | Procedures and protocols related to various networks and the maintenance of nodes                                                                                                           |
| User stories or processes | - Should be able to dockerize releases<br>- Should be able to spin up a cluster of nodes quickly (either scripted or through Docker)<br>- Should be able to upgrade node from prior version |
| Test and verification     |                                                                                                                                                                                             |



|                           | ## Custodial operations                                                                                                                                                    |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | --                                                                                                                                                                         |
| Description               | Procedures and protocols related to the custodianship of tokens on behalf of investors                                                                                     |
| User stories or processes | - Should be able to maintain high level of security and transparency for how tokens are managed.<br>- Should have an efficient and transparent process for dividend payout |
| Test and verification     |                                                                                                                                                                            |




----------

