# abra-skills

The skill library for **Abra Desktop** — **515 ready-made English skills** across 25 categories, fetched live by the app (Skills view → Skill library) and installable into any workspace with one click.

| Category | id | skills |
|---|---|---|
| Web Development | `web-development` | 24 |
| Backend and APIs | `backend-apis` | 24 |
| Databases | `databases` | 20 |
| Mobile Apps | `mobile-apps` | 20 |
| Game Development | `game-development` | 22 |
| DevOps and Cloud | `devops-cloud` | 22 |
| AI and Machine Learning | `ai-machine-learning` | 24 |
| Data Science | `data-science` | 22 |
| Programming Languages | `programming-languages` | 27 |
| Software Architecture | `software-architecture` | 20 |
| Security | `security` | 20 |
| Design and UX | `design-ux` | 22 |
| Writing and Content | `writing-content` | 24 |
| Marketing and Growth | `marketing-growth` | 24 |
| Business and Strategy | `business-strategy` | 22 |
| Productivity | `productivity` | 18 |
| Education and Tutoring | `education-tutoring` | 18 |
| Creative and Media | `creative-media` | 22 |
| Office and Documents | `office-documents` | 18 |
| Communication | `communication` | 16 |
| Finance and Crypto | `finance-crypto` | 20 |
| Ecommerce | `ecommerce` | 16 |
| Career Development | `career-development` | 16 |
| Automation and Scripting | `automation-scripting` | 20 |
| IoT and Electronics | `iot-electronics` | 14 |

## Format

Each skill is a markdown file with frontmatter:

```
---
name: react-hooks
description: Write correct, performant React function components...
category: web-development
---
# ... Overview / Core guidance / Workflow / Quality bar
```

The app reads `index.json` (manifest) and each file from `raw.githubusercontent.com` — no API keys needed.

## License

MIT — use them, fork them, ship them.
