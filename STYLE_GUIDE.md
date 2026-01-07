# API Documentation Style Guide
**Version:** 1.0.0  
**Author:** Belinda Martina

## 1. Voice and Tone
* **Active Voice:** Use active voice whenever possible. (e.g., "The API returns a JSON object" instead of "A JSON object is returned by the API").
* **Professional yet Accessible:** Avoid jargon unless it is a standard industry term (like JWT or CRUD).
* **Direct:** Use "You" to refer to the developer.

## 2. Terminology Standards
To maintain consistency across the docs, use these specific terms:
| Term | Description |
| :--- | :--- |
| **Endpoint** | A specific URL where the API can be accessed. |
| **Payload** | The data sent in a POST or PUT request. |
| **Token** | Specifically refers to the JWT Bearer token used for auth. |
| **Call** | The act of sending a request to the API. |

## 3. Formatting Guidelines
### 3.1 HTTP Methods
Always use UPPERCASE for HTTP methods and wrap them in bold:
* **GET**
* **POST**
* **PUT**
* **DELETE**

### 3.2 URLs and Paths
* Use backticks for paths: `/users/{id}`.
* Use curly braces `{ }` for placeholders/variables.

### 3.3 Code Blocks
Always specify the language for syntax highlighting:
\`\`\`json
{
  "id": 1
}
\`\`\`

## 4. Error Message Standards
All error documentation must include the HTTP Status Code, the `error_code` string, and a human-readable suggestion.

**Example:**
> **401 Unauthorized** > `ERR_AUTH_EXPIRED`: Your session has expired. Please log in again.

## 5. API Reference Structure
Every endpoint page must follow this exact order:
1. **Title** (The Method and Path)
2. **Summary** (One sentence on what it does)
3. **Authentication** (Required/Optional/None)
4. **Parameters** (Table format)
5. **Request Example**
6. **Response Example** (Success & Error)
