# Errors

A failed request returns an HTTP status and a JSON body with a stable `code` and, for most codes, a `message` written for people.

```json
{"code": "CONFLICT", "message": "The branch moved. Reload before creating a branch."}
```

Act on `code`. The wording of `message` can change.

## Common codes

| Status | Code | What it means | What to do |
|---|---|---|---|
| 400 | `VALIDATION_FAILED` | The request or the content it would commit is not valid. | Read `message`, fix the input and send it again. |
| 403 | `ACCESS_DENIED` | You are not signed in, or you lack the permission. | Sign in, or ask an admin for the role. |
| 403 | `ORIGIN_REQUIRED` | A write request did not come from the console origin. | Send it from the console origin. |
| 403 | `QUOTA_EXCEEDED` | The tenant reached a limit, such as storage. | Ask your platform operator to raise the limit. |
| 404 | `NOT_FOUND` | The project, branch or file does not exist or is not visible to you. | Check the id and your access. |
| 409 | `CONFLICT` | Someone changed the branch or file after you loaded it. | Reload and apply your change again. |
| 409 | `MERGE_CONFLICT` | A merge touched the same lines on both sides. | Resolve the files listed in `paths`. |
| 415 | `JSON_REQUIRED` | A write request was not JSON. | Send `Content-Type: application/json`. |
| 503 | `BUSY_RETRY` | The project is busy with another write. | Wait the `Retry-After` seconds and retry. |

Unexpected failures return `500 OPERATION_FAILED` without details. Retry, then contact your operator.
