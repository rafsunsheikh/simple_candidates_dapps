<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Stargazers][stars-shield]][stars-url]
[![Forks][forks-shield]][forks-url]
[![Issues][issues-shield]][issues-url]

<br />
<div align="center">
  <h1 align="center">Build Your First dApp in Under 20 Minutes</h1>
  <p align="center">
    A beginner-friendly decentralised app: deploy a tiny election contract to a local Ethereum chain and read and update it from a plain HTML page.
    <br /><br />
    <a href="#getting-started"><strong>Get started »</strong></a>
    <br /><br />
    <a href="https://rafsunsheikh116.medium.com/new-to-blockchain-development-build-your-first-dapps-in-under-20-minutes-1f2f392d50fe">Read the Tutorial</a>
    &middot;
    <a href="https://github.com/rafsunsheikh/simple_candidates_dapps/issues">Report Bug</a>
    &middot;
    <a href="https://github.com/rafsunsheikh/simple_candidates_dapps/issues">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#how-it-works">How It Works</a></li>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#project-structure">Project Structure</a></li>
    <li><a href="#related-project">Related Project</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

This repository goes with my Medium tutorial, [New to Blockchain Development? Build Your First dApp in Under 20 Minutes][blog-url]. It is made for people who have never built a decentralised app (dApp) before.

You will:

* set up the basic blockchain tools,
* deploy a simple smart contract to a local Ethereum chain run by [Ganache][ganache-url],
* talk to that contract from a basic HTML and JavaScript page, and
* see how [web3.js][web3-url] connects a web page to the blockchain.

You only need a basic idea of what a blockchain, Ethereum and JavaScript are. The [tutorial][blog-url] walks through every step with screenshots.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### How It Works

The contract, [`contracts/Election.sol`](contracts/Election.sol), stores one value: a candidate name. It starts as `"Candidate 1"`, anyone can read it, and anyone can change it with `setCandidate`.

```solidity
contract Election {
    string public candidateName;

    function Election () public {
        candidateName = "Candidate 1";
    }

    function setCandidate (string _name) public {
        candidateName = _name;
    }
}
```

The page, [`index.html`](index.html), uses web3.js to load the contract from its ABI and address. It shows the current candidate name and has a form that calls `setCandidate` with whatever you type. If the browser does not provide its own `web3` object, the page connects straight to Ganache at `http://localhost:7545` and uses the first Ganache account.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

* [![Solidity][solidity-shield]][solidity-url]
* [![web3.js][web3-shield]][web3-url]
* [![Ganache][ganache-shield]][ganache-url]
* [![Remix][remix-shield]][remix-url]
* [![Bootstrap][bootstrap-shield]][bootstrap-url]
* [![jQuery][jquery-shield]][jquery-url]

The web3.js (0.19) and Bootstrap (3.3.7) files are included in the repo, so there is nothing to install with npm. jQuery is loaded from Google's CDN.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

Install these first:

1. [Git](https://git-scm.com/), to clone the repository.
2. [MetaMask](https://metamask.io/), a browser extension for managing Ethereum accounts.
3. [Ganache][ganache-url], a local Ethereum blockchain for testing and development.
4. [Remix IDE][remix-url], an online editor for compiling and deploying smart contracts.
5. A code editor that handles HTML, CSS and JavaScript, for example [VS Code](https://code.visualstudio.com/).

### Installation

1. **Clone the repository**
   ```sh
   git clone https://github.com/rafsunsheikh/simple_candidates_dapps.git
   cd simple_candidates_dapps
   ```
2. **Install and set up MetaMask**
   1. Add MetaMask to your browser.
   2. Store your recovery phrase somewhere safe.
   3. Add a custom network that points to Ganache, with the RPC URL `http://127.0.0.1:7545` and the chain ID that Ganache reports.
3. **Start Ganache**
   * Open Ganache on your computer to run a local Ethereum blockchain.
   * Keep the default RPC server, `http://127.0.0.1:7545`.
4. **Deploy the smart contract**
   1. Open [Remix IDE][remix-url].
   2. Create a new Solidity file and paste in the code from `contracts/Election.sol`.
   3. Compile it with a `0.4.x` compiler. The tutorial uses `0.4.2`. Newer `0.5` and later compilers will not accept this contract, because it uses the old style of constructor.
   4. Deploy it:
      * Choose **Custom - External HTTP Provider** as the environment.
      * Connect to the Ganache RPC server, `http://127.0.0.1:7545`.
   5. Copy the address of the deployed contract and its ABI.
5. **Point the page at your contract**
   1. Open `index.html` in your code editor.
   2. In the `<script>` section, replace the values that are already there with your own:
      * `var contractAbi = [...]` with your contract's ABI.
      * `var contractAddress = '...'` with your contract's address.
   3. Save the file.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

Open `index.html` in your web browser. From there you can:

* see the current candidate name, and
* type a new name and press **Add Candidate** to save it on the blockchain.

Reload the page to see the updated name.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Project Structure

```
.
├── contracts/
│   └── Election.sol      # Solidity smart contract
├── css/                  # Bootstrap 3 styles
├── fonts/                # Bootstrap icon fonts
├── js/
│   ├── bootstrap.min.js  # Bootstrap 3 scripts
│   └── web3.min.js       # web3.js library
├── index.html            # The dApp front end
└── README.md
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Related Project

Want to go further? My [Solidity Learning][solidity-learning-url] repository picks up where this one stops: Hardhat projects with tests, React front ends with ethers.js, a real estate NFT dApp, and a static audit of a live stablecoin contract.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Feel free to open an issue or a pull request to improve this project. Contributions are welcome.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a pull request

If you found this repository helpful, please give it a star and share it with others.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Rafsun Sheikh

* [Blog post][blog-url]: the full tutorial with screenshots and explanations
* [Medium][medium-url]: more articles on blockchain and technology
* [LinkedIn][linkedin-url]: connect with me for updates
* [Website][website-url]: more about my work

Project link: [https://github.com/rafsunsheikh/simple_candidates_dapps][repo-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

* Inspired by the Dapp University YouTube tutorial. Watch their [video](https://www.youtube.com/watch?v=KkZ6iYnSDRw) for more background.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/rafsunsheikh/simple_candidates_dapps.svg?style=for-the-badge
[contributors-url]: https://github.com/rafsunsheikh/simple_candidates_dapps/graphs/contributors
[stars-shield]: https://img.shields.io/github/stars/rafsunsheikh/simple_candidates_dapps.svg?style=for-the-badge
[stars-url]: https://github.com/rafsunsheikh/simple_candidates_dapps/stargazers
[forks-shield]: https://img.shields.io/github/forks/rafsunsheikh/simple_candidates_dapps.svg?style=for-the-badge
[forks-url]: https://github.com/rafsunsheikh/simple_candidates_dapps/network/members
[issues-shield]: https://img.shields.io/github/issues/rafsunsheikh/simple_candidates_dapps.svg?style=for-the-badge
[issues-url]: https://github.com/rafsunsheikh/simple_candidates_dapps/issues
[repo-url]: https://github.com/rafsunsheikh/simple_candidates_dapps
[solidity-learning-url]: https://github.com/rafsunsheikh/solidity_learning
[blog-url]: https://rafsunsheikh116.medium.com/new-to-blockchain-development-build-your-first-dapps-in-under-20-minutes-1f2f392d50fe
[medium-url]: https://medium.com/@rafsunsheikh116
[linkedin-url]: https://www.linkedin.com/in/mdrafsunsheikh/
[website-url]: https://rafsunsheikh.github.io
[solidity-shield]: https://img.shields.io/badge/Solidity%200.4-363636?style=for-the-badge&logo=solidity&logoColor=white
[solidity-url]: https://soliditylang.org/
[web3-shield]: https://img.shields.io/badge/web3.js-F16822?style=for-the-badge&logo=web3dotjs&logoColor=white
[web3-url]: https://web3js.readthedocs.io/
[ganache-shield]: https://img.shields.io/badge/Ganache-E4A663?style=for-the-badge&logo=truffle&logoColor=white
[ganache-url]: https://trufflesuite.com/ganache/
[remix-shield]: https://img.shields.io/badge/Remix%20IDE-222222?style=for-the-badge&logo=ethereum&logoColor=white
[remix-url]: https://remix.ethereum.org/
[bootstrap-shield]: https://img.shields.io/badge/Bootstrap%203-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white
[bootstrap-url]: https://getbootstrap.com/docs/3.3/
[jquery-shield]: https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white
[jquery-url]: https://jquery.com/
