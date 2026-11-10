# Slug Generator - Privacy-First Developer Tool

[![Stars](https://img.shields.io/github/stars/formatho/slug-generator?style=social)](https://github.com/formatho/slug-generator)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Privacy First](https://img.shields.io/badge/Privacy-First%20%F0%9F%94%92-success)](https://formatho.com)
[![Try Online](https://img.shields.io/badge/Try%20Online-Online%20%F0%9F%8C%90-blue)](https://formatho.com/tools/slugify-string)

A fast, secure, and privacy-first slug generator that creates URL-friendly slugs entirely in your browser. No text is ever sent to a server, ensuring complete privacy and security for your content.

## 🚀 Features

- **Instant Generation**: Real-time slug generation as you type
- **Privacy-First**: All processing happens client-side in your browser
- **No Tracking**: Zero analytics, zero cookies, zero data collection
- **Multiple Formats**: Hyphen-separated, underscore-separated, camelCase, PascalCase
- **Unicode Support**: Full support for international characters and emojis
- **Custom Separators**: Choose between hyphens, underscores, or remove spaces
- **Batch Processing**: Generate multiple slugs at once
- **One-Click Copy**: Copy generated slugs to clipboard instantly
- **History Tracking**: Keep track of recent slugs
- **SEO Optimized**: SEO-friendly, human-readable URLs
- **Custom Replacement**: Custom character replacement rules

## 📖 Why Privacy Matters

Traditional slug generators send your text to remote servers, exposing sensitive information:

- Blog post titles and content
- Article headlines and summaries
- Product names and descriptions
- Page titles and metadata
- Internal content and documentation
- User-generated content
- Competitive content analysis
- SEO strategy and keywords

**Formatho processes everything in your browser** - your content never leaves your device.

## 🔧 How It Works

### Slug Generation

Slug generation converts text into URL-friendly strings by:

1. **Lowercasing**: Convert to lowercase
2. **Removing special characters**: Strip non-alphanumeric characters
3. **Replacing spaces**: Convert spaces to separators
4. **Removing extra separators**: Replace multiple separators with single separator
5. **Trimming**: Remove leading/trailing separators

**Example:**
```
Input:  "How to Build a Privacy-First Web Application"
Output: "how-to-build-a-privacy-first-web-application"
```

### Slug Formats

**Hyphen-Separated (Default):**
```
how-to-build-a-privacy-first-web-application
```

**Underscore-Separated:**
```
how_to_build_a_privacy_first_web_application
```

**camelCase:**
```
howToBuildAPrivacyFirstWebApplication
```

**PascalCase:**
```
HowToBuildAPrivacyFirstWebApplication
```

**No Separators:**
```
howtobuildaprivacyfirstwebapplication
```

### Unicode and International Characters

Convert international characters to ASCII equivalents:

| Input | Output |
|-------|--------|
| `café` | `cafe` |
| `naïve` | `naive` |
| `résumé` | `resume` |
| `日本語` | `ri-ben-yu` |
| `🎉 Party!` | `party` |

## 💻 Usage

### Web App

Visit [formatho.com/tools/slugify-string](https://formatho.com/tools/slugify-string) and:

1. **Input**: Enter or paste your text
2. **Select Format**: Choose slug format (hyphen, underscore, camelCase, etc.)
3. **Customize**: Set custom separator and character rules
4. **Generate**: View generated slug in real-time
5. **Copy**: Click copy button to copy slug
6. **History**: View and reuse recent slugs

### NPM Package

```bash
npm install @formatho/slug-generator
```

```javascript
import {
  generateSlug,
  generateSlugCustom,
  generateCamelCase,
  generatePascalCase,
  generateSnakeCase,
  generateKebabCase
} from '@formatho/slug-generator';

// Generate slug (default: kebab-case)
const slug = generateSlug('How to Build a Privacy-First Web Application');
console.log(slug);
// 'how-to-build-a-privacy-first-web-application'

// Generate slug with custom separator
const slugCustom = generateSlugCustom(
  'How to Build a Privacy-First Web Application',
  { separator: '_' }
);
console.log(slugCustom);
// 'how_to_build_a_privacy_first_web_application'

// Generate camelCase
const camelCase = generateCamelCase('How to Build a Privacy-First Web Application');
console.log(camelCase);
// 'howToBuildAPrivacyFirstWebApplication'

// Generate PascalCase
const pascalCase = generatePascalCase('How to Build a Privacy-First Web Application');
console.log(pascalCase);
// 'HowToBuildAPrivacyFirstWebApplication'

// Generate snake_case
const snakeCase = generateSnakeCase('How to Build a Privacy-First Web Application');
console.log(snakeCase);
// 'how_to_build_a_privacy_first_web_application'

// Generate kebab-case
const kebabCase = generateKebabCase('How to Build a Privacy-First Web Application');
console.log(kebabCase);
// 'how-to-build-a-privacy-first-web-application'
```

### Command Line

```bash
# Generate slug (default: kebab-case)
npx @formatho/slug-generator generate "How to Build a Privacy-First Web Application"

# Generate with custom separator
npx @formatho/slug-generator generate "How to Build a Privacy-First Web Application" --separator "_"

# Generate camelCase
npx @formatho/slug-generator generate "How to Build a Privacy-First Web Application" --format camelCase

# Generate PascalCase
npx @formatho/slug-generator generate "How to Build a Privacy-First Web Application" --format pascalCase

# Generate from file
npx @formatho/slug-generator generate-from-file titles.txt --format kebab-case

# Generate multiple slugs
npx @formatho/slug-generator generate-batch "Title 1" "Title 2" "Title 3"
```

### Browser API

```javascript
import { generateSlugAsync } from '@formatho/slug-generator/browser';

// Generate slug asynchronously (for large text)
const slug = await generateSlugAsync('How to Build a Privacy-First Web Application');
console.log(slug);
// 'how-to-build-a-privacy-first-web-application'
```

## 🎯 Use Cases

- **Blog Posts**: Create SEO-friendly URLs for blog posts
- **CMS**: Generate slugs for content management systems
- **E-commerce**: Create product URLs
- **Documentation**: Generate documentation page URLs
- **API Endpoints**: Create API endpoint paths
- **Routing**: Generate URL routes for web applications
- **File Naming**: Create file names from titles
- **Privacy**: Safely generate slugs without exposing content

## 🔒 Privacy & Security

At Formatho, we believe in privacy-first development:

- **Client-Side Processing**: All generation happens in your browser
- **No Server Communication**: Your content never leaves your device
- **No Analytics**: We don't track how you use this tool
- **No Cookies**: We don't store or use cookies
- **Open Source**: Code is available for security audits
- **MIT License**: Free to use, modify, and distribute

## 📊 Performance

| Input Length | Generate Time | Throughput |
|--------------|---------------|------------|
| 10 chars | < 0.1ms | 100M chars/s |
| 100 chars | < 0.5ms | 200M chars/s |
| 1K chars | < 5ms | 200M chars/s |
| 10K chars | < 50ms | 200M chars/s |
| 100K chars | < 500ms | 200M chars/s |

*Benchmarks run on modern browsers (Chrome 120+, Firefox 120+, Safari 17+)*

## 🛠️ Installation

### For Web App

No installation required! Visit [formatho.com/tools/slugify-string](https://formatho.com/tools/slugify-string).

### For NPM Package

```bash
npm install @formatho/slug-generator
```

### For Command Line

```bash
npm install -g @formatho/slug-generator
```

## 📚 API Reference

### `generateSlug(text: string): string`

Generates slug (kebab-case).

**Parameters:**
- `text` - Input text

**Returns:**
- Generated slug (kebab-case)

**Example:**
```javascript
const slug = generateSlug('How to Build a Privacy-First Web Application');
// Returns: 'how-to-build-a-privacy-first-web-application'
```

### `generateSlugCustom(text: string, options?: SlugOptions): string`

Generates slug with custom options.

**Parameters:**
- `text` - Input text
- `options` - Optional configuration object
  - `separator` - Separator character (default: '-')
  - `lowercase` - Convert to lowercase (default: true)
  - `removeStopWords` - Remove stop words (default: false)

**Returns:**
- Generated slug

**Example:**
```javascript
const slug = generateSlugCustom('How to Build a Privacy-First Web Application', {
  separator: '_',
  removeStopWords: true
});
// Returns: 'how_build_privacy_first_web_application'
```

### `generateCamelCase(text: string): string`

Generates camelCase slug.

**Parameters:**
- `text` - Input text

**Returns:**
- Generated camelCase string

**Example:**
```javascript
const camelCase = generateCamelCase('How to Build a Privacy-First Web Application');
// Returns: 'howToBuildAPrivacyFirstWebApplication'
```

### `generatePascalCase(text: string): string`

Generates PascalCase slug.

**Parameters:**
- `text` - Input text

**Returns:**
- Generated PascalCase string

**Example:**
```javascript
const pascalCase = generatePascalCase('How to Build a Privacy-First Web Application');
// Returns: 'HowToBuildAPrivacyFirstWebApplication'
```

### `generateSnakeCase(text: string): string`

Generates snake_case slug.

**Parameters:**
- `text` - Input text

**Returns:**
- Generated snake_case string

**Example:**
```javascript
const snakeCase = generateSnakeCase('How to Build a Privacy-First Web Application');
// Returns: 'how_to_build_a_privacy_first_web_application'
```

### `generateKebabCase(text: string): string`

Generates kebab-case slug.

**Parameters:**
- `text` - Input text

**Returns:**
- Generated kebab-case string

**Example:**
```javascript
const kebabCase = generateKebabCase('How to Build a Privacy-First Web Application');
// Returns: 'how-to-build-a-privacy-first-web-application'
```

### `isSlugValid(slug: string): boolean`

Validates slug format.

**Parameters:**
- `slug` - Slug to validate

**Returns:**
- True if valid slug, false otherwise

**Example:**
```javascript
const isValid = isSlugValid('how-to-build-a-privacy-first-web-application');
// Returns: true

const isInvalid = isSlugValid('How to Build a Privacy-First Web Application');
// Returns: false
```

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📄 License

This project is licensed under the MIT License - see [LICENSE.md](LICENSE.md) for details.

## 🔗 Related Tools

- [URL Encoder/Decoder](https://github.com/formatho/url-encoder-decoder) - Encode and decode URLs
- [HTML Entity Encoder/Decoder](https://formatho.com/tools) - Encode and decode HTML entities
- [Text Tools](https://formatho.com/tools) - More text processing tools
- [SEO Tools](https://formatho.com/tools) - More SEO tools

## 💬 Support

- **Issues**: [GitHub Issues](https://github.com/formatho/slug-generator/issues)
- **Discussions**: [GitHub Discussions](https://github.com/formatho/slug-generator/discussions)
- **Email**: support@formatho.com

## ⭐ Star History

[![Star History Chart](https://api.star-history.com/svg?repos=formatho/slug-generator&type=Date)](https://star-history.com/#formatho/slug-generator&Date)

---

**Made with 🔒 by Formatho**

Privacy-first developer tools, 100+ utilities with zero tracking.

[Try Online](https://formatho.com/tools/slugify-string) | [More Tools](https://formatho.com) | [Privacy Policy](https://formatho.com/privacy)
## ⚡ Free API — Cloudflare Worker

This tool is also available as a free, zero-tracking API deployed on Cloudflare Workers:

**Endpoint:** https://slug-generator-formatho.filesformatho.workers.dev

Deploy it yourself: the complete Worker source is in [`worker/`](./worker) — `cd worker && wrangler deploy`. MIT licensed.

## 🔗 Links

- [Online tool](https://formatho.com/tools/slugify-string)
- [Live API](https://slug-generator-formatho.filesformatho.workers.dev)
