# NFT Pulse

## Table of Contents
- [Overview](#overview)
- [System Components](#system-components)
  - [Part 1: Tlink Generation Website](#part-1-tlink-generation-website)
  - [Part 2: TokenScript](#part-2-tokenscript)
- [Tlink Generation Process](#tlink-generation-process)
- [ERC-7738 Integration](#erc-7738-integration)
- [TokenScript Structure](#tokenscript-structure)
- [Installation and Setup](#installation-and-setup)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

NFT Pulse is a two-part system designed to enhance NFT engagement through the generation of Tlinks (TokenScript links) and the use of TokenScript technology. This system allows for easy sharing and viewing of NFTs across different platforms, particularly on Twitter.

## System Components

### Part 1: Tlink Generation Website 
Demo: https://claude.site/artifacts/f8d148a3-1990-4746-96c5-452ea586fe67

This is a web application that allows users to:
1. Connect their wallet
2. Choose an NFT from their collection
3. Generate a Tlink for the selected NFT

Key Features:
- Wallet connection
- NFT selection interface
- Tlink generation
- Integration with ERC-7738 contract for TokenScript registration

### Part 2: TokenScript
TLink: https://x.com/Victor928/status/1845018599141814423

TokenScript is an XML-based markup language that describes the functions of the token and methods to interact with it. It's used to create rich, interactive experiences for NFTs.

Key Features:
- Defines token attributes and behaviors
- Specifies user interface elements
- Integrates with smart contract functions

## Tlink Generation Process

1. User connects their wallet to the website
2. User selects an NFT from their collection
3. The system checks if a TokenScript is registered for the NFT in the ERC-7738 contract
4. If registered, the system generates a Tlink using the existing TokenScript
5. If not registered:
   - The system generates a new TokenScript for the NFT
   - Registers the TokenScript with the ERC-7738 contract
   - Generates a Tlink using the new TokenScript
6. The Tlink is presented to the user for sharing

## ERC-7738 Integration

ERC-7738 is used for permissionless script registry. The system interacts with the ERC-7738 contract to:
- Check if a TokenScript is registered for an NFT
- Register new TokenScripts for NFTs

Contract Address: 0x0077380bCDb2717C9640e892B9d5Ee02Bb5e0682 (universal across EVM chains)

## TokenScript Structure

A basic TokenScript includes:
- Token information (name, contract address, etc.)
- Attribute definitions
- Card layouts for user interface
- Action definitions (e.g., transfer, vote)

Example structure:
```xml
<ts:token xmlns:ts="http://tokenscript.org/2020/06/tokenscript">
  <ts:label>
    <ts:string xml:lang="en">My NFT</ts:string>
  </ts:label>
  <ts:contract interface="erc721" name="MyNFTContract">
    <ts:address network="1">0x...</ts:address>
  </ts:contract>
  <!-- More elements... -->
</ts:token>
```

## Installation and Setup

(Note: Expand this section with specific instructions as the project develops)

1. Clone the repository:
   ```
   git clone https://github.com/your-organization/nft-pulse.git
   ```

2. Install dependencies:
   ```
   cd nft-pulse
   npm install
   ```

3. Set up environment variables (details to be provided)

4. Run the development server:
   ```
   npm run dev
   ```

## Usage

1. Connect your wallet to the NFT Pulse website
2. Select an NFT from your collection
3. Click "Generate Tlink"
4. Share the generated Tlink on Twitter or other platforms

The Tlink will look like:
https://viewer.tokenscript.org/?chain=17000&contract=0xB8686Db491911561ee26bA80495f863cd7932de8&tokenId=8

When shared on Twitter, this link will render the TokenScript, providing an interactive NFT experience in the tweet feed.

## Contributing

We welcome contributions to NFT Pulse! Please read our [Contributing Guide](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

For more information or support, please contact our team at support@nftpulse.com
