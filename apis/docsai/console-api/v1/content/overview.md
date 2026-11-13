# Console API overview

The DocsAI console API is the HTTP API the console itself uses. Everything you do in the console, from starting a branch to approving a commit, is a request to this API, made as you and checked against your permissions.

## What you can do with it

- **Session**: find out who is signed in and which permissions they hold on a project.
- **Projects**: list the documentation projects of your tenant.
- **Repository**: list branches, start a personal branch, read and commit files, read the diff of a branch, and submit, approve or request changes on its exact commit.
- **Reader**: find the published reader pages that show a Schema Studio API.
- **Notifications**: read and clear the inbox behind the bell in the console header.

## Before you start

- Requests run inside one tenant: the tenant of the signed-in person.
- Write requests must send JSON (`Content-Type: application/json`) from the console origin. Requests from another origin get `403 ORIGIN_REQUIRED`.
- Project ids are UUIDs. Read them from `GET /api/projects`.

See [Authentication](authentication.md) for how a request is signed in and [Errors](errors.md) for the error format.

## Try it

Choose **Test Request** next to an operation. Requests from the reader site go to the **Local mock** server, which answers with the examples in this definition. They never reach a real console.
