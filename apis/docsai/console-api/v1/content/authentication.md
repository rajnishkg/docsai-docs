# Authentication

Every request runs as one signed-in person. DocsAI never decides who you are on its own: it asks the identity provider (IAM) your operator connected.

## Production consoles

The console uses the sign-in of your organization. Your browser sends the session the IAM integration expects, and DocsAI evaluates your permissions from your teams on every request. Scripts use a service principal issued by your operator, never a person's session.

This definition declares that case as `serviceToken`, a bearer token. Whether your console accepts bearer tokens, and how you get one, depends on the IAM integration: ask your operator.

`GET /api/session` needs no credentials. Without a session it answers with `principal` set to null.

## The local demo console

The local demo console has no real sign-in. It offers fixed synthetic identities (author, reviewer, admin, reader and others) and keeps the choice in the `docsai_demo` cookie.

1. Send `POST /api/session` with `{"identity": "author"}` from the console origin.
2. The response sets `docsai_demo`, an HttpOnly cookie valid for one day.
3. Send the cookie with every later request.

A production console answers `POST /api/session` with `403 IAM_NOT_CONNECTED`.

## Permissions

`GET /api/session?project=<id>` returns `capabilities`, the permissions you hold on that project:

| Capability | Lets you |
|---|---|
| `draft` | start branches, create pages and commit |
| `review` | approve or request changes on a submitted commit |
| `publish` | publish an approved commit to the reader site |
| `workspace` | open the project in the console |
| `manage-access` | change teams, project grants and areas |
| `read-insights` | read reader feedback and page statistics |

Your persona and language preferences never change these permissions.
