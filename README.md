# Terraform Planning and Git Workflow

This document records the infrastructure planning and repository maintenance steps performed during the final stages of the Week B assignment.

## 🏗 Terraform Planning

The primary focus was generating and capturing Terraform execution plans in various formats for review and documentation.

### Generating Plan Files

We explored several ways to output the execution plan, eventually settling on a color-stripped text format to ensure readability in standard text editors:# Attempting binary output for terraform show
terraform plan -out=week_b

# Capturing a clean text-based plan (no ANSI color codes)
terraform plan -no-color > plan.txt

# Capturing plan as JSON for external parsing
terraform plan -no-color > plan.json

### 📂 Repository Maintenance

After generating the necessary plans, we performed a cleanup of the TheoU_7.5_BaM_weekB directory to ensure only essential code and documentation were committed to version control.
### Git Versioning
1. Adding Artifacts:
```git
    git add plan.json
    git commit
    git push origin main
```
2. Cleaning the Workspace: We identified that binary files and multiple redundant plan extensions were cluttering the repository. We removed the following files from tracking:week_b (binary)week_b.jsonweek_b.txtExecution:git rm week_b week_b.json week_b.txt
git commit -m "Remove unnecessary files"
git push origin main

### 🔍 System Verification
Before concluding the session, system and user context were verified to ensure logs were attributed correctly:
- Commands used: pwd, ls, date, hostname, whoami.