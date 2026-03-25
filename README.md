# Engineering Framework Template

A ready-to-use template repository for customizing your organization's engineering checklist framework on [Engineering Framework](https://engineeringframework.dev).

Fork this repository, customize the content to match your organization's standards, and connect it via GitHub Sync in your organization's settings. Engineering Framework will pull your framework definition and use it in place of the system defaults for all new projects.

---

## Getting Started

### 1. Fork this repository

Click **Use this template** (or fork it) into your organization's GitHub account.

### 2. Customize the content

Edit `framework.yml` to match your organization's engineering standards. Add, remove, or reorder categories, subcategories, and checklist items. Update or replace the definition and template markdown files to reflect your internal guidance.

### 3. Connect to Engineering Framework

1. Go to **Dashboard → Settings → GitHub Sync** in your Engineering Framework organization
2. Enter your repository owner, name, and branch
3. Create a GitHub Personal Access Token with **Contents: Read** access and paste it in
4. Click **Save Configuration**, then **Sync Now** to pull your framework

### 4. (Optional) Set up auto-sync on push

After saving, copy the **Webhook URL** and **Webhook Secret** from the settings page and add them to your repository under **Settings → Webhooks**. Set the content type to `application/json` and subscribe to **Push** events only. Your framework will sync automatically on every push to the configured branch.

---

## Repository Structure

```
your-framework-repo/
├── README.md
├── LICENSE
├── framework.yml              # Required — defines the full category/item hierarchy
├── definitions/
│   └── {item-slug}.md         # One file per checklist item with hasDefinition: true
└── templates/
    └── {template-slug}.md     # One file per template listed in framework.yml
```

### `framework.yml`

The manifest file defines the complete hierarchy. It is validated on every sync — errors will be reported in the sync status and no changes will be applied until the file is valid.

**Top-level structure:**

```yaml
categories:
  - name: "Category Name"
    slug: "category-slug"        # lowercase, hyphens only
    order: 1
    description: "Optional description"
    subcategories:
      - name: "Subcategory Name"
        slug: "subcategory-slug"
        order: 1
        items:
          - name: "Checklist Item Name"
            slug: "item-slug"    # must be unique across all items
            order: 1
            optional: false      # if true, item can be skipped
            hasDefinition: true  # loads from definitions/{item-slug}.md
            hasTemplate: true    # requires templateSlug to be set
            templateSlug: "template-slug"

templates:
  - slug: "template-slug"
    name: "Human-readable Template Name"
    file: "templates/template-slug.md"
```

**Slug rules:**
- Must match `^[a-z0-9-]+$` (lowercase letters, digits, hyphens only)
- Must be unique within its scope (item slugs are globally unique; template slugs are globally unique)

**Validation rules enforced on sync:**
- All slugs must be unique within their level
- `hasTemplate: true` requires `templateSlug` to be set
- Every `templateSlug` referenced in items must exist in the `templates` array
- Every `file` in `templates` must exist in the repository

### `definitions/`

One markdown file per checklist item that has `hasDefinition: true`. The filename must be `{item-slug}.md`.

Definitions provide guidance to engineers about what the checklist item means, why it matters, and how to complete it. They are displayed in-app when a user opens a checklist item for detail.

### `templates/`

One markdown file per template listed in the `templates` array of `framework.yml`. The filename should match the `file` path declared in the manifest.

Templates are reusable document starters that engineers can use when completing a checklist item. They are provided as starting points — engineers fill in the placeholders for their specific project.

---

## Customization Guide

### Adding a new checklist item

1. Add the item to `framework.yml` under the appropriate subcategory
2. If `hasDefinition: true`, create `definitions/{your-item-slug}.md`
3. If `hasTemplate: true`, create `templates/{your-template-slug}.md` and add the template to the `templates` array in `framework.yml`
4. Push to your configured branch — Engineering Framework will sync automatically if you have the webhook configured

### Removing an item

Remove it from `framework.yml`. Existing project checklist items that reference the removed item will remain in those projects but the item will no longer appear in new projects.

### Reordering items

Change the `order` values. Items are sorted numerically by order within their subcategory. Order values do not need to be sequential.

### Renaming an item

Update the `name` field freely — names are display-only and can be changed without affecting existing data. Do **not** change the `slug` of an existing item if it has already been synced and used in projects, as slugs are the identifier that links template items to project checklist items.

---

## What Gets Synced

Engineering Framework syncs the following from your repository:

| What | How |
|------|-----|
| Category hierarchy | From `framework.yml` |
| Checklist items and their flags | From `framework.yml` |
| Item definitions (guidance text) | From `definitions/{slug}.md` |
| Templates (document starters) | From `templates/{slug}.md` |

The sync is a full replacement of your organization's custom framework — each sync reflects the exact state of your repository at that point in time. Deletions in your repository will remove items from future projects (but not from existing projects that already have those items).

---

## Requirements

- A GitHub repository (public or private) accessible by the PAT you provide
- A Personal Access Token with **Contents: Read** scope on the repository
- An Engineering Framework organization on the **Pro** or **Enterprise** plan

---

## License

This template repository is released under the [MIT License](LICENSE). You are free to fork, modify, and use it for any purpose.
