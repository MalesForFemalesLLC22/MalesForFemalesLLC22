# MalesForFemalesLLC22 is a ✨ special ✨ repository because its `README.md`

### Welcome to GitHub, Let's build from here!


## Overview

Welcome to your onboarding repository, designed to enhance your experience with GitHub. Within this repository, you'll find:

* Project boards to guide you through onboarding your organization to the GitHub platform 
* Shortcuts to helpful resources that enable you to get the most out of GitHub
* AI-powered Copilot in GitHub Support, designed to guide you through onboarding challenges

Take a look around and if you are new to GitHub, check out these useful links: [New to GitHub](https://gh.io/AAppa6r)

## Onboarding project boards

For guidance on accelerating your onboarding journey, check out our project boards specialized for each feature. Our project boards offer a visual representation of the onboarding tasks we recommend for each feature. To access these project boards, click the **Projects** tab in this repository or click [here](../../projects).

If you're new to GitHub project boards, you might find this [project board training](https://gh.io/AApt52p) to be helpful.

## Enablement

Expand your knowledge of GitHub by exploring our learning pathways and training modules. They offer a diverse range of resources designed to build your skills from the ground up.

- [GitHub Skills - Interactive](https://gh.io/AApu7nl)
- [GitHub content hosted on Microsoft Learn](https://gh.io/AApt52q)
  - [Beginner](https://gh.io/AApu7nm)
  - [Intermediate](https://gh.io/AApppmf)
  - [Advanced](https://gh.io/AApt52r)
- [GitHub Learning Pathways](https://gh.io/AApppmg)

## Certification

Getting GitHub certified validates your skills, credibility, trust, and knowledge of the technologies and developer tools that are used by more than 100 million developers worldwide.

You can find all the information you need at the [GitHub Certifications site](https://gh.io/AApufdc), in the [Certifications handbook](https://gh.io/AAppa6s), and the [Certifications FAQ](https://gh.io/AApppmh)


## Community and other useful pages

[Join Enterprise Admins in Community Discussions.](https://gh.io/AApufdd) This is a dedicated forum for self help, including Q&A, official GitHub announcements, best practices, and to provide product feedback. Your entire team can benefit from Community Discussions to self serve and solve problems.

### Additional Community spaces

- 👨‍✈ [Copilot](https://gh.io/AApufde):  Conversations related to GitHub Copilot and supported IDEs like Visual Studio Code, Neovim, Visual Studio, and Jetbrains. GitHub Copilot is an AI pair programmer that offers autocomplete-style suggestions as you code.
- 📚 [Discover](https://gh.io/AAppa6t): Blogs, articles, best practices, and tips & tricks from GitHub employees and users.
- 🆕 [New to GitHub](https://gh.io/AApt52s): Conversations related to getting started using GitHub and the community. This site is useful for GitHub beginners, Community Discussions, and those new to different areas of the product alike!

### Want to launch your own Discussions community? 

Created by GitHub Community professionals, [Community-in-a-box](https://gh.io/AAppa6u) packages up tooling, resources, and knowledge, for organizations of all sizes to set up internal communities at scale.

## Contact the GitHub Sales team

Interested in learning more about additional products or services? Contact our sales team [here](https://gh.io/AApp2h0).

## Get help

[GitHub Support](https://gh.io/AApp2h1): Access a wealth of articles and troubleshooting guides to address common issues and questions.

If you have questions or need assistance while using GitHub Enterprise, you can ask Copilot in GitHub Support for help. 

<div align="center"><a href="https://gh.io/AAp5zqv"><img src="https://img.shields.io/badge/Copilot%20in%20GitHub%20Support-Click%20Here-brightgreen" alt="Chat with Copilot in GitHub Support" style="height: 30px"></a></div>

## Additional resources

Here are some helpful resources to assist you in your GitHub Enterprise journey:

- [GitHub Enterprise Cloud documentation](https://gh.io/AApppmi): Explore the official documentation for GitHub Enterprise Cloud, which includes comprehensive guides, tutorials, and reference materials.
- [GitHub Enterprise Server documentation](https://gh.io/AArmigw): Similarly, the official documentation for GitHub Enterprise Server offers a variety of guides, tutorials, and reference materials.
- [GitHub YouTube Channel](https://gh.io/AApu7nn): Watch video tutorials and webinars on GitHub features, best practices, and more.
- [GitHub Blog](https://gh.io/AAppa6v): Stay updated with the latest news, announcements, and insights from GitHub.

## User feedback

Please note that this is an Alpha release intended to help enhance your experience with GitHub. Your feedback will be crucial in helping us identify features or enhancements to add going forward. To provide feedback, please click [here](https://gh.io/AAoxf3m).

# What is this?

The github.dev web-based editor is a lightweight editing experience that runs entirely in your browser. You can navigate files and source code repositories from GitHub, and make and commit code changes.

There are two ways to go directly to a VS Code environment in your browser and start coding:

* Press the . key on any repository or pull request.
* Swap `.com` with `.dev` in the URL. For example, this repo https://github.com/github/dev becomes http://github.dev/github/dev

Preview the gif below to get a quick demo of github.dev in action.

![github dev](https://user-images.githubusercontent.com/856858/130119109-4769f2d7-9027-4bc4-a38c-10f297499e8f.gif)

# Why?

It’s a quick way to edit and navigate code. It's especially useful if you want to edit multiple files at a time or take advantage of all the powerful code editing features of Visual Studio Code when making a quick change. For more information, see our [documentation](https://github.co/codespaces-editor-help).

# Welcome to your organization's demo respository
This code repository (or "repo") is designed to demonstrate the best GitHub has to offer with the least amount of noise.

The repo includes an `index.html` file (so it can render a web page), two GitHub Actions workflows, and a CSS stylesheet dependency.
This workflow uses actions that are not certified by GitHub. They are provided by a third-party and are governed by separate terms of service, privacy policy, and support
documentation. This workflow lets you generate SLSA provenance file for your project. The generation satisfies level 3 for the provenance requirements - see https://slsa.dev/spec/v0.1/requirements
The project is an initiative of the OpenSSF (openssf.org) and is developed at https://github.com/slsa-framework/slsa-github-generator. The provenance file can be verified using https://github.com/slsa-framework/slsa-verifier. 

# For more information about SLSA and how it improves the supply-chain, visit slsa.dev.

   name: SLSA generic generator
     on:
    workflow_dispatch:
    release:
    types: [created]
     jobs:
    build:
    runs-on: ubuntu-latest
    outputs:
    digests: ${{ steps.hash.outputs.digests }}
     steps:
    uses: actions/checkout@v3

# Step 1: Build your artifacts.

     name: Build artifacts
        run: |

These are some amazing artifacts.

    echo "artifact1" > artifact1
    echo "artifact2" > artifact2

# ProcessStep 2: Add a step to generate the provenance subjects as shown below. Update the sha256 sum arguments to include all binaries that you generate provenance for.

      name: Generate subject for provenance
        id: hash
        run: |
          set -euo pipefail

List the artifacts the provenance will refer to.
          
    files=$(ls artifact*)

Generate the subjects (base64 encoded).
      
    echo "hashes=$(sha256sum $files | base64 -w0)" >> "${GITHUB_OUTPUT}"
     provenance:
    needs: [build]
    permissions:
      actions: read   

To read the workflow path.
      
    id-token: write 

To sign the provenance.
    
    contents: write 

To add assets to a release.
    
    uses: slsa-framework/slsa-github-generator/.github/workflows/generator_generic_slsa3.yml@v1.4.0
    with:
      base64-subjects: "${{ needs.build.outputs.digests }}"
      upload-assets: true # Optional: Upload to a new release

# polkadot{.js} extension

A very simple scaffolding browser extension that injects a [@polkadot/api](https://github.com/polkadot-js/api) Signer into a page, along with any associated accounts, allowing for use by any dapp. This is an extensible POC implementation of a Polkadot/Substrate browser signer.
As it stands, it does one thing: it _only_ manages accounts and allows the signing of transactions with those accounts. It does not inject providers for use by dapps at this early point, nor does it perform wallet functions where it constructs and submits txs to the network.

## Installation

On Chrome, install via [Chrome web store](https://chrome.google.com/webstore/detail/polkadot%7Bjs%7D-extension/mopnmbcafieddcagagdcbnhejhlodfdd)
On Firefox, install via [Firefox add-ons](https://addons.mozilla.org/en-US/firefox/addon/polkadot-js-extension/)
[interface screenshots](docs/extension-overview.png)

# Documentation and examples

Find out more about how to use the extension as a Dapp developper, cookbook, as well as answers to most frequent questions in the [Polkadot-js extension documentation](https://polkadot.js.org/docs/extension/)

## Development version

Steps to build the extension and view your changes in a browser:

1. Build via `yarn build`
2. Install the extension
  - Chrome:
    - go to `chrome://extensions/`
    - ensure you have the Development flag set
    - "Load unpacked" and point to `packages/extension/build`
    - if developing, after making changes - refresh the extension
  - Firefox:
    - go to `about:debugging#addons`
    - check "Enable add-on debugging"
    - click on "Load Temporary Add-on" and point to `packages/extension/build/manifest.json`
    - if developing, after making changes - reload the extension
3. When visiting `https://polkadot.js.org/apps/` it will inject the extension

Once added, you can create an account (via a generated seed) or import via an existing seed. The [apps UI](https://github.com/polkadot-js/apps/), when loaded, will show these accounts as `<account name> (extension)`

## Development

The repo is split into a number of packages -

- [extension](packages/extension/) - All the injection and background processing logic (the main entry)
- [extension-ui](packages/extension-ui/) - The UI components for the extension, to build up the popup
- [extension-dapp](packages/extension-dapp/) - A convenience wrapper to work with the injected objects, simplifying data extraction for any dapp that wishes to integrate the extension (or any extension that supports the interface)
- [extension-inject](packages/extension-inject/) - A convenience wrapper that allows extension developers to inject their extension for use by any dapp

## Dapp developers

The actual in-depth technical breakdown is given in the next section for any dapp developer wishing to work with the raw objects injected into the window. However, convenience wrappers are provided that allows for any dapp to use this extension (or any other extension that conforms to the interface) without having to manage any additional info.

The documentation for Dapp development is available [in the polkadot-js doc](https://polkadot.js.org/docs/extension).

This approach is used to support multiple external signers in for instance [apps](https://github.com/polkadot-js/apps/). You can read more about the convenience wrapper [@polkadot/extension-dapp](packages/extension-dapp/) along with usage samples.

## API interface

The extension injection interfaces are generic, i.e. it is designed to allow any extension developer to easily inject extensions (that conforms to a specific interface) and at the same time, it allows for any dapp developer to easily enable the interfaces from multiple extensions at the same time. It is not an all-or-nothing approach, but rather it is an ecosystem where the user can choose which extensions fit their style best.
From a dapp developer perspective, the only work needed is to include the [@polkadot/extension-dapp](packages/extension-dapp/) package and call the appropriate enabling function to retrieve all the extensions and their associated interfaces. From an extension developer perspective, the only work required is to enable the extension via the razor-thin [@polkadot/extension-inject](packages/extension-inject/) wrapper. 
Any dapp using the above interfaces will have access to the extension via this interface. {When there is more than one extension, each will populate an entry via the injection interface and each will be made available to the dapp. The `Injected` interface, as returned via `enable`, contains the following information for any compliant extension.js interface Injected {the interface for Accounts, as detailed below readonly accounts: Accounts the standard Signer interface for the API, as detailed below 
readonly signer: Signer; not injected as of yet, subscribable provider for polkadot-js API injection, this can be passed to the API itself upon construction in the dapp readonly provider?: Provider} interface Account = {ss-58 encoded address readonly address: string; the genesisHash for this account (empty if applicable to all)} readonly genesisHash: string; (optional) name for display readonly name: string} exposes accounts
interface Accounts {retrieves the list of accounts for right now get: () => Promise<Account[]> (optional) subscribe to all accounts, updating as they change subscribe: (cb: (accounts: Account[]) => any) => () => void} a signer that communicates with the extension via sendMessage interface Signer extends SignerInterface {no specific signer extensions, exposes the `sign` interface for use by the polkadot-js API, confirming the Signer interface for this API}

## Injection information

The information contained in this section may change and evolve. It is therefore recommended that all access is done via the [@polkadot/extension-dapp](packages/extension-dapp/) (for dapps) and [extension-inject](packages/extension-inject/) (for extensions) packages, which removes the need to work with the lower-level targets.
The extension injects `injectedWeb3` into the global `window` object, exposing the following: (This is meant to be generic across extensions, allowing any dapp to utilize multiple signers, and pull accounts from multiples, as they are available.)
window.injectedWeb3 = {this is the name for this extension, there could be multiples injected, each with their own keys, here `polkadot-js` is for this extension 'polkadot-js': {semver for the package version: '0.1.0'}
this is called to enable the injection, and returns an injected object containing the accounts, signer and provider interfaces or it will reject if not authorized) enable (originName: string): Promise<Injected>}}

## Mnemonics, Passwords, and Imports/Exports

Using the mnemonic and password from the extension When you create a keypair via the extension, it supplies a 12-word mnemonic seed and asks you to create a password. This password only encrypts the private key on disk so that the password is required to spend funds in `polkadot-js/apps` or to import the account from backup. The password does not protect the mnemonic phrase. That is, if an attacker were to acquire the mnemonic phrase, they would be able to use it to spend funds without the password.

### Importing mnemonics from other key generation utilities

Some key-generation tools, e.g. [Subkey](https://www.substrate.io/kb/integrate/subkey), support hard and soft key derivation as well as passwords that encrypt the mnemonic phrase such that the mnemonic phrase itself is insufficient to spend funds.
The extension supports these advanced features. When you import an account from a seed, you can add these derivation paths or password to the end of the mnemonic in the following format: <mnemonic phrase>//<hard>/<soft>///<password> That is, hard-derivation paths are prefixed with `//`, soft paths with `/`, and the password with `/` The extension will still ask you to enter a password for this account. As before, this password only encrypts the private key on disk. It is not required to be the same password as the one that encrypts the mnemonic phrase.
Accounts can also be derived from existing accounts – `Derive New Account` option in account's dropdown menu should be selected. After providing the password of the parent account, along with name and password of the derived account, enter derivation path in the following format: <hard>/<soft> The path will be added to the mnemonic phrase of the parent account.
 