# Kavin Deshpande — Interactive Portfolio

A responsive portfolio built with Next.js App Router, TypeScript, Tailwind CSS v4, Motion for React, and Lucide icons. The original visual system is preserved, with interactive project detail panels, a Japanese intro toggle, and a Pac-Man-inspired personal-memory maze.

## Run locally

Requirements: Node.js 20.9 or newer.

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Interactions

- Click the name in the hero to switch between English and beginner/N4-friendly Japanese.
- Select a project card to read its summary, tools, and languages. Enter optional GitHub and live-demo URLs; these are saved in local browser storage.
- Use the arrow keys or on-screen controls to navigate the mini maze and collect treats.
- Each collected treat unlocks a personal-memory card. Upload an image for a memory; images are stored in browser local storage on that device. Keep images under 3 MB.

## Customize

- Main page and project details: `app/page.tsx`
- Styling and responsive rules: `app/globals.css`
- Resume: `public/Kavin_Deshpande_CV.pdf`
- Memory labels: the `memories` array in `app/page.tsx`

Project links and memory images are stored locally in the browser. They are not uploaded to a server and will not automatically appear on another visitor's device. To publish permanent project links for every visitor, set the URLs in the `projects` array before deployment. For shared personal photos, add image files to `public/` and reference them in the `memories` data rather than relying on browser uploads.


## Updating your content

- Replace `public/Kavin_Deshpande_CV.pdf` with your latest CV, keeping this exact filename so the View CV link continues to work.
- Edit the `projects` array near the top of `app/page.tsx` to update project summaries, tools, languages, GitHub URLs, and live-demo URLs.
- Edit the `experience-list` section in `app/page.tsx` to add, remove, or update experience timeline entries. Copy an existing `motion.article` with class `experience-item` and update its text and tags.
- The Japanese name/introduction toggle remains on your name. The explanatory “Click my name…” hint has been removed to encourage visitors to discover it.
- Personal maze memories are configured in the `memories` array in `app/page.tsx`; uploaded photos are handled by the maze UI in the browser. For public deployment, add permanent image files under `public/` and reference those paths if you want every visitor to see the same photos.

## Deploying to Vercel

1. Push this project to a GitHub repository (include `package.json`, `app/`, `public/`, and the config files; do not upload `node_modules/` or `.next/`).
2. In Vercel, choose **Add New → Project**, import the GitHub repository, and keep the detected Next.js settings.
3. Select **Deploy**. No environment variables are required for the current portfolio.
4. For future updates, commit and push to the connected GitHub branch; Vercel will redeploy automatically.

Netlify can also host Next.js, but Vercel is the simpler default for this project because it is built with Next.js.
