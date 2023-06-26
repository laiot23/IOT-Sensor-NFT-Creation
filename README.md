# Contents
- [Repo Description](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#simple-candy-machine-walkthrough)
- [Setup on Mac](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#to-run-demo-locally-as-is-mac)
- [Setup on Windows](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#to-run-locally-as-is-windows)
- [Creating a CandyMachine](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#creating-a-candymachine)
- [Customize your UI](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#setup-your-own-cmui)
- [*GTFO localhost](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#ship-it-on-vercel)

# Simple Candy Machine Walkthrough
This project will show you how to clone a repo, setup your local development environment, create a candymachine, create a minting user interface, and setting up an rpc. <b>Do this with devnet first!</b> Start by cloning this repo and demoing as-is, I've included a devnet candymachine so the UI loads correctly.

This `demo` branch contains a `.env` file where the `main` branch shows an `.env.template` If you're using this branch, you'll need to modify the `.env` file with your candymachine ID. If you're using the `main` branch, you'll need to change the file name to `.env`

## To run demo locally AS-IS (MAC)

### First
Clone the repository to your machine. [not sure how?](https://github.com/ilovespectra/repo-demo)
### Second
1. Install Node.js:
Both http-server and ngrok require Node.js to be installed on your system. If you don't have Node.js installed, you can download and install it from the [official website](https://nodejs.org)

Follow the instructions specific to your operating system to complete the installation.

2. Install http-server:
Once Node.js is installed, open your terminal and run the following command to install http-server globally:
```
npm install -g http-server
```
This command will use npm (Node Package Manager) to download and install http-server globally on your system.

3. Verify http-server installation:
To verify that http-server is installed correctly, run the following command:
```
http-server --version
```
If installed successfully, it should display the version number of http-server.

4. Install ngrok:
Next, you'll install ngrok which provides secure tunnels to localhost for exposing local servers. Run the following command in your terminal to download the ngrok binary:
```
curl -O https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
```
This command will download a compressed .zip file containing the ngrok binary.

5. Unzip and move ngrok:
After the download is complete, unzip the ngrok binary and move it to a directory that is included in your system's PATH. Run the following commands in your terminal:
```
unzip ngrok-stable-linux-amd64.zip
sudo mv ngrok /usr/local/bin/
```
These commands will unzip the downloaded file and move the ngrok binary to /usr/local/bin/, making it accessible system-wide.

6. Verify ngrok installation:
To verify that ngrok is installed correctly, run the following command:
```
ngrok version
```
If installed successfully, it should display the version number of ngrok.
### Third
Depending whether you're using npm or yarn, run either:
```
npm install
```
or 
```
yarn
```
Then:
```
npm run dev
```
or 
```
yarn dev
```
Open a new terminal and run:
```
npx ngrock http 3000
```
Open this link in your browser:
![ngrok](https://media.discordapp.net/attachments/1051281685234327613/1122877527329886418/image.png?width=1864&height=500)
<br><br>
You will need 1 devnet SOL to mint, plus around .023SOL for transaction fees. If you don't have devnet SOL, scroll down to [Creating a CandyMachine](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#creating-a-candymachine) and follow the steps to install Rust/Solana-CLI. Once the Solana CLI has been installed, copy your wallet public address ('pubkey'), open a command terminal window and run:
```
solana config set --url devnet
```
```
solana airdrop 2 <PASTE_YOUR_PUBKEY>
```
Now you can mint from the UI and see the confirmation modal pop-up.

## To run locally AS-IS (WINDOWS)
### First
Clone the repository to your machine. [not sure how?](https://github.com/ilovespectra/repo-demo)
### Second
1. Install Node.js:
Both http-server and ngrok require Node.js to be installed on your system. You can download the Windows installer for Node.js from the official website: https://nodejs.org

Download the appropriate installer for your Windows version and follow the installation instructions.

2. Install http-server:
Once Node.js is installed, open Command Prompt or PowerShell and run the following command to install http-server globally:
```
npm install -g http-server
```
This command will use npm (Node Package Manager) to download and install http-server globally on your system.

3. Verify http-server installation:
To verify that http-server is installed correctly, run the following command:
```
http-server --version
```
If installed successfully, it should display the version number of http-server.

4. Install ngrok:
Next, you'll install ngrok which provides secure tunnels to localhost for exposing local servers. Follow these steps to install ngrok on Windows:

Visit the ngrok website: https://ngrok.com
Sign up for a free account and download the Windows version of ngrok.
Extract the downloaded ngrok ZIP file to a convenient location on your computer.
5. Add ngrok to PATH:
To use ngrok from anywhere in the command prompt, you need to add its location to the system's PATH variable:

Open the Start menu and search for "environment variables."
Click on "Edit the system environment variables."
In the System Properties window, click on the "Environment Variables" button.
In the "System variables" section, find the "Path" variable and click on "Edit."
Click on "New" and enter the path to the directory where you extracted ngrok (e.g., C:\path\to\ngrok).
Click "OK" to save the changes.
6. Verify ngrok installation:
To verify that ngrok is installed correctly, open Command Prompt or PowerShell and run the following command:
```
ngrok version
```
If installed successfully, it should display the version number of ngrok.
### Third
Depending whether you're using npm or yarn, run either:
```
npm install
```
or 
```
yarn
```
Then:
```
npm run dev
```
or 
```
yarn dev
```
Open a new terminal and run:
```
npx ngrock http 3000
```
Open this link in your browser:
![ngrok](https://media.discordapp.net/attachments/1051281685234327613/1122877527329886418/image.png?width=1864&height=500)
<br><br>
You will need 1 devnet SOL to mint, plus around .023SOL for transaction fees. If you don't have devnet SOL, scroll down to [Creating a CandyMachine](https://github.com/ilovespectra/pnfts-mint/edit/demo/README.md#creating-a-candymachine) and follow the steps to install Rust/Solana-CLI. Once the Solana CLI has been installed, copy your wallet public address ('pubkey'), open a command terminal window and run:
```
solana config set --url devnet
```
```
solana airdrop 2 <PASTE_YOUR_PUBKEY>
```
Now you can mint from the UI and see the confirmation modal pop-up.

# Creating a Candymachine 

## Rust / Solana / Sugar

1. Install Rust:
The Solana CLI is built with Rust, so you'll need to install it first. To install Rust, open your terminal and run the following command:
```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Follow the prompts in the terminal and agree to the installation. Rustup, the Rust version manager, will be installed along with the latest stable version of Rust.

2. Add Rust to PATH:
After the Rust installation is complete, you'll need to add it to your system's PATH variable. Open a new terminal window or run the following command to apply the changes immediately:
```
source $HOME/.cargo/env
```
3. Install Solana CLI:
Now that Rust is installed, you can proceed to install the Solana CLI. Run the following command in your terminal:
```
sh -c "$(curl -sSfL https://release.solana.com/v1.9.7/install)"
```
This command will download the Solana CLI installer script and execute it.

4. Verify Solana CLI installation:
To verify that the Solana CLI is installed correctly, run the following command:
```
solana --version
```
If installed successfully, it should display the version number of the Solana CLI.

5. Install Sugar CLI:
Sugar is a command-line tool that makes it easier to interact with Solana programs and accounts. To install Sugar, run the following command:
```
cargo install sugar-sdk
```
This command will use Cargo (Rust's package manager) to download and install the Sugar CLI.

6. Verify Sugar CLI installation:
To verify that Sugar CLI is installed correctly, run the following command:
```
sugar --version
```
If installed successfully, it should display the version number of the Sugar CLI.

## Candymachine

Create a new folder in your workspace named `assets`.
<br><br>

Create a file in the `assets` directory named `0.json` and paste the following contents:
```
{
    "name": "test",
    "symbol": "DEMO",
    "description": "This is demo metadata for demo NFT collection for devnet.",
    "image": "0.png",
    "attributes": [
        {
            "trait_type": "Type",
            "value": "Demo"
        }
    ],
    "properties": {
        "files": [
            {
                "uri": "0.png",
                "type": "image/png"
            }
        ]
    }
}
```
Create another file in the assets folder named `collection.json` and paste the following contents:
```
{
    "name": "tests",
    "symbol": "DEMO",
    "description": "This is a demo collection for devnet UI testing.",
    "image": "collection.png",
    "attributes": [],
    "properties": {
      "files": [
        {
          "uri": "collection.png",
          "type": "image/png"
        }
      ]
    }
  }
```
Modify the metadata for your collection, and an image for your nft to your assets folder called `0.png`, repeating the process for each nft in your collection.<br><br>
Add an image for your collection called `collection.png`.
<br><br>
Run the following commands in this order:
```
solana config set --url devet
```
```
solana airdrop 2
```
```
sugar config create
```
```
sugar upload
```
```
sugar launch
```
At this stage, you'll have a `config.json` where you will be required to add your guards, at least one is required. It should look something like this:
```
  "guards": {
    "default": {
      "solPayment" : {
        "value": 1,
        "destination": "YOUR_PUBKEY"
      }
    }
  }
}
```
```
sugar guard add
```
Copy and paste your Candymachine ID into your `.env` file.

To setup a Candy Machine:

- Create your Candy Machine using [Sugar](https://docs.metaplex.com/programs/candy-machine/how-to-guides/my-first-candy-machine-part1) (now supports pNFTs)
- Change token standard to pNFT: `sugar config set -t pnft`
- Make sure you have setup your [Candy Guard](https://docs.metaplex.com/programs/candy-machine/how-to-guides/my-first-candy-machine-part1#candy-guards---further-configuration). _This is a necessary step._

After these, you can use this UI to mint pNFTs.

## Candy Guards supported

- [Start date](https://docs.metaplex.com/programs/candy-machine/available-guards/start-date)
- [Sol Payment](https://docs.metaplex.com/programs/candy-machine/available-guards/sol-payment)
- [Allow List](https://docs.metaplex.com/programs/candy-machine/available-guards/allow-list)
  - Grab your Merkle Root from [here](https://tools.key-strokes.com/merkle-root)
  - Add the Merkle Root to your Sugar config.json:
    ```
        "allowList": {
            "merkleRoot": "e889dfa8fbfb6016378348ca395f243c55a0768647c2ca58e5febffa17e02d60"
        },
    ```
  - Add your allow list wallets to the `allowlist.json` file
- [Mint Limit](https://docs.metaplex.com/programs/candy-machine/available-guards/mint-limit)
- [Token Burn](https://docs.metaplex.com/programs/candy-machine/available-guards/token-burn)

## develop locally

- `yarn`

- Copy and fill the contents from the `.env.template` file into a `.env` file.

- `yarn dev`

## deploy

You can deploy to any provider but make sure you add the `NEXT_PUBLIC_CANDY_MACHINE_ID` environment variable. (_Try [Vercel](https://vercel.com/new)_)

## contribute

You can build guards, or improve the UI, and your PR will be happily reviewed & merged.

Also, I'm accepting tips in SOL to keep improving this open-source project: 52zEuaG5VBQTzRP7MLMyEzSuKgYPF9E9dtaWrmXaiNkg

# Setup your own cmui

You'll need to modify a few things to make this work for your own candymachine on mainnet. <b>Be careful tho, there's no edit undo</b>.<br><br>
Start by changing your `example.env` to `.env`. <b>Proceed with Caution!</b><br><br> 
Head over to [Quicknode](https://www.quicknode.com/) and get setup with a free account. 

Create an endpoint<br><br>
![rpc-start](https://media.discordapp.net/attachments/1051281685234327613/1120493098221457509/rpc-start.png?width=884&height=330)
<br><br>
Select Solana<br><br>
![rpc-solana](https://media.discordapp.net/attachments/1051281685234327613/1120493098590552145/rpc-solana.png?width=600&height=330)
<br><br>
Select mainnet-beta <b>Proceed with caution</b><br><br>
![rpc-mainnet](https://media.discordapp.net/attachments/1051281685234327613/1120493098909306950/rpc-mainnet.png)
<br><br>
Create your endpoint<br><br>
![rpc-create](https://media.discordapp.net/attachments/1051281685234327613/1120493099160981604/rpc-create.png?width=540&height=330)
<br><br>
Select your RPC<br><br>
![rpc-yours](https://media.discordapp.net/attachments/1051281685234327613/1120495297659936768/rpc-yours.png)
<br><br>
Copy the address<br><br>
![rpc-copy](https://media.discordapp.net/attachments/1051281685234327613/1120495297353756682/rpc-copy.png?width=768&height=330)
<br><br>
Navigate to `/components/WalletProvider.tsx` and paste your RPC endpoint url in your `const endpoint` where the curser lies in the screenshot below.<br><br>
![rpc-paste2](https://media.discordapp.net/attachments/1051281685234327613/1120498024444071966/rpc-paste2.png?width=932&height=248)
<br><br>
<b>Update your `favicon.ico`</b><br><br>
Use [remove.bg](https://remove.bg) to create a PNG of your logo, download and rename the file to `favicon.ico`. Delete the existing `favicon.ico` in the `/public/` folder (the default vercel image), and add your file.

# Ship it on Vercel

Head over to [Vercel.com](https://vercel.com) and link your Github.<br><br>
Add New Project<br><br>
![add new project](https://media.discordapp.net/attachments/1051281685234327613/1121085093641998336/image.png)<br><br>
Select this repo<br><br>
