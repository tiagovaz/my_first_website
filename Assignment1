# Assignment: Customize Cafe Montreal

**Frontend Development Workshop — Hands-on Practice**

You have received two files: `index.html` and `style.css`. They form a single-page website for a fictional cafe. Your job is to modify both files by following the steps below.

Each step tells you exactly what to change and where. Work through them in order — later steps build on earlier ones.

---

## Before You Start

1. Make sure `index.html` and `style.css` are in the same folder.
2. Open `index.html` in your browser to see the starting page.
3. Keep the browser open. After every step, save your file and refresh the browser to check your work.

---

## Part 1 — CSS Changes (work in style.css)

### Step 1: Change the color scheme

The current page uses a brown and gold palette. Pick a new pair of colors you like and replace them across the stylesheet.

Find every place where these two colors appear and replace them:

- `#6B4226` (brown) — replace with your new dark color
- `#E8A94E` (gold) — replace with your new accent color

There are many places to change. Use your editor's "Find and Replace" feature to catch them all. Refresh the browser after to make sure everything looks consistent.

### Step 2: Change the fonts

The page currently uses `Georgia, serif` on the body. Change it to a different font. You can use any of these or pick your own:

- `Verdana, sans-serif`
- `"Trebuchet MS", sans-serif`
- `"Courier New", monospace`
- `"Palatino", serif`

Find the `body` rule in `style.css` and change the `font-family` line.

### Step 3: Style the nav links differently

Right now the nav links only get an underline on hover. Make them more visible by adding a background color on hover instead.

Find the `.nav-link:hover` rule and replace `text-decoration: underline;` with:

```css
background: rgba(255, 255, 255, 0.15);
border-radius: 4px;
```

### Step 4: Add rounded images to the cards

The card images currently have sharp corners at the top. Add rounded corners to the top of each image.

Find the `.card-img` rule and add this line:

```css
border-radius: 8px 8px 0 0;
```

### Step 5: Make the cards change on hover

The cards currently get a subtle shadow on hover. Make the effect stronger by also moving the card up slightly.

Find the `.card:hover` rule and add this line alongside the existing `box-shadow`:

```css
transform: translateY(-4px);
```

---

## Part 2 — Add a New Section: "Our Team" (work in both files)

You will add a brand new section to the page showing three team members. This requires changes in both `index.html` and `style.css`.

### Step 6: Add a nav link

In `index.html`, find the `<ul class="nav-links">` list. Add a new list item between "About" and "Reviews":

```html
<li><a href="#team" class="nav-link">Team</a></li>
```

Notice that `href="#team"` means we need a section with `id="team"` for this link to work.

### Step 7: Add the Team section in HTML

In `index.html`, add the following section between the closing `</section>` of the About section and the opening of the Reviews section:

```html
<!-- TEAM — id="team" — the nav link href="#team" points here -->
<section id="team" class="section">
  <h2 class="section-title">Our Team</h2>

  <div class="team-grid">

    <div class="team-member">
      <div class="team-photo"></div>
      <h3 class="team-name">Eloise Tremblay</h3>
      <p class="team-role">Founder and Head Roaster</p>
    </div>

    <div class="team-member">
      <div class="team-photo"></div>
      <h3 class="team-name">Marco Silva</h3>
      <p class="team-role">Head Baker</p>
    </div>

    <div class="team-member">
      <div class="team-photo"></div>
      <h3 class="team-name">Aisha Chen</h3>
      <p class="team-role">Barista and Latte Artist</p>
    </div>

  </div>
</section>
```

Save and refresh. You should see the new section, but it will look unstyled. That is expected — we need to add CSS next.

### Step 8: Style the Team section in CSS

Open `style.css` and add the following rules at the bottom of the file, before the footer styles:

```css
/* --- TEAM (class="team-member") ---
   Each team member reuses the same classes. */

.team-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 24px;
  text-align: center;
}

.team-member {
  background: white;
  padding: 24px;
  border-radius: 8px;
}

.team-photo {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: #D5E3D0;
  margin: 0 auto 16px;
}

.team-name {
  font-size: 18px;
  margin-bottom: 4px;
}

.team-role {
  font-size: 14px;
  color: #8C7A66;
}
```

Save and refresh. You should see three styled team member cards with circular photo placeholders.

### Step 9: Update the team colors to match your new palette

In Step 1 you changed the color scheme. Now go back to the team styles you just added and replace `#D5E3D0` (the photo placeholder background) with a color that fits your new palette.

---

## Part 3 — Add Another Section: "Gallery" (work in both files)

Now do it on your own with less guidance. Add a "Gallery" section that shows a grid of images.

### Step 10: Add the nav link

Add a new nav link that points to `href="#gallery"`. Place it between "Team" and "Reviews" in the navigation list.

### Step 11: Create the Gallery section in HTML

Add a new section between Team and Reviews with `id="gallery"`. Inside it, create:

- An `<h2>` with `class="section-title"` and the text "Gallery"
- A `<div>` with `class="gallery-grid"`
- Inside the grid, add 6 `<img>` tags with `class="gallery-img"`. You can use these image URLs or find your own:
  - `https://images.unsplash.com/photo-1442512595331-e89e73853f31?w=400&q=80`
  - `https://images.unsplash.com/photo-1507133750040-4a8f57021571?w=400&q=80`
  - `https://images.unsplash.com/photo-1514066558159-fc8c737ef259?w=400&q=80`
  - `https://images.unsplash.com/photo-1504627298-2b0e060e7674?w=400&q=80`
  - `https://images.unsplash.com/photo-1485808191679-5f86510681a2?w=400&q=80`
  - `https://images.unsplash.com/photo-1554118811-1e0d58224f24?w=400&q=80`
