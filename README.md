# homebrew-merlion

Homebrew tap for [merlion-agent](https://github.com/MerlionOS/merlion-agent) — a Rust port of hermes-agent.

## Install

```bash
brew tap MerlionOS/merlion
brew install merlion-agent
merlion doctor
```

## Updating the formula

When a new merlion release lands, fetch the sha256s from the release
assets and update [`Formula/merlion-agent.rb`](Formula/merlion-agent.rb):

```bash
for t in x86_64-apple-darwin aarch64-apple-darwin x86_64-unknown-linux-gnu aarch64-unknown-linux-gnu; do
  curl -fsSL "https://github.com/MerlionOS/merlion-agent/releases/download/v<NEW>/merlion-$t.tar.gz.sha256"
done
```

Bump `version` in the formula, patch the four `sha256` fields, commit, push.
