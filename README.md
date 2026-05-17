# 🤖 AI Job Applier Dashboard

A local-first web dashboard to manage your entire job search from one place — upload resume, maintain a structured profile, track applications by portal, and let AI fill job forms using your profile data.

## 📁 Project Structure

```
jobsearch/
├── job-applier.html       ← Main dashboard (open in browser)
├── profile.json           ← YOUR candidate profile — fill this first!
├── applications.json      ← Daily application log (add entries as you apply)
└── README.md              ← This file
```

## 🚀 How to Run Locally

1. **Clone this repo**
   ```bash
   git clone https://github.com/ankitrhll9/jobsearch.git
   cd jobsearch
   ```

2. **Open the dashboard**
   - Double-click `job-applier.html` — OR —
   - Use VS Code + [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer): right-click `job-applier.html` → **Open with Live Server**
   - Dashboard runs at `http://127.0.0.1:5500/job-applier.html`

3. **Fill your profile**
   - Open `profile.json` in any text editor or VS Code
   - Fill every blank field — especially: `email`, `phone`, `total_years`, `current_ctc_lpa`, `expected_ctc_lpa`, `current_company`
   - Save the file — the dashboard reads it on load (when served via Live Server)

## 🧠 AI Application Workflow (Automation Logic)

When you want AI (e.g., a browser automation script or AI agent) to apply to jobs on your behalf:

1. **Read `profile.json`** — extract all structured candidate data
2. **Read uploaded resume** — extract additional details; cross-check with JSON
3. **Open portal** — Naukri, Instahyre, LinkedIn, Indeed, etc.
4. **Match form fields** to profile JSON keys
5. **Fill automatically** where data is present and unambiguous
6. **⚠️ STOP & ASK** if any field is blank, conflicting, or uncertain — prompt user to update `profile.json`
7. **Submit** and write a new entry in `applications.json`

## 🌐 Supported Job Portals

### India-focused
| Portal | URL |
|--------|-----|
| Naukri | https://www.naukri.com |
| Instahyre | https://www.instahyre.com |
| LinkedIn Jobs | https://www.linkedin.com/jobs |
| Indeed India | https://in.indeed.com |
| Shine | https://www.shine.com |
| TimesJobs | https://www.timesjobs.com |
| Wellfound | https://wellfound.com |

### Remote-first
| Portal | URL |
|--------|-----|
| Remote.co | https://remote.co |
| Remotive | https://remotive.com |
| Working Nomads | https://www.workingnomads.com |
| Jobgether | https://jobgether.com |
| We Work Remotely | https://weworkremotely.com |

## 📋 Common Fields Asked During Job Applications

The `profile.json` covers all of these:
- Personal: name, email, phone, location, DOB, gender
- Work: total experience, current company, designation, notice period
- Compensation: current CTC, expected CTC, fixed/variable split
- Education: degree, specialization, college, % or CGPA, passing year
- Skills: primary, secondary, tools, certifications
- Preferences: locations, work mode, employment type, relocation
- Screening: work authorization, shift preference, disability, category
- Docs: PAN, Aadhar (last 4), UAN, passport

## 🔄 Keeping Profile Updated

The AI should compare every form question against `profile.json`. If a question cannot be answered:
- Log the field name under a "missing" section in the dashboard
- Show an alert asking you to update `profile.json`
- Only proceed after you've filled the value

## 🛠 Tech Stack
- Pure HTML + CSS + Vanilla JS (no build tools needed)
- `profile.json` as the single source of truth
- `applications.json` as the log store
- GitHub for version control and sync across machines
