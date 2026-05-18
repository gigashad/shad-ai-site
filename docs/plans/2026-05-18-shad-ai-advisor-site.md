# Shad.ai Advisor Website Implementation Plan

> For Hermes: implement this directly in the existing Astro static site, keeping the diff small and deployable through GitHub Pages.

Goal: Turn shad.ai from a tiny personal miniblog into a static advisor website for Shad, in partnership with Giga, with clear proof, offers, booking paths, current projects, and links to X/Substack/Telegram.

Architecture: Keep the existing Astro project in `miniblog-main`. Replace the homepage with a single strong advisor landing page, update constants/header metadata, add CNAME and GitHub Pages workflow. Avoid a CMS until the content volume demands it.

Tech Stack: Astro 5, Tailwind CSS, static output, GitHub Actions, GitHub Pages/custom domain.

---

## Constraints

- Static and simple.
- Mostly/free hosting.
- GitHub-backed.
- Must be credible enough to put in X bio.
- Must be easy to edit as exact tweets, speeches, media, pricing, and booking links are confirmed.

## Implementation

1. Fix broken build by adding `EMAIL` to `src/consts.ts`.
2. Update constants for Shad.ai advisor positioning and links.
3. Replace `src/pages/index.astro` with a single-page advisor website:
   - hero
   - what Shad does inside companies
   - proof timeline / engagements
   - current work: Giga, Zip Code, Tower.com, Altworth
   - predictions / hit tweets placeholders
   - media and speeches placeholders
   - advisory packages / pricing bands
   - booking/contact CTA
4. Simplify `src/components/Header.astro` into section anchors and external links.
5. Add `public/CNAME` with `shad.ai` for GitHub Pages custom domain.
6. Add `.github/workflows/deploy.yml` to build from `miniblog-main` and publish to GitHub Pages.
7. Build locally with `npm run build`.
8. Review diff and commit.
9. Push branch/main to GitHub.
10. Enable Pages deployment from GitHub Actions when possible. If private repo Pages blocks on plan/visibility, note the remaining toggle.

## Open content slots

Need user confirmation later:

- exact Giga partnership wording
- exact booking link if not `mailto:shad@shad.ai`
- exact advisory rates
- exact hit tweet URLs/screenshots
- exact prediction receipts
- exact speech/media links
- whether repo should be public for free GitHub Pages if required

## Verification

- `npm run build` passes.
- `dist/CNAME` exists.
- GitHub Actions workflow exists.
- Homepage contains all requested content categories.
- No broken internal import remains.
