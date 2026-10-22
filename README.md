# Thally

![Thally](assets/icon.png)

Create and monitor your own Thally documentation sites from Claude. Connect your
Thally workspace to create a managed docs site, follow deployment progress, look
up its published AI readiness score, inspect aggregate traffic, and review
potentially stale pages and observed product-update work.

## Connect and use

You need a Thally account and a workspace you can access. Connect the bundled
Thally connector in Claude and complete Thally sign-in and workspace consent.
GitHub authorization is also required for site creation and repository evidence.
On Claude Team or Enterprise, an organization owner may need to add the connector
before members connect their own accounts. Never paste access tokens into chat.

In Claude Code, load this folder with `claude --plugin-dir ./thally`, then use
`/mcp` to check the connector and authenticate. Skills are available as
`/thally:create-docs-site`, `/thally:ai-readiness`, `/thally:docs-analytics`, and
`/thally:docs-freshness`. In Claude chat or Cowork, enable the plugin and connect
its connector; describe the task naturally.

Try these prompts:

- “Create a new Thally docs site for my product using a private GitHub repository.”
- “What are my docs site's AI readiness score and analytics for the last 30 days?”
- “Which pages may be stale after my latest product updates?”

Site creation uses Thally's canonical starter or a compatible existing Thally
docs repository. Review the site name, repository, and visibility before creation.
Creation consumes available workspace capacity and returns pending until
provisioning completes. Creating a starter does not generate product-specific
documentation. Identical retries reuse the same UUID and settings.

## Plans and limits

The Free plan includes managed hosting and Analytics for one docs site. Track
requires Cloud or Enterprise and the existing setup and AI-credit balance.
The connector uses the workspace's current permissions, plan, feature settings, and capacity;
installing this plugin grants no additional entitlement. Billing and plan changes
happen in Thally, outside the plugin.

Readiness measures structure and machine readability, not product-update coverage.
Freshness reports observed source drift and Track work; missing evidence remains
unknown. These tools cannot delete sites, merge pull requests, purchase plans,
start paid generation, or publish documentation edits.

## Data, privacy, and access

The plugin contains instructions and a remote connector configuration. It runs
no bundled server, scripts, hooks, or dependency installation. Tool arguments
and OAuth-authorized requests go to https://app.thally.io/api/mcp/cloud. Thally
uses its existing hosting and GitHub integrations to perform requested operations.
Returned workspace site metadata, deployment state, aggregate analytics,
readiness checks, source-drift evidence, and Track review links become available
to Claude in the conversation. Tools exclude credentials, build logs, raw
repository contents, and freeform visitor search/message text.

Thally handles service data under its [Privacy Policy](https://thally.io/privacy)
and [Terms of Service](https://thally.io/terms). Claude's processing follows your
Anthropic agreement and account controls. Revoke the connection in Thally
Settings to stop subsequent access. This source package makes no additional
retention or deletion promise.

## Help and source status

See [Thally documentation](https://docs.thally.io), visit
[Thally](https://thally.io), or email [support@thally.io](mailto:support@thally.io).
The package is MIT licensed; hosted services remain subject to Thally's terms.

Version 1.0.0 is prepared source for Claude. Local package validation does not
establish a working production connection or completed Claude testing. Release
requires live OAuth, all-tool testing, reviewer access, and directory review.
