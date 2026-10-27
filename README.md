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
