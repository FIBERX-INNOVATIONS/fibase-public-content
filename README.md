# Fibase Public Content Repository

This repository stores all public-facing content for the application in multiple languages. It serves as a centralized source for managing email templates, app copy, and other user-facing content that needs to be maintained across different locales.

## Project Structure

```
fibase-public-content/
├── app_content/           # Application UI text and copy content
├── email_content/         # Email template content and notifications
└── README.md             # This file
```

### Folders

#### `app_content/`
Contains JSON files for application-specific text content such as:
- UI labels and buttons
- Error messages
- Help text and tooltips
- On-boarding content
- General application copy

Each language should have its own JSON file named according to the locale code (e.g., `en-GB.json`, `es-ES.json`, `fr-FR.json`).

#### `email_content/`
Contains JSON files for email notification templates and transactional emails. Includes:
- Subject lines
- Email body content with headers, greetings, and call-to-action text
- Placeholder variables for dynamic content

Each language should have its own JSON file named according to the locale code.

## Content Format

### Language File Naming Convention

Language files follow the [BCP 47 language tag](https://tools.ietf.org/html/bcp47) format:
- `en-GB` - English (United Kingdom)
- `en-US` - English (United States)
- `es-ES` - Spanish (Spain)
- `fr-FR` - French (France)
- `de-DE` - German (Germany)

### JSON Structure Example

Email content files use a hierarchical structure with template keys and nested properties:

```json
{
    "TEMPLATE_NAME": {
        "subject_text": "Email subject line",
        "body": {
            "header_text": "Email header",
            "hello_text": "Greeting",
            "main_content_text": "Primary message content",
            "action_text": "Call-to-action text",
            "contact_us_text": "Contact information or support details"
        }
    }
}
```

**Key Points:**
- Use descriptive, all-caps template names
- Use `_text` suffix for text content keys (e.g., `header_text`, `subject_text`)
- Organize nested content logically using `body` or similar containers
- Use clear, descriptive key names that indicate content purpose

## Adding a New Language

To add support for a new language:

1. **Duplicate existing files**: Copy the existing language files (e.g., `en-GB.json`) from both `app_content/` and `email_content/` folders
2. **Rename files**: Use the appropriate BCP 47 language tag (e.g., `de-DE.json` for German)
3. **Translate content**: Replace all English text values with translations in the target language
4. **Maintain structure**: Keep the JSON structure and keys identical - only translate the string values
5. **Test**: Ensure valid JSON formatting using a JSON validator

## File Format Requirements

- **File Type**: JSON (`.json`)
- **Encoding**: UTF-8
- **Formatting**: Properly formatted with consistent indentation (2 or 4 spaces)
- **Validation**: All files must be valid JSON

## Usage Guidelines

- **Keys**: Never change key names between language versions - these are used by the application to reference content
- **Variables**: Use clear variable naming conventions for dynamic content
- **Length**: Keep content concise and appropriate for UI/email display
- **Consistency**: Maintain consistent terminology and tone across all content in a language
- **Review**: Have native speakers review translations for cultural appropriateness and accuracy

## Current Supported Languages

- English (United Kingdom) - `en-GB.json`

## Contributing

When adding new content:

1. Add the new template or copy to all language files
2. Maintain consistent JSON structure across all languages
3. Ensure all files remain valid JSON
4. Update this README if adding new content categories or languages

## Related Resources

- [BCP 47 Language Tags](https://tools.ietf.org/html/bcp47)
- [JSON Format Specification](https://www.json.org/)
- [UTF-8 Encoding](https://en.wikipedia.org/wiki/UTF-8)
