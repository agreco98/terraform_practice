# 🛡️ Test

Test.

---

## 📌 Purpose

Purpose.

---

## 🧭 Flow Overview

1. Test
   - Test Flow

---

## 📁 Project Structure & Conventions

'''bash
├── terraform/ # Infrastructure as code
│ ├── backend/ # Backend configs for dev, test, prod
│ │ ├── backend.dev.conf
│ │ ├── backend.test.conf
│ │ └── backend.prod.conf
│ ├── lambda_<name>.tf # Lambda definition
│ ├── lambda_<name>iam_role.tf # IAM role for Lambda (least privilege)
│ ├── api.tf # API Gateway definition
│ ├── api_resource.tf # API resource paths
│ ├── api_method<name>METHOD.tf # One per method (e.g., GET, POST)
│ ├── step_function.tf
│ ├── step_function_iam_role.tf
│ ├── dynamodb.tf


---

### ➕ Adding a New Lambda

1. Create a folder under `src/lambdas/lambda_<name>/`:
   - Include `main.py`, `__init__.py`, and optionally `requirements.txt`
2. Add unit tests in `src/tests/`
3. In `terraform/`, create:
   - `lambda_<name>.tf`
   - `lambda_<name>_iam_role.tf` (least privilege IAM)
4. Run `bundle_lambdas.py` to build the zipped version into `/dist`

---

### ➕ Adding a New API Method

1. Create a new file: `api_method_<resource>_<METHOD>.tf`
2. Update `api_resource.tf` to register the new route
3. Ensure proper Lambda integration and IAM permission if needed

---

## 🧪 Testing

Install dependencies from `src/tests/requirements.txt` and run with your test runner of choice (e.g., `pytest`).

Example:
```bash
pip install -r src/tests/requirements.txt
pytest src/tests/
```

## API Usage

### Endpoint

POST

### Query parameters

- test

### Request Body

```bash
{
    'email': 'email'
    'test': <secret-api>
}
```

### Dry Run

```bash
{
    'email': 'email'
}
```

### Request Body 2

```bash
{
    'email': 'email'
}
```

### Notes

- Notes Tests

--- 

## 📄 Additional Documentation

For more details, please refer to the [Confluence documentation page](https://tu-confluence-link-aqui).
