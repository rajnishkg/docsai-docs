# DocsAI user documentation

This repository is the source of the DocsAI user documentation for tenant admins, authors, reviewers and readers. It is a DocsAI tenant documentation repository: the DocsAI console publishes it to the reader site after review. This README is for contributors and is not published.

It contains only documentation and sample APIs. Never add secrets, personal data or customer data.

## Layout

```text
catalog.json                     products, sections, documents, assets and APIs (schema version 2)
docs/docsai/v1/<section>/        one Markdown/MDX file per page; the file name is the page slug
assets/docsai/v1/screenshots/    <page-slug>/NN-<role>-<action>.png
apis/docsai/console-api/v1/      public OpenAPI 3.1 definition of the DocsAI console API (one file) and its guides
apis/docsai/billing-sample/v1/   protected sample API (console only, never published; owned by the api team)
playground/environments.yaml     repository-wide test servers (empty; the console API declares its own)
.github/CODEOWNERS               ownership; DocsAI maintains its own block
```

Sections: `get-started`, `tenant-admin`, `writing`, `github`, `api-docs`, `reference`.

## How to contribute

1. Start a branch named `work/<you>/<topic>`, in the console with **Start editing** or locally with `git switch -c`.
2. Change pages. A new page needs its entry in `catalog.json` (`documents`); a new image needs an entry in `assets` and in the page's `assets`. **New page** in the console writes both.
3. Commit with `docs(<section>): <change>`.
4. Submit the commit for review in the console, or push the branch and open a pull request.
5. After approval, a publisher publishes the commit. After a pull request is merged, an admin chooses **Sync source**.

See the published page *Naming conventions* for every naming rule.

## Run the API mocks

The console API declares a `mock` test server at `http://127.0.0.1:4020`; the billing sample lists `http://127.0.0.1:4021` in its `servers` for the Schema Studio Test view:

```bash
npx @stoplight/prism-cli mock apis/docsai/console-api/v1/openapi.yaml --host 127.0.0.1 --port 4020
npx @stoplight/prism-cli mock apis/docsai/billing-sample/v1/openapi.yaml --host 127.0.0.1 --port 4021
```

Keep each API definition in one `openapi.yaml`: the reader renders operations from the entry file only.

## License

Text and images: CC BY 4.0.
