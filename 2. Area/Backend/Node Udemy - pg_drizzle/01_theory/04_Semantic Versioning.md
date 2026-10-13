---
tags:
  - theory
  - versioning
---


Let's take the example of Express.js versions:

`4.18.2`

It is made up of **3 parts**:

---

###  patch version  (`.2`)
- Optional updates (can skip without issues)
- fully backward compatible 

### Minor version (`.18`)
- **Critical bug fixes** such as security updates or new features
- Backward compatible fully

### Major version (`4`)
- If your app was built on version 4, updating to version 5 will **likely break** your code.
- Avoid updating this for existing projects.
- Update only when starting a **new project**.

---






## Symbols Before Version Numbers

These symbols define how updates are handled in `package.json` whenever you do npm i .

### Example: `^4.18.2`
- **^ (Caret)** → Allows updates for **minor** and **patch** versions.
- Major updates are not applied automatically.

### Example: `~4.18.2`
- **~ (Tilde)** → Allows only **patch updates** (e.g., bug fixes).
- Minor or major updates are not applied automatically.

### Example: `4.18.2` (No Symbol)
- **No symbol** → Version is **locked**.
- No updates (major, minor, or patch) will be applied automatically.
