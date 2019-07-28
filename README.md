What are you planning to build?
A block chain based e-voting solution, meeting all the challenges being faced by today’s voting systems paper ballot or Electronic Voting Machine-EVM.  The challenges like transparency of whole process starting from casting vote to declaration of result-the complete audit trail available publicly, no physical machine/space is needed, no requirement of centralized agency –zero manual touch, no constraint of casting vote only from home town, fool proof security, no capturing of pooling both, single time voting, maintain anonymity of the voter, no mistake in counting, no error in voting candidate other than a choice, no restriction on supporting number of candidates in the poll fray etc.


How does it work?
The e-voting system will be working on “Block Chain Mining” using a permissioned block chain, sort of a variation of the consortium-based chains, which uses the proof-of-authority (POA) consensus algorithm. In proof-of-authority based networks, transactions and blocks are validated by approved accounts, known as validators, here in our system it shall be election commission administrator. The process of validation shall be automated and would not require the election administrator to monitor it. 

In order to reduce to reduce gas consumption and the number of transactions on the block chain, it uses “eth.calls”, which allows nodes to send messages to other nodes or smart contracts to retrieve its current state without storing the message on the block chain and thus reduces the size of the block chain and gas consumption.

The implementation will consists of three smart contracts, coded in Ethereum’s Solidity language, two scripts written in JavaScript, and one HTML page described in the paras below

Roles description – (a) Administrator is responsible for deploying the initial Registrar and Creator smart contracts, to grant or revoke ballot creation permission for registered voters/creators. (b) Voter registers in our system with a valid student ID and e-mail address to vote on given ballot ID numbers (c) Creator is a voter with ballot creation permission.

Front/back-end pages (a) VoteUI.html page is the user interface, allowing users to enter necessary information, on submission of necessary information, the corresponding click buttons will invoke functions in App.js.  (b) App.js -gathers information from VoteUI.html and interacts with Crypto.js and the Ethereum Blockchain. For each corresponding request from VoteUI.html, it utilizes eth.calls, Crypto.js server calls, and Ethereum transactions to verify, encrypt/decrypt votes, and store ballot/vote information. (c) Crypto.js acts as a cryptographic server. All votes are encrypted, homomorphically added, and decrypted using the Paillier homomorphic encryption system key pair in this server.

Smart contracts (a) Registrar.sol -It keeps track of all registered voters and creators, ballot IDs, voting contract addresses, and whitelisted e-mail domains. This allows the contract to perform voter veriﬁcation, permission modiﬁcation, and Voting.sol address retrieval. The owner of this contract is the administrator (b) Creator.sol acts as a spawner for different Voting.sol contracts. The Creator deﬁnes the voting contract’s details when ﬁlling out the required information in VoteUI.html. The owner of this contract is the administrator (c) Voting.sol acts as a virtual ballot and regulates the voting on the ballot. Another set of voter veriﬁcation, that includes vote attempts and ballot time limit, is also conducted in this contract. The owner of this contract is the contract’s creator.
The sequence shall be initial setup, register vote, create ballot, load ballot, vote and get votes.


How users can get started with the project?
All the stake holders the administrator, creators, and voters need to have the MetaMask plugin downloaded in their Chrome browser  which allows all stake holders to manage their Ethereum wallet and interact with decentralized applications and smart contracts without running a full node and thus resolving the issue of scaling of the block chain.  Also Ethereum’s Web3 framework is used, internally, to allow the users to easily manage signed transactions and interactions with the Ethereum block chain. 

Using MetaMask and Web3 eliminates the need for users to download full or even partial Ethereum blockchains on their local machines in order to broadcast transactions. The only action required of users when registering, voting, or creating ballots is to use their passwords to unlock their Ethereum accounts in the MetaMask plugin and securely interact with the block chain. 

MetaMask cannot impersonate the user and send transactions on the user’s behalf. Acting as an intermediary between Chrome and the Ethereum blockchain, as transactions are signed using the sender’s private key, which is stored locally on the user’s machine.


What data set(s) are you using?
Some fictitious data set, say election of the president, secretary in BITS Pilani.


What technologies are you using?
•	A permissioned public, shared block chain is a form of hybrid (private and public) system that facilitates whitelisted access of the block chain and at the same time all the transactions are viewable by the public. Thus allowing the casting of votes quickly with prominent levels of trust and finally provides real-time publicly verifiable casting of votes by all engaged parties/key players in the voting ecosystem (voters, election administrators etc)

•	Smart contracts written in Solidity, running on an open source block chain platform “Ethereum Virtual Machine (EVM)”, which guarantees to bind parties and voters to an immutable agreement over the Internet.

•	Non-Interactive Zero-knowledge-proof- Crypto methods like homomorphic encryption, bind signature, linkable ring signature etc. to have a secure method to authenticate and verify eligible voters while guaranteeing their privacy.

•	Homomorphic encryptions- Allow complex mathematical operations to be performed on encrypted data without compromising the encryption. In mathematics, homomorphic describes the transformation of one data set into another while preserving relationships between elements in both sets, whether they are performed on encrypted or decrypted data --  will yield equivalent results. . In voting system, this allows to count encrypted ballots by any third party without leaking any information in the ballot. The known homographic encryption, can be used in voting, are ELGamal and Paillier.

•	Blind Cryptographic Signature-It allows a person to get a message signed by another party without revealing any information about the message to the other party. In voting system, employing blind signature, ensures the tallying authority that ballot is from a valid voter while not revealing about the voter’s selection.

•	Linkable Ring Signatures wherein a group of people can put cryptographic signature on a message such that resulting signature does not reveal their identity (anonymity), but the same time, allows anyone to determine whether the signatures have been carried out / issued by the same group member (likability). In voting system the authority uses the likability tag to identify that the voter has already voted.

•	 Multi-Party Signature Scheme shall enable voters’ authentication and authorization and societies, governments and organizations can build a election systems and processes.
