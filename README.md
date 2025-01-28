# Emoji List API 🌟

A lightweight API to fetch emojis and their metadata. Data is stored in static JSON files for easy access.

---

## Base URL
All endpoints are served from:  
`https://morfusee.github.io/emoji-list-api/`

---

## Quick Start

### Fetch All Emojis
```javascript
fetch("https://morfusee.github.io/emoji-list-api/emojis.json")
  .then(response => response.json())
  .then(data => console.log(data));
```

### Fetch by Category
Replace `{category}` with: `faces`, `activities`, `nature`, `objects`, or `places`.  
```javascript
// Example: Fetch nature emojis
fetch("https://morfusee.github.io/emoji-list-api/categories/{category}.json")
  .then(response => response.json())
  .then(data => console.log(data));
```

---

## Endpoints

| Category     | Path                                                                 |
|--------------|----------------------------------------------------------------------|
| All Emojis   | [`/emojis.json`](https://morfusee.github.io/emoji-list-api/emojis.json) |
| Faces        | [`/categories/faces.json`](https://morfusee.github.io/emoji-list-api/categories/faces.json) |
| Activities   | [`/categories/activities.json`](https://morfusee.github.io/emoji-list-api/categories/activities.json) |
| Nature       | [`/categories/nature.json`](https://morfusee.github.io/emoji-list-api/categories/nature.json) |
| Objects      | [`/categories/objects.json`](https://morfusee.github.io/emoji-list-api/categories/objects.json) |
| Places       | [`/categories/places.json`](https://morfusee.github.io/emoji-list-api/categories/places.json) |

---

## Emoji Schema
All responses follow this structure:

| Field                 | Type               | Description                                                                 | Nullable |
|-----------------------|--------------------|-----------------------------------------------------------------------------|----------|
| `emoji`               | `string`           | The emoji character (e.g., `"😀"`)                                          | No       |
| `hexcode`             | `string`           | Unicode hexcode (e.g., `"1F600"`)                                           | No       |
| `group`               | `string`           | Broad category (e.g., `"Smileys & Emotion"`)                                | No       |
| `subgroup`            | `string`           | Sub-category (e.g., `"face-smiling"`)                                       | No       |
| `annotation`          | `string`           | Human-readable name (e.g., `"grinning face"`)                               | No       |
| `tags`                | `string[]`         | Searchable tags (e.g., `["happy", "smile"]`)                                | No       |
| `shortcodes`          | `string[]`         | Common shortcodes (e.g., `[":grinning:"]`)                                  | No       |
| `emoticons`           | `string[]`         | Legacy emoticon representations (e.g., `[":D"]`)                            | No       |
| `directional`         | `boolean`          | Whether the emoji has text directionality (e.g., `false`)                   | No       |
| `variation`           | `boolean`          | Whether a variation exists (e.g., `true`)                                   | No       |
| `variationBase`       | `string`           | Base emoji for variations (e.g., `"👋"` for `"👋🏻"`)                        | Yes      |
| `unicode`             | `number`           | Unicode version number (e.g., `15.0`)                                       | No       |
| `order`               | `number`           | Sorting index in Unicode releases                                           | No       |
| `skintone`            | `string`           | Skin tone modifier (e.g., `"light"`)                                        | Yes      |
| `skintoneCombination` | `string[]`         | Possible skin tone combinations (e.g., `["light", "medium"]`)               | Yes      |
| `skintoneBase`        | `string`           | Base emoji without skin tone (e.g., `"👍"` for `"👍🏽"`)                    | Yes      |
