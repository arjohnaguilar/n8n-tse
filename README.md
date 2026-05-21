# 🧠 TSE Support Knowledge Base

This document is used by the AI Support Assistant to troubleshoot system issues, validate data problems, and guide resolution steps.

---

# 🧭 System Overview

## Core Systems
- Backend: AWS Lambda / Microservices
- Automation: n8n workflows
- Database: PostgreSQL / MySQL
- Storage: S3 / Google Sheets
- Monitoring: CloudWatch Logs / Alerts

---

# 🚨 Common Issues & Playbooks

---

## 🔥 1. AWS Lambda Timeout

### Symptom
- Function fails with:


### Possible Causes
- Heavy initialization code
- No internet access (missing NAT Gateway in VPC)
- External API latency
- Timeout too low
- Cold start issues

### Troubleshooting Steps
1. Check CloudWatch logs
2. Compare execution time vs timeout setting
3. Verify if Lambda is inside VPC
4. Check outbound internet access (NAT Gateway)
5. Identify slow external API calls

### Fixes
- Increase timeout (e.g. 10s → 30–60s)
- Move heavy logic outside handler
- Add caching where possible
- Ensure NAT Gateway exists if needed

---

## 🔐 2. IAM Permission Denied

### Symptom


### Possible Causes
- Missing IAM policy
- Wrong role attached
- Cross-account access not configured
- Incorrect resource ARN

### Troubleshooting Steps
1. Identify IAM role/user in error
2. Check attached policies
3. Validate allowed actions
4. Verify resource ARN matches environment

### Fixes
- Add required IAM permissions
- Attach correct role to service
- Fix ARN scope (dev/prod mismatch)

---

## 📊 3. Data Mismatch (Reports vs System)

### Symptom
- Google Sheet / report does not match system data

### Possible Causes
- Delayed sync
- Incorrect query filters
- Manual edits in spreadsheet
- Cache or stale data

### Troubleshooting Steps
1. Identify source of truth system
2. Compare timestamps (system vs report)
3. Validate query filters
4. Check last sync execution logs

### Fixes
- Re-run sync pipeline
- Fix query conditions
- Lock spreadsheet edits
- Add validation rules

---

## 🔁 4. n8n Workflow Failure

### Symptom
- Workflow does not run or fails mid-process

### Possible Causes
- Broken node connection
- Invalid credentials
- API failure
- Timeout in HTTP request node

### Troubleshooting Steps
1. Open n8n execution logs
2. Identify failed node
3. Check input/output data
4. Test API manually
5. Validate credentials

### Fixes
- Fix node configuration
- Refresh credentials
- Add retry logic
- Handle API failures gracefully

---

## 🧪 Standard TSE Troubleshooting Flow

Always follow this structure:

1. Understand the issue  
2. Identify affected system  
3. Check logs / evidence  
4. Determine possible root causes  
5. Suggest fix or workaround  
6. Ask for missing details if unclear  

---

## 📥 Required Information From Users

If issue is unclear, always ask:

- Full error message
- Timestamp of issue
- Affected system (AWS, n8n, DB, etc.)
- Screenshots or logs
- Recent changes before issue

---

## 🧠 Root Cause Thinking Framework

When analyzing issues, always consider:

- Configuration issue?
- Permission issue?
- Network/VPC issue?
- Data inconsistency?
- Performance/timeout issue?
- Human/manual error?

---

## 💬 Communication Style

- Use simple language first
- Avoid jargon unless needed
- Break steps clearly
- Be calm and structured
- Ask clarifying questions when needed

---

## 📌 Future Expansion Areas

Add more playbooks:

- API Gateway failures
- Database connection issues
- CI/CD deployment failures
- Security incidents
- Payment processing issues
- Third-party API failures