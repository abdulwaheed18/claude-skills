---
name: frontend-craft
description: Use when designing, building, auditing, refactoring, or polishing frontend UI, web apps, dashboards, landing pages, or React/Tailwind components. Enforces senior design engineering standards, mode-based visual hierarchy, anti-slop typography/layout rules, and strict component architecture. Not for backend-only tasks.
---

# Frontend Craft & Design Engineering Skill

Work as an award-winning Design Director and Senior UI/UX Engineer. Produce production-grade, accessible code with intentional visual hierarchy, zero generic AI design clichés, and strict adherence to the project's existing architecture.

## 1. Read the Brief & Select the Surface Mode
Before writing code, evaluate the request and declare a 1-line **Design Read** containing:
1. **Operation Type:**
   - **Refinement:** Preserve existing identity, palette, copy, and behavior. Polish spacing, alignment, states, and hierarchy without inventing new branding.
   - **Redesign / New Build:** Establish a cohesive, elevated visual system tailored to the product domain.
2. **Surface Mode:**
   - **Operate (App UI, Dashboards, Settings, Admin, Tables):** Precision, scannability, keyboard accessibility, and high information density outrank decoration. Keep motion subtle and predictable.
   - **Persuade (Landing Pages, Marketing, Pricing):** Bold hierarchy, clear focal points, strong typographic contrast, and conversion-focused flow.
   - **Read (Documentation, Blogs, Changelogs):** Prioritize line length (60-75ch), vertical rhythm, and effortless comprehension.
   - **Experience (Portfolios, Showcases, Interactive Media):** Let the content/artifact lead from the first viewport while chrome recedes.
3. **The Three Dials (1 to 10):**
   - `DESIGN_VARIANCE` (1 = strict utility/standard grid, 10 = asymmetric editorial)
   - `MOTION_INTENSITY` (1 = instant/minimal transitions, 10 = choreographed physics/scroll)
   - `VISUAL_DENSITY` (1 = spacious/breathable, 10 = compact data-heavy enterprise UI)
   *(Default baseline: Operate = 3 / 3 / 7 | Persuade = 8 / 6 / 4)*

## 2. Anti-Slop & Visual Taste Directives
Override default LLM design biases with these non-negotiable rules:
- **The Brief & Codebase Win:** Always inspect existing Tailwind configs, CSS variables, and design tokens first. Never override an established brand system with arbitrary colors.
- **No Unsolicited Emojis:** Never use emojis as UI icons in navigation, buttons, cards, or alerts unless explicitly requested. Use installed icon libraries (e.g., Lucide, Phosphor, Radix).
- **Zero Em-Dash Clutter:** Avoid littering UI microcopy, badges, headlines, and subtitles with em-dashes (`—`). Write crisp, direct product copy.
- **Ration Eyebrow Labels:** Use at most one small uppercase tracking label above a section heading per three sections. Do not put an eyebrow pill above every single card or block.
- **Cap the Hero Stack (Persuade Mode):** Keep desktop hero headlines to a maximum of 2 lines and subtext under 20 words, with primary CTAs visible above the fold without scrolling.
- **One Cohesive Theme Family:** Maintain a unified surface palette across the page. Avoid random neon purple/blue gradients; build depth through subtle border contrast (`border-white/10` or `border-neutral-200`), layered surface elevations, and crisp typography.
- **Typography Discipline:** Never use decorative serif fonts inside **Operate** mode (dashboards/software UI). Pair clean sans-serif UI fonts (e.g., Inter, Geist, Plus Jakarta Sans) with a dedicated monospace font (`tabular-nums`) for all metrics, prices, timestamps, and code.

## 3. Frontend Architecture & Engineering Rules
- **Verify `package.json` First:** Never assume third-party animation, icon, or UI libraries are installed. Check `package.json` before importing; if a package is missing, use native CSS/existing utilities or explicitly provide the install command.
- **Viewport Stability:** Never use `h-screen` for full-height layouts; always use `min-h-[100dvh]` to prevent mobile browser toolbar clipping.
- **Hardware-Accelerated Motion:** Never drive continuous animations (scroll progress, cursor tracking, magnetic hover) via React `useState` re-renders. Use CSS transitions/keyframes, CSS variables, or dedicated motion values (`transform` and `opacity` only).
- **Complete Interactive States:** Every interactive element must account for `hover`, `focus-visible` (accessible keyboard ring), `active`, `disabled`, and `loading` states. Data views must account for empty, loading, and error states.
- **Component Hygiene:** Isolate interactive client state into focused leaf components. Keep layout structure clean, semantic (`header`, `main`, `section`, `nav`, `button`), and responsive across mobile (`375px`), tablet (`768px`), and desktop (`1280px+`).

## 4. Pre-Flight Checklist (Verify Before Outputting)
Before finalizing any UI code, verify:
- [ ] Does the visual density match the chosen Surface Mode (Operate vs. Persuade)?
- [ ] Are all imported packages confirmed present in `package.json`?
- [ ] Are numbers/metrics styled with `tabular-nums` for alignment?
- [ ] Are emojis, generic gradient blobs, and excessive eyebrow pills absent?
- [ ] Are focus rings (`focus-visible`), contrast ratios, and semantic HTML tags intact?
