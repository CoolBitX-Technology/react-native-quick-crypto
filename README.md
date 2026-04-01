npm module: https://www.npmjs.com/package/@coolwallet-app/react-native-quick-crypto

# Install bun

```bash
brew install oven-sh/bun/bun@1.2.0
bun --version
```

## Troubleshooting

### `brew install oven-sh/bun/bun@1.2.0` fails at `brew link`

If Homebrew reports that `bun@1.2.0` is installed but cannot be symlinked because files belong to `bun@1.1.26`, run:

```bash
brew unlink bun@1.1.26
brew link --overwrite bun@1.2.0
bun --version
```

To preview what would be replaced before linking:

```bash
brew link --overwrite bun@1.2.0 --dry-run
```

# Bundle libs

```bash
bun install
bun prepare
```

# Publish

```bash
npm login
bun release 
```

Example log for publishing:

```bash
❯ bun release             
$ ./scripts/release.sh
Starting the release process...
Provided options: 
Publishing 'react-native-quick-crypto' to NPM
$ release-it

🚀 Let's release @coolwallet-app/react-native-quick-crypto (currently at 1.0.18)


Empty changelog

✔ Select increment (next version): Other, please specify...
✔ Please enter a valid version: 1.0.18-cbx.0
✔ bun tsc && bun lint && bun format && bun prepare
✔ Publish @coolwallet-app/react-native-quick-crypto@cbx to npm? Yes
✔ Please enter OTP for npm: 056218
🔗 https://registry.npmjs.org/package/@coolwallet-app/react-native-quick-crypto
🏁 Done (in 60s.)
Successfully released QuickCrypto!
```

# Develop flow

- Create pull request into cbx branch
- After the PR merged, publish to npm on cbx branch
- Create pull request for the version change to cbx branch
- After version change PR merged, Create git tag and github release
  - Example git tag: `v0.7.17-cbx.6`
  - Using auto-generate notes from GitHub GUI
