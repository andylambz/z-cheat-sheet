# 📝 Markdown Cheat Sheet – Full Syntax

## 📚 Headings

```markdown
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---

## ✍️ Text Formatting

```markdown
**Bold**
*Italic*
***Bold & Italic***
~~Strikethrough~~
`Inline code`
```

---

## 📋 Lists

### Unordered List

```markdown
- Item 1
- Item 2
  - Subitem
* Item with asterisk
```

### Ordered List

```markdown
1. First item
2. Second item
   1. Nested item
```

---

## 🔗 Links & Images

```markdown
[Link text](https://example.com)
![Alt text](https://example.com/image.jpg)
<https://example.com>         # Auto-link
```

---

## 📦 Code Blocks

### Inline Code

```markdown
Use `npm install` to install packages.
```

### Fenced Code Block

<pre>
```js
function greet() {
  console.log("Hello Markdown!");
}
```
</pre>

### Indented Code Block

```markdown
    This is an indented code block.
```

---

## 📐 Tables

```markdown
| Name  | Age | Job       |
|-------|-----|-----------|
| An    | 25  | Developer |
| Bình  | 30  | Designer  |
```

---

## 📌 Blockquotes

```markdown
> This is a blockquote.
>> Nested blockquote.
```

---

## 📎 Horizontal Rule

```markdown
---
***
___
```

---

## ✅ Task Lists (GitHub-flavored)

```markdown
- [x] Task completed
- [ ] Task pending
```

---

## 🧠 Comments (Invisible)

```markdown
<!-- This is a comment -->
```

---

## 🧩 Extended Syntax (GitHub & Markdown processors)

### Footnotes

```markdown
Here is a footnote reference[^1].

[^1]: This is the footnote content.
```

### Definition Lists

```markdown
Term 1
: Definition 1

Term 2
: Definition 2
```

### Abbreviations

```markdown
*[HTML]: HyperText Markup Language
```

### Emoji (GitHub only)

```markdown
:smile: :rocket: :fire:
```

---

## 🧭 HTML in Markdown

```markdown
<div style="color: red;">This is red text</div>
```

→ Useful for styling or layout tweaks.

---

## 📂 File Links (GitHub only)

```markdown
[View file](./path/to/file.txt)
```

---

## 🧪 Math (if supported)

```markdown
$$
E = mc^2
$$
```

→ Requires Markdown engine with LaTeX support (e.g., Jupyter, Obsidian)

---

## 📌 Escaping Characters

```markdown
\*Not italic\*
\# Not a heading
```

→ Use backslash `\` to escape Markdown symbols.
