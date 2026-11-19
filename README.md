# CraftCore · Case Study

> **Source code is private under client NDA.** This repo documents the product, the architecture and my role. Happy to walk through it on a call: [book 30 min](https://calendly.com/muhammadusman200301/30min).

**CraftCore** is a hiring platform built for industrial skilled trades. Job seekers search trade jobs and build profiles with their experience and certifications; employers post jobs and reach trade workers.

| | |
|---|---|
| **My role** | Full-stack developer |
| **Platforms** | iOS, Android |
| **Live** | [App Store](https://apps.apple.com/us/app/craftcore/id6767089223) · [Google Play](https://play.google.com/store/apps/details?id=com.craftcoremobile) |

## Tech stack
React Native · TypeScript · Firebase Auth · Firestore · Cloud Functions · Typesense

## What I built
- Sign-up and account flows with Firebase Auth
- Job and candidate **search with filters** using Typesense
- Worker profiles with experience and certifications
- **Cloud Functions** triggered by data changes for application tracking and notifications

## Architecture (simplified)

```
Mobile app ──► Firebase Auth
     │
     ├──► Firestore (jobs, profiles, applications)
     │         └── on change ──► Cloud Functions ──► notifications
     │                                └──► sync to Typesense index
     └──► Typesense (fast search & filters)
```

## Challenges and how I handled them
- **Fast search over jobs and candidates** – Firestore alone isn't built for full-text search with filters, so I synced data to Typesense through Cloud Functions.
- **Keeping both sides updated** – event-driven notifications so applicants and employers see status changes quickly.

---
More of my work: [Portfolio](https://muhammadusman-portfolio10.netlify.app) · [LinkedIn](https://www.linkedin.com/in/muhammad-usman-987852388/)
