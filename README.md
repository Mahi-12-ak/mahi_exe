# mahi.exe — GitHub Pages edition 🕷️

A responsive, single-page personal website. No build tools or dependencies required.

## Publish with GitHub Pages

1. Create a new GitHub repository (for example, `mahi-exe`).
2. Upload `index.html` to the **root** of the repository. Keep the filename exactly `index.html`.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Choose branch `main` and folder `/ (root)`, then Save.
6. Wait a minute or two. GitHub will show your public website URL in the Pages section.

Anyone with that URL can visit the site. Keep the repository public if using the free GitHub Pages plan.

## What's working

- Responsive navigation and mobile menu
- Dark/light theme (remembered on the visitor's device)
- Share-link button (uses the browser share menu or copies the URL)
- Random thought, advice, chaos, visitor-title and fake-award buttons
- Mood buttons and working four-question quiz with result + reset
- Scrapbook caption shuffle and local photo previews
- Guestbook local demo mode

## Guestbook: local vs shared

Without setup, guestbook messages are saved only in the visitor's own browser. They are **not** visible to other visitors.

To make comments shared across visitors, create a Supabase project and follow `supabase-setup.sql`. Then open `index.html` and replace the two placeholders near the top of its `<script>`:

- `PASTE_SUPABASE_PROJECT_URL`
- `PASTE_SUPABASE_PUBLISHABLE_OR_ANON_KEY`

Use only the project's public publishable/anon key. **Never put a service-role or secret key in frontend code.**

The supplied SQL enables public reading and public posting. That means strangers can submit text, so review the policies and consider moderation, rate limiting or a CAPTCHA before sharing the site widely. Do not collect private information in the guestbook.

## Add scrapbook photos permanently

The photo picker creates previews on the current device only. To publish photos:
1. Create a folder called `images` in your repository.
2. Upload image files into it.
3. Edit the scrapbook cards in `index.html` to use `<img src="images/your-photo.jpg" alt="A short description">` inside each `.photo-frame`.

Only publish photos you have permission to share. Avoid addresses, school details, schedules and other private information.
