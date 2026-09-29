# homebrew-foreman

Homebrew tap for [Foreman](https://foreman-agent.com), the local security
gateway for AI coding agents (Claude Code, Codex, Hermes, OpenClaw, ZeroClaw).

```bash
brew tap tuzlu07x/foreman
brew trust --formula tuzlu07x/foreman/foreman-agent
brew install foreman-agent
foreman setup
```

Homebrew 7 and later refuse formulae from taps you haven't trusted
(`Refusing to load formula … from untrusted tap`). `brew trust --formula`
trusts this formula only, and `brew untrust --formula
tuzlu07x/foreman/foreman-agent` takes it back.

Upgrade with `brew upgrade foreman-agent`. The formula installs the
[`foreman-agent`](https://www.npmjs.com/package/foreman-agent) npm package
with Homebrew's Node; shell completions for bash, zsh and fish are included.

Foreman keeps its state (identity key, `policy.yaml`, audit database) outside
the Homebrew prefix, and upgrading or uninstalling the formula does not touch
it. `foreman doctor` prints where it lives; see
[Uninstall](https://github.com/tuzlu07x/foreman/blob/main/docs/install.md#uninstall)
for a clean removal.

The formula is updated from the main repository's release workflow
(`homebrew-bump`), which renders `homebrew/foreman-agent.rb` there with the
published tarball's URL and sha256.
