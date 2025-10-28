# WordPress Plugin Development Guide

This project uses the Context7 MCP server for up-to-date WordPress documentation and DDEV for local development.

## Development Workflow

### 1. Use Context7 for WordPress Documentation

Before writing any WordPress plugin code:
1. Use the Context7 MCP server to fetch relevant WordPress documentation
2. Specify topics like: hooks, filters, REST API, admin pages, custom post types, meta boxes, shortcodes, etc.
3. Follow WordPress coding standards and best practices from the documentation

**WordPress Documentation ID**: `/websites/wordpress`

#### Example Prompts

- "Use Context7 to get WordPress hook documentation, then add a filter for..."
- "Look up WordPress REST API docs via Context7, then create an endpoint for..."
- "Fetch WordPress plugin structure docs, then help me create a plugin that..."
- "Use Context7 to get documentation on custom post types, then help me register a new CPT for..."
- "Look up WordPress admin pages and settings API via Context7, then create a settings page..."

### 2. Verify Code Compliance

After generating plugin code, **always** run the Plugin Check command to verify compliance with WordPress standards:

```bash
ddev wp plugin check <plugin-slug>
```

This command uses the WordPress Plugin Check plugin to validate:
- Coding standards compliance
- Security best practices
- Performance issues
- Accessibility requirements
- Plugin repository guidelines

#### Example Usage

```bash
# Check a specific plugin
ddev wp plugin check my-custom-plugin

# Get more detailed output
ddev wp plugin check my-custom-plugin --format=json
```

**Important**: Fix any errors or warnings reported by Plugin Check before considering the code complete.

## Best Practices

1. **Always fetch documentation first** - Use Context7 to get up-to-date WordPress APIs and patterns
2. **Run Plugin Check immediately** - Verify all generated code with `ddev wp plugin check`
3. **Follow WordPress Coding Standards** - Reference the standards from Context7 documentation
4. **Test in DDEV environment** - Use the local DDEV setup for all development and testing

## Workflow Summary

```
Request feature → Fetch Context7 docs → Generate code → Run Plugin Check → Fix issues → Test
```
