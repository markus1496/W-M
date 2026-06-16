# Wedding Invitation Email Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single self-contained HTML email file for wedding guests with ceremony, transport, and reception details, styled to match the physical wedding invitation design system.

**Architecture:** One static `email.html` file with all CSS inlined (email client compatibility). Table-based layout, max 600px wide. Google Fonts loaded via `<link>` in `<head>` for preview — with fallback stacks for clients that block remote fonts. No JavaScript, no images, no external assets except Google Fonts and two Google Maps links.

**Tech Stack:** HTML5, inline CSS, Google Fonts (Cormorant Garamond, Great Vibes, Lato)

---

## File Structure

| File | Responsibility |
|---|---|
| `email.html` | Complete self-contained wedding email |

---

### Task 1: HTML skeleton with fonts and base styles

**Files:**
- Create: `email.html`

- [ ] **Step 1: Create the base HTML file**

Create `email.html` with the following content — this is the full skeleton before any visible sections are added:

```html
<!DOCTYPE html>
<html lang="sk">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Svadobné oznámenie – Aneta & Maroš</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;600&family=Great+Vibes&family=Lato:wght@300;400&display=swap" rel="stylesheet">
</head>
<body style="margin:0;padding:0;background-color:#FAF6F0;font-family:'Lato',Arial,sans-serif;">
  <table role="presentation" width="100%" cellpadding="0" cellspacing="0" style="background-color:#FAF6F0;">
    <tr>
      <td align="center" style="padding:40px 16px;">
        <table role="presentation" width="600" cellpadding="0" cellspacing="0" style="max-width:600px;width:100%;background-color:#FAF6F0;">
          <!-- SECTIONS GO HERE -->
        </table>
      </td>
    </tr>
  </table>
</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Open `email.html` in a browser. Expected: blank cream (#FAF6F0) page with no errors in browser console.

- [ ] **Step 3: Commit**

```bash
git init
git add email.html
git commit -m "feat: add HTML email skeleton with fonts and base layout"
```

---

### Task 2: Header section

**Files:**
- Modify: `email.html` — replace `<!-- SECTIONS GO HERE -->` with header + first placeholder comment

- [ ] **Step 1: Add the header section**

Replace `<!-- SECTIONS GO HERE -->` with:

```html
<!-- HEADER -->
<tr>
  <td style="background-color:#F4DCD6;padding:12px 0;"></td>
</tr>
<tr>
  <td align="center" style="background-color:#FAF6F0;padding:36px 40px 8px;">
    <table role="presentation" width="100%" cellpadding="0" cellspacing="0">
      <tr>
        <td align="center">
          <div style="width:60px;height:1px;background-color:#D4AF37;display:inline-block;vertical-align:middle;"></div>
          <span style="display:inline-block;vertical-align:middle;margin:0 12px;color:#D4AF37;font-size:18px;line-height:1;">✦</span>
          <div style="width:60px;height:1px;background-color:#D4AF37;display:inline-block;vertical-align:middle;"></div>
        </td>
      </tr>
      <tr>
        <td align="center" style="padding-top:24px;">
          <p style="margin:0;font-family:'Cormorant Garamond','Georgia',serif;font-size:32px;font-weight:600;letter-spacing:0.25em;color:#2B2B2B;text-transform:uppercase;">Aneta <span style="color:#D4AF37;">&amp;</span> Maroš</p>
        </td>
      </tr>
      <tr>
        <td align="center" style="padding-top:12px;padding-bottom:24px;">
          <p style="margin:0;font-family:'Great Vibes','cursive';font-size:36px;color:#2B2B2B;">Tešíme sa na Vás</p>
        </td>
      </tr>
      <tr>
        <td align="center">
          <div style="width:60px;height:1px;background-color:#D4AF37;display:inline-block;vertical-align:middle;"></div>
          <span style="display:inline-block;vertical-align:middle;margin:0 12px;color:#D4AF37;font-size:18px;line-height:1;">✦</span>
          <div style="width:60px;height:1px;background-color:#D4AF37;display:inline-block;vertical-align:middle;"></div>
        </td>
      </tr>
    </table>
  </td>
</tr>
<tr>
  <td style="background-color:#F4DCD6;padding:12px 0;"></td>
</tr>

<!-- CONTENT SECTIONS GO HERE -->
```

- [ ] **Step 2: Open in browser and verify**

Open `email.html`. Expected:
- Top blush-pink band
- Gold ornament line (✦ between two lines)
- "ANETA & MAROŠ" in serif uppercase, gold ampersand
- "Tešíme sa na Vás" in script font below
- Second gold ornament line
- Bottom blush-pink band

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add email header with names and decorative ornaments"
```

---

### Task 3: Date section

**Files:**
- Modify: `email.html` — replace `<!-- CONTENT SECTIONS GO HERE -->` with date section + next placeholder

- [ ] **Step 1: Add the date section**

Replace `<!-- CONTENT SECTIONS GO HERE -->` with:

```html
<!-- DATE -->
<tr>
  <td align="center" style="padding:40px 40px 8px;">
    <p style="margin:0;font-family:'Cormorant Garamond','Georgia',serif;font-size:22px;letter-spacing:0.15em;color:#2B2B2B;text-transform:uppercase;">Sobota, 13. jún 2026</p>
  </td>
</tr>

<!-- DIVIDER 1 -->
<tr>
  <td style="padding:24px 40px 0;">
    <div style="height:1px;background-color:#D4AF37;"></div>
  </td>
</tr>

<!-- INFO SECTIONS GO HERE -->
```

- [ ] **Step 2: Open in browser and verify**

Expected: date text centered in serif uppercase below the header, gold divider line underneath.

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add date section and first gold divider"
```

---

### Task 4: Obrad (Ceremony) section

**Files:**
- Modify: `email.html` — replace `<!-- INFO SECTIONS GO HERE -->` with OBRAD section + next placeholder

- [ ] **Step 1: Add the ceremony section**

Replace `<!-- INFO SECTIONS GO HERE -->` with:

```html
<!-- OBRAD -->
<tr>
  <td align="center" style="padding:32px 40px 8px;">
    <p style="margin:0 0 10px;font-family:'Lato',Arial,sans-serif;font-size:11px;font-weight:400;letter-spacing:0.2em;color:#2B2B2B;text-transform:uppercase;">Obrad</p>
    <p style="margin:0 0 4px;font-family:'Lato',Arial,sans-serif;font-size:17px;color:#2B2B2B;">14:00</p>
    <p style="margin:0 0 12px;font-family:'Lato',Arial,sans-serif;font-size:15px;color:#2B2B2B;line-height:1.5;">Kostol v Nižnej Šebastovej</p>
    <a href="https://maps.app.goo.gl/NSPS5DX52Mi8tGUy8" target="_blank" style="font-family:'Lato',Arial,sans-serif;font-size:13px;color:#D4AF37;text-decoration:none;">&#128205; Zobraziť na mape</a>
  </td>
</tr>

<!-- DIVIDER 2 -->
<tr>
  <td style="padding:24px 40px 0;">
    <div style="height:1px;background-color:#D4AF37;"></div>
  </td>
</tr>

<!-- DOPRAVA + HOSTINA GO HERE -->
```

- [ ] **Step 2: Open in browser and verify**

Expected: "OBRAD" label in small caps, "14:00" slightly larger, church name, gold map link below. Gold divider underneath.

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add ceremony section with map link"
```

---

### Task 5: Doprava (Transport) section

**Files:**
- Modify: `email.html` — replace `<!-- DOPRAVA + HOSTINA GO HERE -->` with DOPRAVA section + next placeholder

- [ ] **Step 1: Add the transport section**

Replace `<!-- DOPRAVA + HOSTINA GO HERE -->` with:

```html
<!-- DOPRAVA -->
<tr>
  <td align="center" style="padding:32px 40px 8px;">
    <p style="margin:0 0 10px;font-family:'Lato',Arial,sans-serif;font-size:11px;font-weight:400;letter-spacing:0.2em;color:#2B2B2B;text-transform:uppercase;">Doprava</p>
    <p style="margin:0;font-family:'Lato',Arial,sans-serif;font-size:15px;color:#2B2B2B;line-height:1.7;max-width:420px;">Miesto stretnutia hostí je pri kostole. Po obrade bude pre Vás zabezpečený odvoz autobusom priamo k svadobnej sále.</p>
  </td>
</tr>

<!-- DIVIDER 3 -->
<tr>
  <td style="padding:24px 40px 0;">
    <div style="height:1px;background-color:#D4AF37;"></div>
  </td>
</tr>

<!-- HOSTINA GO HERE -->
```

- [ ] **Step 2: Open in browser and verify**

Expected: "DOPRAVA" label, two-sentence transport description centered, gold divider below.

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add transport section"
```

---

### Task 6: Hostina (Reception) section

**Files:**
- Modify: `email.html` — replace `<!-- HOSTINA GO HERE -->` with HOSTINA section + footer placeholder

- [ ] **Step 1: Add the reception section**

Replace `<!-- HOSTINA GO HERE -->` with:

```html
<!-- HOSTINA -->
<tr>
  <td align="center" style="padding:32px 40px 32px;">
    <p style="margin:0 0 10px;font-family:'Lato',Arial,sans-serif;font-size:11px;font-weight:400;letter-spacing:0.2em;color:#2B2B2B;text-transform:uppercase;">Hostina</p>
    <p style="margin:0 0 4px;font-family:'Lato',Arial,sans-serif;font-size:17px;color:#2B2B2B;">~15:30</p>
    <p style="margin:0 0 12px;font-family:'Lato',Arial,sans-serif;font-size:15px;color:#2B2B2B;line-height:1.5;">Koňareň</p>
    <a href="https://maps.app.goo.gl/g6idJ7YdwRtB57GL6" target="_blank" style="font-family:'Lato',Arial,sans-serif;font-size:13px;color:#D4AF37;text-decoration:none;">&#128205; Zobraziť na mape</a>
  </td>
</tr>

<!-- FOOTER GO HERE -->
```

- [ ] **Step 2: Open in browser and verify**

Expected: "HOSTINA" label, "~15:30", "Koňareň", gold map link. Matches OBRAD section visually.

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add reception section with map link"
```

---

### Task 7: Footer section

**Files:**
- Modify: `email.html` — replace `<!-- FOOTER GO HERE -->` with footer (no further placeholders)

- [ ] **Step 1: Add the footer section**

Replace `<!-- FOOTER GO HERE -->` with:

```html
<!-- FOOTER -->
<tr>
  <td style="background-color:#F4DCD6;padding:28px 40px;" align="center">
    <p style="margin:0;font-family:'Lato',Arial,sans-serif;font-size:13px;color:#2B2B2B;letter-spacing:0.1em;">Tešíme sa na Vás &nbsp;·&nbsp; Aneta &amp; Maroš</p>
  </td>
</tr>
```

- [ ] **Step 2: Open in browser and do a full visual review**

Open `email.html`. Check the complete email top to bottom:
- Top blush band → gold ornament → serif names → script subtitle → gold ornament → blush band
- Date in serif
- Gold divider → OBRAD section → map link
- Gold divider → DOPRAVA section
- Gold divider → HOSTINA section → map link
- Blush footer with closing text

All text should be charcoal (#2B2B2B). Dividers and map links should be gold (#D4AF37). Background cream (#FAF6F0). Header/footer bands blush (#F4DCD6).

Resize browser window to ~375px wide (mobile) — layout should stay readable and centered.

- [ ] **Step 3: Commit**

```bash
git add email.html
git commit -m "feat: add footer — wedding email complete"
```

---

## Done

The complete `email.html` is ready to paste into any email client (Gmail, Outlook, Mailchimp, etc.) or send directly.
