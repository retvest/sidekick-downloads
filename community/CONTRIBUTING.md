# Share a Sidekick skill or workflow

Use Settings → Community → Prepare a contribution in a compatible Sidekick
version. Choose an item you have permission to share, give it a public author
name and a version, and include its complete licence text and attribution.
Review the entire generated package, then export it. Nothing is published by
that export. You submit the public contribution yourself through GitHub.

The app-side feature is currently unreleased. You can also prepare a JSON
package by following one of the examples in `items/`.

1. Remove secrets, private URLs, customer identifiers and personal material from
   the instructions, code and templates. Export excludes run inputs/outputs,
   conversations, Settings credentials and workspace files, but cannot tell
   whether a literal inside your definition is confidential.
2. Fork this public repository on GitHub. Add the package under
   `community/items/your-item-id/1.0.0.json`. IDs contain lowercase letters,
   numbers and hyphens. Versions contain three numeric components.
3. Include `format: sidekick-community-item-v1`, `id`, `version`, `kind`,
   `author`, `license`, `licenseText` and `payload`. Kind is `instruction` or
   `workflow`. Supported licence identifiers are `MIT`, `CC0-1.0` and
   `CC-BY-4.0`; preserve the full actual licence and required attribution.
4. Open a pull request describing what the item does, its model/tool needs,
   whether it contains executable code, what you actually checked and known
   limitations. Do not claim testing that you have not performed.
5. A maintainer reviews the package and adds its metadata and SHA-256 digest to
   `community/catalogue.json`. The entry must identify the exact file bytes.
   Publication occurs only when the pull request is merged.

To update an item, add a new version file. Do not replace an existing published
version with different bytes. For an unsafe or withdrawn version, change its
catalogue status to `withdrawn` and explain the reason in the pull request.
Already imported copies are not automatically removed or changed; users must
review them. Report vulnerabilities through [the security contact](https://retvest.com/security/)
instead of including private exploit material or credentials in a public issue.

Maintainer review covers the complete definition, authorship/licence statements,
embedded credentials or private material, tool permissions, code execution and
the accuracy of the description. It is not a sandbox or security guarantee.
Code steps run with the user's filesystem, network and process access after a
separate run approval. Never claim that a matching hash makes code safe.

The catalogue is limited to 100 entries and packages to 256 KB in this version.
Instructions are imported for manual use. Workflows retain their normal tool
bindings and per-run approval. A contributor's local connector IDs may not exist
on another computer; avoid embedding account-specific bindings in shared flows.

For derivatives, retain the original package's licence and attribution, add your
own contribution attribution where appropriate, and identify the original item
and version in the pull request. The app does not automatically relicense
imported content.
