---
name: REST API Architect
description: Expert in designing resource-oriented REST APIs using OpenAPI 3.1 specifications.
---

# Context
Use this skill when:
1. Designing new API endpoints or resources.
2. Reviewing existing OpenAPI (`swagger.yaml/json`) files.
3. Generating boilerplate code from an API contract.

# Design Principles

### 1. Resource-First Naming
- **Nouns Only:** Use `/users`, not `/getUsers`. Actions are defined by HTTP methods.
- **Plurality:** Use plural nouns for collections (`/orders`) and IDs for instances (`/orders/{id}`).
- **Case:** All paths MUST be `kebab-case` and lowercase.

### 2. Semantic HTTP Methods
- `GET`: Idempotent retrieval. No side effects.
- `POST`: Create a new resource or trigger a non-idempotent action.
- `PUT`: Full replacement of a resource (Idempotent).
- `PATCH`: Partial update (Preferred over PUT for performance).
- `DELETE`: Remove a resource.

### 3. Standardization (OpenAPI 3.1)
- **OperationId:** Every operation must have a unique, camelCase `operationId` (e.g., `listUsers`).
- **Descriptions:** Every parameter, property, and response must have a `description` field for AI discoverability.
- **Status Codes:** - `201 Created` for successful POSTs.
  - `422 Unprocessable Entity` for validation errors (Standard in 2026).
  - `429 Too Many Requests` for rate-limiting.
- **Error Format:** Follow **RFC 9457** (Problem Details for HTTP APIs).

### 4. Collection Handling
- **Pagination:** Use cursor-based pagination for large datasets.
- **Filtering:** Use query parameters (e.g., `/products?category=tech`).
- **Sorting:** Use a standardized `sort` parameter (e.g., `?sort=-created_at`).

# Instructions for the Agent
- When asked to "create an endpoint," first define the **Path**, then the **Request Schema**, then the **Success/Error Responses**.
- Always use `$ref` to keep schemas modular and reusable in `components/schemas`.
- Ensure all Date/Time fields use `format: date-time` (ISO 8601).