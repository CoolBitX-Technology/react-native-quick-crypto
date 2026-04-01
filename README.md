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
```

# Publish

```bash
npm login
bun release $RELEASE_VERSION # e.g.: 0.7.17-cbx.0
```

Example log for publishing:

```bash
❯ bun release 0.7.17-cbx.6
$ ./scripts/release.sh 0.7.17-cbx.6
Starting the release process...
Provided options: 0.7.17-cbx.6
Publishing 'react-native-quick-crypto' to NPM
$ release-it 0.7.17-cbx.6

🚀 Let's release @coolwallet-app/react-native-quick-crypto (0.7.17-cbx.5...0.7.17-cbx.6)


Empty changelog

✔ bun tsc && bun lint && bun format && bun prepare
? Publish @coolwallet-app/react-native-quick-crypto@cbx to npm? Yes
? Please enter OTP for npm: 513493
🔗 https://registry.npmjs.org/package/@coolwallet-app/react-native-quick-crypto
🏁 Done (in 225s.)
Successfully released QuickCrypto!
```

# Develop flow

- Create pull request into cbx branch
- After the PR merged, publish to npm on cbx branch
- Create pull request for the version change to cbx branch
- After version change PR merged, Create git tag and github release
  - Example git tag: `v0.7.17-cbx.6`
  - Using auto-generate notes from GitHub GUI
