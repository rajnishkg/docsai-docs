# API contracts

Canonical API contracts live under `apis/<product>/<api-id>/<version>/`: `openapi.yaml` with its local `components/`, `graphql/schema.graphql` or `protobuf/service.proto`.

Reference shared definitions under `schemas/` with repository-relative `$ref`s. ReDoc, playground pages and SDKs are generated at publish time and are never committed here.
