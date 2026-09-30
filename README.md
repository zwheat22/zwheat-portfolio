# zwheat.com — portfolio site

Plain HTML/CSS, no build step required. Three pages: About (`index.html`),
Projects (`projects.html`), Resume (`resume.html`), sharing one stylesheet
(`style.css`) and a footer with your contact info on every page.

## Before you deploy

1. **Fill in your content.** Open `index.html` and `projects.html` in
   any text editor / VS Code and replace the placeholder text (marked
   with HTML comments like `<!-- Replace this with... -->`).
2. **Add your resume.** Drop your resume PDF into `assets/resume.pdf`
   (exact filename). The Resume page already points at that path.
3. **Restyle if you want.** Everything visual — colors, fonts, spacing —
   is controlled by the CSS variables at the top of `style.css`. Change
   those and the whole site updates.

## Deploy to Cloudflare

You already have Node/npm installed. From inside this folder:

```sh
# 1. Install Wrangler (Cloudflare's CLI) if you haven't already
npm install -g wrangler

# 2. Log in — opens a browser to authorize against your Cloudflare account
wrangler login

# 3. Deploy
wrangler deploy
```

That last command reads `wrangler.jsonc`, uploads everything in this
folder, and gives you a live URL like
`https://zwheat-portfolio.<your-subdomain>.workers.dev` immediately.

## Point zwheat.com at it

1. In the [Cloudflare dashboard](https://dash.cloudflare.com), go to
   **Workers & Pages**.
2. Select the `zwheat-portfolio` project.
3. Go to **Settings → Domains & Routes** (or **Custom Domains**,
   depending on what the dashboard calls it when you get there).
4. Add `zwheat.com` (and `www.zwheat.com` if you want that to work too).

Since Cloudflare already manages your domain's DNS, this is a couple of
clicks — no manual DNS record editing needed.

## Making updates later

Edit the files, then just run `wrangler deploy` again from this folder.
Every deploy replaces the live site.

(If you connect this folder to a GitHub repo later, you can set up
auto-deploy on every `git push` instead of running the command by hand
— ask me when you're ready for that and I'll walk you through it.)
