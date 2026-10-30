---
name: implement-api-endpoint
description: Implement or modify backend REST API endpoints, including routing, validation, authorization, business logic, persistence, error handling, and tests. Use when the user requests API development.
---

# Implement API Endpoint

## Purpose

Provide a consistent workflow for implementing backend REST API endpoints in an existing software project.

This skill is framework-independent and must follow the actual project's architecture, programming language, and conventions.

## Step 1 — Analyze the Request

1. Identify the HTTP method and endpoint path.
2. Determine request parameters, headers, and body.
3. Determine the expected response structure.
4. Identify authorization requirements.
5. Identify validation rules and error responses.
6. Identify database operations and state transitions.

Do not invent unspecified requirements.

## Step 2 — Inspect the Existing Code

Before implementing:

1. Locate existing routes, controllers, or Lambda handlers.
2. Identify related services and domain models.
3. Inspect request and response DTOs.
4. Examine repository or database access patterns.
5. Identify existing authentication and authorization mechanisms.
6. Find similar endpoints that can be reused.

Use the project's existing architecture.

Do not introduce a new framework or architectural pattern without a clear reason.

## Step 3 — Plan the Implementation

Prepare a concise implementation plan containing:

- Files to create or modify.
- Required API changes.
- Business logic changes.
- Data access changes.
- Authorization and validation.
- Tests to add or update.

For significant changes, present the plan and obtain user approval before proceeding.

## Step 4 — Implement the Endpoint

Follow these principles:

- Keep HTTP handling separate from business logic when the architecture supports it.
- Validate request parameters and payloads.
- Enforce authorization on the server side.
- Reuse existing services and utilities.
- Preserve established response formats.
- Handle missing resources and invalid states explicitly.
- Avoid unnecessary dependencies and abstractions.
- Keep changes limited to the requested functionality.

For operations modifying multiple records, consider atomicity, concurrency, idempotency, and failure recovery.

## Step 5 — Handle Errors

Verify:

- Invalid input is rejected.
- Missing resources produce the required error response.
- Unauthorized or forbidden access is rejected.
- Business rule violations are handled.
- Internal errors do not expose sensitive information.

Follow the API contract and existing project conventions when choosing HTTP status codes.

## Step 6 — Add Tests

When the project supports automated tests, cover:

- Successful requests.
- Invalid input.
- Missing resources.
- Unauthorized access.
- Forbidden operations.
- Empty data.
- Important business rule violations.
- State changes and persistence behavior.

Use the project's existing test framework.

Do not claim tests passed unless they were executed.

## Step 7 — Verify

When permitted:

1. Run relevant tests.
2. Check compilation or syntax.
3. Verify request and response contracts.
4. Review the changes for unintended side effects.
5. Inspect the final diff.

Report any checks that could not be completed.

## Step 8 — Report

Provide a concise summary:

- Endpoint implemented.
- Files modified.
- Business rules implemented.
- Tests executed and results.
- Remaining limitations or risks.

## Safety

Never expose credentials or secrets.

Never deploy to production without explicit permission.

Never execute destructive database operations without approval.

Never modify unrelated project files.


## Resource Efficiency

- Work only on the task explicitly requested by the user.
- Prefer focused code inspection over reading the entire repository.
- Reuse existing code and avoid unnecessary rewrites.
- Do not repeatedly analyze unchanged files without a reason.
- For large tasks, divide implementation into small logical stages.
- Avoid unnecessary tool calls and repeated test executions.
- Limit automatic debugging to two repair attempts
  before reporting the problem and asking for guidance.
- Run targeted tests before considering a full test suite.
- Ask for approval before expensive or long-running operations.
- Do not start unrelated improvements or refactoring.

## Change Control and Safety

- Before editing, identify the files that need modification.
- Do not modify files outside the agreed task scope.
- Ask for approval before expanding the scope.
- Never run deployment, migration, infrastructure,
  or destructive commands without explicit approval.
- Do not execute AWS CLI, Terraform apply/destroy,
  or Syndicate deployment commands without approval.
- Do not use automatic approval for high-risk tools.
- Never reset, clean, or rewrite Git history automatically.
- Do not commit or push changes unless explicitly requested.
- After implementation, report every created,
  modified, and deleted file.
- Report all executed commands and their outcomes.
- Stop and ask the user when an operation may affect
  external systems or persistent data.