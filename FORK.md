# Fork Notes

This is a fork of [bun913/mcp-testrail](https://github.com/bun913/mcp-testrail)
maintained by OneLogin/OneIdentity for security reasons.

## Why We Fork

- Pins the agent runtime to a reviewed commit, preventing supply-chain surprises
  from upstream publishes.
- Allows internal review and approval before any version upgrade.

## Changes from Upstream

- Added `"prepare": "npm run build"` to `package.json` so the TypeScript
  compiles when installed directly from the git URL (required for
  `npm install git+https://...`).

## Upgrading

1. Review the upstream changes: `git log upstream/main..main`
2. Merge upstream: `git fetch upstream && git merge upstream/main`
3. Audit any new code in `src/`.
4. Push and get the new commit SHA.
5. Update the SHA in `agents/context/OneLogin/mcp_servers/testrail/setup.sh`
   and `setup.ps1` in the [oi-eng/.github](https://github.com/oi-eng/.github) repo.
