# ✅ API Testing Checklist

> Use this checklist for every API endpoint you test. Check off each item as you verify it.
> Covers: REST API testing using Postman or automation tools.

**Author:** Dipali Pagire | QA Engineer | Pune, India

---

## 📋 Test Details

| Field         | Value                        |
|---------------|------------------------------|
| API Name      | [e.g., User Management API]  |
| Base URL      | [https://api.example.com]    |
| Endpoint      | [e.g., GET /api/users]       |
| Tested By     | [Name]                       |
| Date          | [DD-MM-YYYY]                 |
| Tool Used     | Postman / Newman / REST Assured |

---

## 1. 🔢 Status Code Verification

- [ ] **200 OK** — Successful GET / PUT / PATCH requests return 200
- [ ] **201 Created** — Successful POST requests return 201
- [ ] **204 No Content** — Successful DELETE returns 204 with empty body
- [ ] **400 Bad Request** — Invalid input / missing required fields returns 400
- [ ] **401 Unauthorized** — Missing or invalid token returns 401
- [ ] **403 Forbidden** — Valid token but insufficient permissions returns 403
- [ ] **404 Not Found** — Non-existent resource ID returns 404
- [ ] **409 Conflict** — Duplicate resource creation returns 409
- [ ] **422 Unprocessable Entity** — Validation error returns 422 (where applicable)
- [ ] **500 Internal Server Error** — Server-side errors return 500 (not 200)

---

## 2. 📦 Response Body Validation

- [ ] Response body is valid JSON (not HTML or plain text)
- [ ] All required fields are present in the response
- [ ] Field names match the API contract / documentation exactly
- [ ] No extra/unexpected fields are returned (no data leakage)
- [ ] Field data types are correct (string, number, boolean, array, object)
- [ ] Numeric fields are numbers, not strings (e.g., `"id": 1` not `"id": "1"`)
- [ ] Date/time fields are in expected format (ISO 8601: `2024-01-15T10:30:00Z`)
- [ ] Boolean fields are `true`/`false`, not `"true"`/`"false"`
- [ ] Null values are `null`, not empty string `""`
- [ ] Empty list returns `[]`, not `null`
- [ ] Nested objects have correct structure
- [ ] Array items all have consistent schema

---

## 3. 📄 Response Headers

- [ ] `Content-Type: application/json` header is present
- [ ] `Content-Type` charset is `UTF-8` where applicable
- [ ] `Authorization` / `Bearer` token not exposed in response headers
- [ ] No sensitive data (passwords, keys) in response headers
- [ ] CORS headers present if cross-origin requests are expected
- [ ] `X-Request-ID` or trace header present (for debugging/logging)

---

## 4. ⚡ Response Time / Performance

- [ ] Response time is under **2000ms** for standard GET requests
- [ ] Response time is under **3000ms** for POST/PUT operations
- [ ] Response time is consistent across multiple runs (no spikes)
- [ ] Large list responses (100+ records) respond within acceptable time
- [ ] Paginated endpoints handle large pages without timeout

---

## 5. 🔒 Authentication & Authorisation

- [ ] Request without token returns **401 Unauthorized**
- [ ] Request with expired token returns **401 Unauthorized**
- [ ] Request with invalid/tampered token returns **401 Unauthorized**
- [ ] User A cannot access User B's private data (authorisation check)
- [ ] Admin-only endpoints return **403** for non-admin users
- [ ] Token with read-only scope cannot perform write operations
- [ ] Token is not returned in response body after login where not expected

---

## 6. ✏️ CRUD Operations

### GET (Read)
- [ ] Returns correct data for valid ID
- [ ] Returns 404 for non-existent ID
- [ ] List endpoint returns paginated results
- [ ] Pagination fields (`page`, `per_page`, `total`, `total_pages`) are accurate
- [ ] Filtering by query params returns correct results
- [ ] Sorting query params work as expected

### POST (Create)
- [ ] Successful creation returns 201 with created resource in body
- [ ] Created resource has auto-generated `id` field
- [ ] Created resource has `createdAt` timestamp
- [ ] Duplicate creation returns 409 (if applicable)
- [ ] Missing required field returns 400 with descriptive error message
- [ ] Extra/unknown fields in request body are handled gracefully (ignored or rejected)

### PUT (Full Update)
- [ ] All fields in the resource are replaced
- [ ] Response includes `updatedAt` timestamp
- [ ] PUT with missing required field returns 400
- [ ] PUT on non-existent resource returns 404

### PATCH (Partial Update)
- [ ] Only the specified fields are updated
- [ ] Unspecified fields retain their original values
- [ ] Response includes `updatedAt` timestamp

### DELETE
- [ ] Successful delete returns 204 with empty body
- [ ] Deleted resource is not accessible via GET (returns 404)
- [ ] Deleting non-existent resource returns 404

---

## 7. 🧪 Negative / Boundary Testing

- [ ] Empty string in required field returns 400
- [ ] Null value in required field returns 400
- [ ] Integer field with string value returns 400
- [ ] Extremely long string input (>10,000 chars) is handled gracefully
- [ ] Negative number in numeric field is handled
- [ ] Zero as an ID returns 404 or 400
- [ ] Special characters in string fields (`<`, `>`, `"`, `'`, `&`) don't break the API
- [ ] SQL injection attempt in input fields is rejected
- [ ] XSS payload in string field is sanitised/rejected
- [ ] Numeric overflow values are handled
- [ ] Decimal precision is correct (e.g., `19.99` not `19.990000000001`)

---

## 8. 🗄️ Database / Data Integrity

- [ ] Created record exists in the database after POST
- [ ] Updated fields are correctly saved to the database after PUT/PATCH
- [ ] Deleted record is removed from the database after DELETE
- [ ] Relationships between tables/collections are maintained (no orphan records)
- [ ] Unique constraints are enforced (duplicate email, username etc. rejected)
- [ ] Foreign key constraints are enforced

---

## 9. 📃 Error Response Validation

- [ ] Error responses have consistent JSON structure: `{ "error": "message" }` or `{ "message": "...", "code": "..." }`
- [ ] Error messages are descriptive and helpful (not just "error" or "bad request")
- [ ] Error messages do NOT expose internal server details, stack traces, or file paths
- [ ] Error messages do NOT expose database schema or query details
- [ ] 500 errors do not leak sensitive internal information

---

## 10. 🔗 Environment Variables

- [ ] Base URL is parameterised (uses environment variable, not hardcoded)
- [ ] Auth token is stored in environment variable (not hardcoded in request)
- [ ] All dynamic IDs are saved from previous responses and reused
- [ ] No sensitive credentials are committed to version control

---

## 11. 📝 Documentation & Reporting

- [ ] Each test request has a clear, descriptive name
- [ ] Test assertions are written for every request
- [ ] Failed assertions include useful failure messages
- [ ] Collection is organised into logical folders by feature/module
- [ ] Newman/CI run generates exportable report

---

## Quick Reference: Common HTTP Status Codes

| Code | Meaning                | Common Cause                          |
|------|------------------------|---------------------------------------|
| 200  | OK                     | Successful GET / PUT / PATCH          |
| 201  | Created                | Successful POST                       |
| 204  | No Content             | Successful DELETE                     |
| 400  | Bad Request            | Invalid input, missing required field |
| 401  | Unauthorized           | Missing/invalid/expired token         |
| 403  | Forbidden              | Insufficient permissions              |
| 404  | Not Found              | Resource doesn't exist                |
| 409  | Conflict               | Duplicate resource                    |
| 422  | Unprocessable Entity   | Validation failed                     |
| 429  | Too Many Requests      | Rate limit exceeded                   |
| 500  | Internal Server Error  | Backend/server crash                  |

---

*Checklist by Dipali Pagire | QA Engineer | Pune, India*
