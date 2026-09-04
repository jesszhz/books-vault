# books-vault

Reading log used in [personal-website-v2](https://github.com/jesszhz/personal-website-v2) as a git submodule mounted at `content/`.

## Layout

```
books-vault/
├── content/
│   ├── books/           # one *.md per book
│   └── covers/          # local-fallback cover jpgs
├── templates/
│   └── book.md          # Obsidian template for new book notes
└── README.md
```

## Adding a book

1. Cmd-N → create new `book` template 
2. Rename the note to `kebab-case-title.md` and move it into `content/books/`
3. Fill title, author, genre, ISBN, `word_count`
4. If today is the first read, leave the pre-filled date; otherwise edit it
5. Push (Obsidian Git plugin, or `git push` from the terminal)

## Rereads

Append the new date to `read_dates` (chronological, oldest first).

## Frontmatter schema

```yaml
---
title: The Left Hand of Darkness
author: Ursula K. Le Guin
genre: [sci-fi, literary]
isbn: 9780441478125          # drives cover URL via Open Library
cover: piranesi.jpg          # optional; overrides automatic cover lookup
read_dates:
  - 2020-06-22
  - 2023-01-15
  - 2024-11-03
favorite: true
word_count: 78000            # site derives reading time at ~250 wpm
---

Free-form review / notes go here.
```

- `title`, `author`, `read_dates` are required
- Everything else is optional!
- If the book isn't on Open Library, drop a jpg in `content/covers/` and set
  `cover: <filename>`