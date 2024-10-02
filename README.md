# Introduction

Xybor's Golang clean architecture template

## Workflow

Centralized authentication and authorization server.

1. Put or modify configurations in `config`.
2. Use `cmd` to start the server.
3. Call api by `adapter/rest` or `adapter/gprc` or execute command line in `adapter/cli`
to interact with the server.
4. `adapter` calls the `usercase` to handle application-specific logic.
5. `usecase`:
 - Calls `domain` to invoke business logic.
 - Calls `infras` to integrate
with external services or database.
 - Calls `pkg` to use shared libraries and utilities. 
 - Returns reponse to the `adapter` via `dto` models.
