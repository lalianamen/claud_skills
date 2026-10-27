# claud_skills

Project skills for Claude Code. Anything in `.claude/skills/<name>/SKILL.md` loads
automatically when Claude Code runs in this repo; call it as `/<name>`.

## marketing (Anthropic, v1.2.0, Apache-2.0)
Copied from https://github.com/anthropics/knowledge-work-plugins/tree/main/marketing
(license: `.claude/skills/LICENSE-marketing`).

| Skill | What it does | Простой запрос |
|---|---|---|
| `/campaign-plan` | Campaign brief: goals, audience, channels, content calendar, metrics | `/campaign-plan план рекламы ремонта отопления в Лос-Анджелесе на ноябрь–февраль, бюджет $1000/мес` |
| `/content-creation` | Blog, social, email, landing page, press release copy | `/content-creation статья для сайта: 5 признаков, что кондиционеру нужен ремонт` |
| `/draft-content` | Same, with headline options and SEO tips | `/draft-content пост в Instagram про сезонное обслуживание печи, 3 варианта заголовка` |
| `/competitive-brief` | Competitor positioning and messaging gaps | `/competitive-brief сравни меня с 3 HVAC-компаниями в Глендейле` |
| `/email-sequence` | Multi-email nurture / onboarding / win-back flows | `/email-sequence 3 письма клиентам, которые не обслуживали кондиционер больше года` |
| `/seo-audit` | Keyword, on-page, technical and competitor SEO audit | `/seo-audit проверь сайт masterdomhvac.com по запросу "AC repair Los Angeles"` |
| `/performance-report` | Marketing performance report with recommendations | `/performance-report отчёт по рекламе за октябрь: вот цифры из Google Ads …` |
| `/brand-review` | Check copy against brand voice and flag risky claims | `/brand-review проверь текст объявления: …` |

## stop-slop (Hardik Pandya, MIT)
Copied from https://github.com/hardikpandya/stop-slop (license: `.claude/skills/stop-slop/LICENSE`).

| Skill | What it does | Простой запрос |
|---|---|---|
| `/stop-slop` | Strip AI writing patterns (filler phrases, formulaic structures, passive voice) from prose | `/stop-slop перепиши, чтобы не звучало как ИИ: …текст…` |

## ui-ux-pro-max (Next Level Builder, MIT)
Copied from https://github.com/nextlevelbuilder/ui-ux-pro-max-skill (commit 28b3b8d,
license: `.claude/skills/ui-ux-pro-max/LICENSE`). Left out: `scripts/tests`. Changed: script
path in `SKILL.md` from `${CLAUDE_PLUGIN_ROOT}/.claude/...` to `.claude/...` (project install).
Needs Python 3 for its search script.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/ui-ux-pro-max` | UI/UX guidance: styles, palettes, fonts, UX rules, accessibility, per-stack tips | `/ui-ux-pro-max подбери стиль, цвета и шрифты для сайта HVAC-компании в Лос-Анджелесе` |

## remotion (Remotion, v4.0.539)
Copied from https://github.com/remotion-dev/skills (commit 30d4553), same files `npx skills add
remotion-dev/skills` installs. The skills repo has no license file of its own; it is part of the
Remotion monorepo under the Remotion License (https://github.com/remotion-dev/remotion/blob/main/LICENSE.md):
Remotion itself is free for individuals and for-profit companies with up to 3 employees, larger
companies need a company license. Skills write and run a Remotion (React) video project; they need
Node.js, and `/remotion-render` needs the machine to render video.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/remotion-best-practices` | Router: picks the right Remotion skill when unsure | `/remotion-best-practices сделай 15-секундное видео про бесплатный пример C-20 HVAC` |
| `/remotion-create` | New Remotion project or video | `/remotion-create промо-ролик 20 секунд для licena.us, вертикальный 9:16` |
| `/remotion-markup` | Animation, layout, text, audio, effects in the video code | `/remotion-markup добавь анимированный заголовок "Get your HVAC license"` |
| `/remotion-studio` | Opens a live preview of the video | `/remotion-studio` |
| `/remotion-render` | Exports the finished MP4 or a still image | `/remotion-render сохрани видео в MP4 1080x1920` |
| `/remotion-captions` | Transcribes speech and adds animated subtitles | `/remotion-captions сделай субтитры на английском к моему видео` |
| `/remotion-maps` | Animated maps, routes, markers | `/remotion-maps карта Лос-Анджелеса с зонами, где я работаю` |
| `/remotion-multimedia` | Trim, crop, read metadata of video files | `/remotion-multimedia обрежь видео до первых 30 секунд` |
| `/remotion-interactivity` | Makes video values editable in Studio | `/remotion-interactivity сделай цену и текст редактируемыми в Studio` |
| `/remotion-saas` | Builds an app that generates videos | `/remotion-saas приложение, которое делает видео-отзыв из текста клиента` |
| `/remotion-docs` | Searches Remotion documentation | `/remotion-docs как добавить фоновую музыку` |
| `/remotion-upgrade` | Updates Remotion packages in a project | `/remotion-upgrade обнови Remotion до последней версии` |

## find-skills (Vercel, MIT)
Copied from https://github.com/vercel-labs/skills/tree/main/skills/find-skills (commit 533c7df,
license: `.claude/skills/find-skills/LICENSE`). Uses the `npx skills` CLI (needs Node.js) and the
https://skills.sh catalog. Its step 6 installs with `-g -y` (global, no confirmation): ask Claude to
show the skill and install it into this repo instead.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/find-skills` | Searches the skills.sh catalog for a skill that fits a task, checks installs and source, shows the install command | `/find-skills найди скилл для Google Business Profile и отзывов` |

## arena (pstack by Cursor, MIT)
Copied from https://github.com/backnotprop/pstack (standalone mirror of
https://github.com/cursor/plugins/tree/main/pstack, commit f51fdeb, license: `.claude/skills/arena/LICENSE`).
Also copied the four short principle skills arena points to: `principle-separate-before-serializing-shared-state`,
`principle-redesign-from-first-principles`, `principle-laziness-protocol`, `principle-prove-it-works`.
Left out: `poteto-mode` (a whole working persona; arena only cites it for picking subagent effort).
Arena runs only when called as `/arena`. It starts several subagents, so one run costs several times
the tokens of doing the task once. Its default runner list names Grok models; in Claude Code all
runners fall back to Claude.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/arena` | Runs 2+ subagents on the same task in parallel, a separate judge scores them, then merges the best parts into one result | `/arena напиши 3 варианта заголовка и подзаголовка для главной licena.us` |

## claude-code-setup (Anthropic, v1.0.0, Apache-2.0)
Copied from https://github.com/anthropics/claude-plugins-official/tree/main/plugins/claude-code-setup
(commit 41f619d, license: `.claude/skills/claude-automation-recommender/LICENSE`). The plugin holds one skill.
Read-only: it scans a project and recommends, it does not change files.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/claude-automation-recommender` | Scans a project and recommends the top 1-2 Claude Code automations per type: hooks, skills, subagents, plugins, MCP servers | `/claude-automation-recommender посоветуй автоматизации Claude Code для репозитория LLICENA` |

## openreel (written here; app by Augani, MIT)
Our own setup and usage guide for OpenReel Video (https://github.com/Augani/openreel-video), based
on its docs/AGENT-GUIDE.md. OpenReel has no skill of its own; Claude drives it through the desktop
app's local MCP server, so it works only with Claude running on the same computer as the app.

| Skill | What it does | Простой запрос |
|---|---|---|
| `/openreel` | Connects OpenReel Video to Claude and edits the open project: cut, captions, text, audio, export | `/openreel обрежь видео до 30 секунд, добавь английские субтитры и экспортируй 1080x1920` |
