# Guides and manuals

Guides, tutorials, release notes and converted manual pages live under `docs/<product>/<version>/`.

Every page that readers should see is listed in `catalog.json` with its product, version, classification and lifecycle. Manuals converted from PDF use `docs/<product>/<version>/manuals/<manual-id>/`.

Group pages by author folder, for example `get-started/`, `concepts/`, `guides/`, `integrations/`, `features/` and `reference/`. The folder is for authors and ownership; readers see the page under its catalog `section`, and its route stays `docs/<product>/<version>/<slug>/` when it moves. Each version lists its `sections` in `catalog.json`. See the content structure guide in the DocsAI documentation.
