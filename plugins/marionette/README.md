# Marionette

Build, debug, review, and test Marionette v5 applications with their installed,
version-matched documentation. This plugin bundles the Marionette skill, readable
Node.js lookup scripts, and a connection to the public documentation MCP at
`https://mcp.marionettejs.com/mcp`. Version `5.0.0-rc.2` targets the published release
candidate; it does not represent a stable v5 release.

## Install

In Claude Code, add the repository marketplace and install its plugin:

```text
/plugin marketplace add marionettejs/marionette#v5.0.0-rc.2
/plugin install marionette@marionettejs
```

Use `/marionette:marionette` for the bundled skill. The repository also provides
Codex and Cursor marketplace manifests and a portable Agent Plugins manifest.
Follow your client's plugin installation interface. Install the Marionette npm
package separately in your application; the plugin does not install a runtime.

For the skill alone, use the skills CLI from your application directory:

```sh
npx skills add marionettejs/marionette --skill marionette --agent codex
```

This follows the default branch and installs no MCP connection. To keep an exact
release's skill, copy the complete `skills/marionette` directory from the installed
Marionette npm package into your client's skill directory.

## Use

The skill routes to local Markdown in the installed package. Its optional lookup
scripts read local package files, verify documentation hashes, and print the
package version and source revision. They do not fetch documentation or execute
application examples. Node 24 or newer is required for the RC2 package.

The hosted MCP reads the public documentation snapshot. When used, it receives
your search queries, document or section identifiers, and requested version and
revision. It requires no account or API key. Read `marionette://catalog` first and
compare both package version and source revision with the installed package's
`docs-manifest.json`; use local docs when they differ. See the installed
`docs/tooling.md` for the complete identity checks. The plugin defines no hooks or
application mutations.

## License

MIT. See the repository's
[license](https://github.com/marionettejs/marionette/blob/v5.0.0-rc.2/license.txt).
