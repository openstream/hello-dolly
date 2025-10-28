# Hello Dolly - WordPress Plugin Development Example

This repository demonstrates the complete process of fixing a WordPress plugin to meet modern coding standards and WordPress.org requirements.

## 🎯 What This Repository Demonstrates

This project showcases a comprehensive workflow for WordPress plugin development using:

- **Context7 MCP** - Fetching up-to-date WordPress documentation
- **WP-CLI Plugin Check** - Validating code against WordPress standards
- **Claude Code** - AI-assisted development with best practices
- **Git Version Control** - Documenting the complete development journey

## 📚 About Hello Dolly

Hello Dolly is WordPress's classic example plugin, created by Matt Mullenweg. It displays random lyrics from the song "Hello, Dolly" by Jerry Herman in the WordPress admin area.

While it's a simple plugin, the original version had **6 coding standards violations** that we've systematically fixed and documented.

## 🔧 Development Journey

### Commit History

The repository's commit history tells the complete story:

1. **Initial Setup** - Claude Code documentation and workflow
2. **Original Plugin** - Hello Dolly v1.7.2 with 6 violations
3. **Security Fixes** - Proper output escaping and WordPress functions
4. **Text Domain Resolution** - Understanding WordPress i18n requirements
5. **Folder Structure** - Moving to proper plugin architecture
6. **Documentation** - Adding WordPress.org compliant readme.txt

### Issues Fixed

| Issue | Original | Fixed |
|-------|----------|-------|
| **License** | Missing GPL header | ✅ GPL v2 or later with URI |
| **Security** | No output escaping | ✅ `esc_html()`, `esc_attr()`, `esc_html__()` |
| **Functions** | `mt_rand()` | ✅ `wp_rand()` |
| **i18n** | Missing text domain | ✅ Text domain: `hello` |
| **Structure** | Single file | ✅ Proper folder: `plugins/hello/` |
| **Docs** | No readme.txt | ✅ WordPress.org compliant readme |

## 🛠️ Development Workflow

This project demonstrates the recommended WordPress plugin development workflow:

```bash
# 1. Use Context7 to fetch WordPress documentation
context7 get-library-docs /websites/wordpress --topic "hooks filters escaping"

# 2. Write/modify plugin code following standards

# 3. Verify with WP-CLI Plugin Check
ddev wp plugin check hello

# 4. Commit with descriptive messages
git commit -m "Fix: Add proper output escaping for security"
```

### Tools Used

- **DDEV** - Local WordPress development environment
- **WP-CLI** - WordPress command-line interface
- **Plugin Check** - Official WordPress plugin checker
- **Context7 MCP** - Real-time WordPress documentation
- **Claude Code** - AI-powered development assistant

## 📁 Repository Structure

```
wordpress-claude/
├── .claude/
│   └── claude.md              # Claude Code workflow documentation
├── wp-content/
│   └── plugins/
│       └── hello/
│           ├── hello.php      # Fixed Hello Dolly plugin
│           └── readme.txt     # WordPress.org documentation
├── .gitignore                 # WordPress-specific ignores
├── LICENSE                    # GPL v2 License
└── README.md                  # This file
```

## ✅ Plugin Check Results

### Before (Original v1.7.2)

```
❌ Missing "License" in Plugin Header
❌ mt_rand() discouraged - use wp_rand()
❌ Missing $domain parameter in __()
❌ Unescaped output: __() on line 67
❌ Unescaped output: $lang on line 68
❌ Unescaped output: $chosen on line 69
```

### After (Fixed v1.7.3)

```bash
$ ddev wp plugin check hello
✅ Success: Checks complete. No errors found.
```

## 📖 Key Learnings

### 1. Security Through Output Escaping

**Always escape output** - even when data seems "safe":

```php
// ❌ Wrong (vulnerable to XSS)
echo $variable;

// ✅ Correct (safe)
echo esc_html( $variable );
echo esc_attr( $attribute );
echo esc_url( $url );
```

### 2. Text Domain Conventions

For proper internationalization:

- Text domain must match **folder name** (not filename)
- Single-file plugins: `plugins/hello.php` → text domain `hello.php`
- Folder-based plugins: `plugins/hello/hello.php` → text domain `hello`

### 3. WordPress-Specific Functions

Use WordPress functions instead of PHP alternatives:

- `wp_rand()` instead of `mt_rand()`
- `wp_remote_get()` instead of `file_get_contents()`
- `wp_safe_redirect()` instead of `header('Location: ...')`

### 4. Plugin Structure Best Practices

```
plugins/plugin-name/           # Folder matches text domain
├── plugin-name.php           # Main file
├── readme.txt                # WordPress.org docs
├── languages/                # Translation files
├── assets/                   # CSS, JS, images
└── includes/                 # Additional PHP files
```

## 🚀 Using This Repository

### Prerequisites

- WordPress 4.6+
- PHP 5.6+
- WP-CLI with Plugin Check installed

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/openstream/hello-dolly.git
   cd hello-dolly
   ```

2. Copy plugin to WordPress:
   ```bash
   cp -r wp-content/plugins/hello /path/to/wordpress/wp-content/plugins/
   ```

3. Activate the plugin:
   ```bash
   wp plugin activate hello
   ```

### Verifying the Fixes

Run Plugin Check to verify all standards are met:

```bash
wp plugin check hello
```

## 📝 Claude Code Workflow

This repository includes `.claude/claude.md` which documents the complete workflow for using Claude Code with WordPress development:

- Using Context7 MCP to fetch WordPress documentation
- Running `ddev wp plugin check` to verify compliance
- Following WordPress coding standards
- Best practices for plugin development

See [`.claude/claude.md`](.claude/claude.md) for details.

## 🤝 Contributing

This repository serves as an educational example. Feel free to:

- Fork and experiment
- Study the commit history to understand the development process
- Use as a template for your own WordPress plugins

## 📄 License

This project is licensed under the GPL v2 or later - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Matt Mullenweg** - Original Hello Dolly plugin creator
- **WordPress Community** - For maintaining excellent documentation
- **Plugin Check Team** - For creating the validation tool
- **Context7** - For providing up-to-date WordPress documentation via MCP

## 🔗 Resources

- [WordPress Plugin Handbook](https://developer.wordpress.org/plugins/)
- [WordPress Coding Standards](https://developer.wordpress.org/coding-standards/)
- [Plugin Check Documentation](https://wordpress.org/plugins/plugin-check/)
- [WP-CLI Documentation](https://wp-cli.org/)

---

**Note**: This repository demonstrates WordPress plugin development best practices through the lens of fixing a classic example plugin. The commit history shows the complete journey from identifying issues to implementing proper solutions.
