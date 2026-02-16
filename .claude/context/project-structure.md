---
created: "2026-02-16T19:30:00-05:00"
last_updated: "2026-02-16T19:30:00-05:00"
version: "1.0.0"
author: "Claude Code CCPM"
---

# Project Structure

```
trauma-ai-template/
├── templates/
│   ├── current/                    # Active production templates
│   │   ├── trauma-evidence-synthesis-system-v3.0-2026-01.md  # Master
│   │   ├── journal-club-chalk-talk-template-v2.0-2025-11.md
│   │   ├── topic-research-template-v1.0-2025-12.md
│   │   ├── openevidence-workflow-template-v1.0-2025-01.md
│   │   └── journal-club-simplified-workflow-v1.0-2025-01.md
│   └── archive/                    # Prior versions
├── outputs/
│   ├── topics/                     # Completed topic syntheses
│   │   ├── antibiotic-prophylaxis/
│   │   ├── psh-storming/
│   │   ├── stress-ulcer-prophylaxis/
│   │   ├── hemorrhage-resuscitation/
│   │   ├── spinal-cord-injury/
│   │   └── rib-fractures/
│   └── topic-lists/                # Planning docs
├── epic-ehr/
│   └── current/                    # Active EPIC templates
├── reference/                      # Clinical reference materials
├── personal/                       # Personal workflow docs
├── AI_GUIDE.md                     # AI usage guide
├── CONTRIBUTING.md                 # Contribution guidelines
├── README.md                       # Project documentation
└── .claude/context/                # CCPM context files
```
