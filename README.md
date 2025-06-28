# Doctype JSON Schema

The `doctype-schema.json` file defines a JSON Schema for validating Frappe Doctype JSON definition files.

> **Disclaimer:** This schema was constructed based on the Doctypes available in Frappe at the time of creation. Some fields may be deprecated or removed in later versions. Please verify against the official Frappe documentation.

## Usage

You can enable JSON validation for your Doctype files in two ways:

### 1. VSCode Workspace Settings

Add or update `.vscode/settings.json` in your workspace:

```json
{
  "json.schemas": [
    {
      "fileMatch": ["**/doctype/*/*.json"],
      "url": "https://raw.githubusercontent.com/bawahakim/frappe-json-schema/main/doctype-schema.json"
    }
  ]
}
```

Or reference the local copy in this repo:

```json
{
  "json.schemas": [
    {
      "fileMatch": ["**/doctype/*/*.json"],
      "url": "./frappe-json-schema/doctype-schema.json"
    }
  ]
}
```

### 2. Add `$schema` to Your Doctype File

At the top of your Doctype JSON file, include the `$schema` property.

Remote URL example:

```json
{
  "$schema": "https://raw.githubusercontent.com/bawahakim/frappe-json-schema/main/doctype-schema.json",
  "doctype": "My DocType",
  "fields": [
    // ... field definitions ...
  ]
}
```

Local copy example:

```json
{
  "$schema": "./frappe-json-schema/doctype-schema.json",
  "doctype": "My DocType",
  // ... other properties ...
}
```

## License

`doctype-schema.json` is licensed under the same terms as this repository. See `LICENSE` for details.

---

For more information on JSON Schema, visit https://json-schema.org/
