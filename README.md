# haikult-l10n

Localization files for [Haiku.lt](https://haiku.lt) — an invoicing web application.

## Structure

Translations are organized by [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code. English (`en/`) is the source
language and serves as the reference for all other translations.

```
{lang}/
├── app-frontend/       # UI strings for the web application
│   ├── account.json
│   ├── common.json
│   ├── components.json
│   ├── errors.json
│   ├── expenses.json
│   ├── invoice.json
│   ├── invoices.json
│   ├── pages.json
│   ├── settings.json
│   └── statistics.json
├── pdf-generator/      # Strings used in generated PDF invoices
│   └── invoice.json
├── shared/             # Shared strings (emails, language names)
│   ├── email_strings.json
│   └── language_names.json
└── static-frontend/    # Content for the public-facing website
    ├── articles/       # Markdown articles (help, blog, legal, etc.)
    └── layout.json
```

## Contributing

Contributions to improve existing translations or add new ones are welcome!

### Improving an existing translation

1. Fork this repository.
2. Edit the relevant JSON or Markdown files under the language folder.
3. Use `en/` as the reference for keys and content.
4. Open a pull request describing what was changed and why.

### Adding a new language

1. Copy the entire `en/` directory and rename it to the target ISO 639-1 code.
2. Translate all strings and articles.
3. Add the language to `shared/language_names.json` in every language folder.
4. Open a pull request.

### Guidelines

- Keep JSON key names unchanged — only translate the values.
- Preserve placeholders (e.g. `{name}`, `%s`) exactly as they appear in the source.
- For Markdown articles, preserve the structure and formatting; translate the text content.
- When in doubt, match the tone of the existing translations in that language.

## License

[MIT](LICENSE) © Dalius Dobravolskas
