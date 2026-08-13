# Assignment 4 — Building Your AI Team

Part of the DevOps Micro Internship (DMI) Cohort 3 with Agentic AI

---

## Purpose

In this assignment, you will build and configure a set of specialized AI subagents inside your project. You will learn how different models and tool permissions define agent behavior, and you will trigger two real agent delegations to analyze security and cost aspects of your Terraform infrastructure.

---

# Task 1 — Create the Agents Folder and Add Files

## Goal

Create the `.claude/agents/` directory and add all required agent files.

### Evidence

#### Screenshot 1 — VS Code sidebar showing `.claude/agents/` with all 3 files

![project](./screenshots/ss20.png)

---

# Task 2 — Compare the Agent Configurations

## Goal

Analyze the configuration differences between the three agents and demonstrate understanding of model and tool selection.

### Written Answers

#### 1. Why does the cost optimizer use Haiku instead of Sonnet?

Cost-optimizer uses Haiku because the job is simple: check the code against a known list of cost issues. It doesn't need heavy thinking, just fast pattern-matching. Haiku does that well, and it's cheaper and quicker than Sonnet so it's the smarter choice for this task.


---

#### 2. Why does the security auditor NOT have Write in its tools list?

Security-auditor is intentionally read-only. Its job is to inspect Terraform files and flag vulnerabilities, not fix them. Withholding Write access means the agent can never modify infrastructure on its own  it can only read and report. That separation of "find the issue" from "fix the issue" is a safety boundary, not an oversight.


---

#### 3. Why does the tf-writer use `inherit` instead of a specific model?

inherit means tf-writer doesn't lock itself to one model it uses whatever model is powering the parent session. So if you're running the session on Sonnet, tf-writer uses Sonnet; if you switch to Opus, it follows. This keeps the agent flexible instead of hardcoding a model choice that might not match the session's needs.


---

### Evidence

#### Screenshot 2 — `security-auditor.md` frontmatter showing model and tools configuration

![secaud](./screenshots/ss21.png)

---

#### Screenshot 3 — `cost-optimizer.md` frontmatter showing the model and tools configuration

![costopt](./screenshots/ss22.png)

---

# Task 3 — Run the Security Auditor

## Goal

Trigger the security auditor agent and analyze the generated security report for your Terraform infrastructure.

### Evidence

#### Screenshot 4 — The delegation message showing Claude launched the security-auditor

![message](./screenshots/ss23.png)

---

#### Screenshot 5 — Security audit report output

![report](./screenshots/ss24.png)

---

# Task 4 — Run the Cost Optimizer

## Goal

Trigger the cost optimizer agent and review the generated cost optimization report.

### Evidence

#### Screenshot 6 — The full cost optimization report

![report](./screenshots/ss25.png)

---

# Submission Instructions

- Ensure all agent files are committed in `.claude/agents/`
- Complete all written answers in your GitHub Repo
- Push final changes to your forked GitHub repository

---

## GitHub Repository URL

Paste your forked repository URL here:

[`Add your URL here`](https://github.com/shekahassan/Ultimate-Agentic-DevOps-with-Claude-Code)

---

# Completion Checklist

- [ ] `.claude/agents/` folder contains all 3 agent files
- [ ] Screenshot 2 shows correct `security-auditor.md` configuration
- [ ] Screenshot 3 shows correct `cost-optimizer.md` configuration
- [ ] All 3 written answers completed 
- [ ] Security auditor executed successfully
- [ ] Cost optimizer executed successfully
- [ ] Security report is visible with findings
- [ ] Cost report is visible with recommendations
- [ ] All required screenshots added
- [ ] GitHub repo updated with agents

---

## 📌 About DMI & CloudAdvisory

DevOps Micro Internship (DMI) is a project-based DevOps program run by Pravin Mishra (The CloudAdvisory) focused on real-world execution, systems thinking, and career readiness.

It helps learners build strong DevOps foundations with hands-on experience.

---

## 📌 Resources

- 🌐 DMI Official Website: https://dmi.pravinmishra.com?utm_source=github&utm_medium=readme  
- 🎓 University: https://university.pravinmishra.com?utm_source=github&utm_medium=readme  
- 💬 Discord Community: https://discord.pravinmishra.com?utm_source=github&utm_medium=readme  
- 📝 Blog: https://dmi.pravinmishra.com/blog?utm_source=github&utm_medium=readme  
- ▶️ YouTube Playlist: https://www.youtube.com/playlist?list=PLFeSNDtI4Cho  
- 🔗 Pravin Mishra (LinkedIn): https://www.linkedin.com/in/pravin-mishra-aws-trainer/  
- 🏢 CloudAdvisory (LinkedIn): https://www.linkedin.com/company/thecloudadvisory/

---

*This submission is part of DevOps Micro Internship (DMI) Cohort 3 — Agentic AI Track.*