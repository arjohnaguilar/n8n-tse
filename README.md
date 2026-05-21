# 🔐 2FA / Login Support SOP (Intent-Based)

This document defines how to handle 2FA-related support requests using intent-first troubleshooting.

---

# 🧭 1. Core Principle

Do NOT require perfect request formatting.

Instead:
- Focus on understanding if the user is asking about 2FA or login issues
- Extract available information from the message
- Ask follow-up questions if needed

---

# 🧠 2. Intent Detection Rule

If the user message includes any of the following:

- 2FA not working
- login failed
- cannot access account
- OTP issue
- authenticator issue
- password problem

👉 Treat as a VALID SUPPORT REQUEST

Even if details are incomplete.

---

# 🔍 3. Information Extraction (Best Effort)

From user message, try to identify:

- Store / Account ID (if present)
- Name (if present)
- Mobile number (if present)
- Type of issue (2FA / login / password)

⚠️ If missing, do NOT block processing—just mark as “missing info”.

---

# 🧭 4. Support Flow (MANDATORY)

## STEP 1: Confirm Issue Type
Start by confirming:

- "Is this a 2FA/login issue?"

---

## STEP 2: Basic User Check (FIRST TROUBLESHOOTING STEP)

Always ask:

- Have you tried rechecking your password?
- Are you using the correct login credentials?
- Did you recently change your password?
- Are you able to access your email or phone for OTP?

---

## STEP 3: Attempt Basic Resolution

Before reset:

- Ask user to retry login
- Confirm password correctness
- Check if issue is temporary

---

## STEP 4: Decide Next Action

### If resolved:
✔ No reset needed  
✔ Inform user issue is resolved  

### If NOT resolved:
➡ Proceed to 2FA reset evaluation  

---

# 🔐 5. 2FA Reset Condition

Only proceed if:

- User confirms password is correct
- Basic login troubleshooting failed
- Issue clearly related to 2FA/authenticator
- No security risk detected

---

# ⚙️ 6. 2FA Reset Execution

If approved:

1. Locate account (if ID provided)
2. Remove existing 2FA binding
3. Reset authentication setup
4. Trigger re-enrollment
5. Log action in system

---

# 📢 7. Communication Rule

Always:

- Start with confirmation question
- Do NOT immediately ask for full details
- Guide step-by-step
- Keep language simple

---

# 🚨 8. Escalation Rules

Escalate if:

- Identity cannot be confirmed
- Account cannot be found
- Suspicious activity detected
- Multiple failed attempts

---

# 🧠 9. Support Behavior Rule

- Always prioritize intent over format
- Do NOT reject due to missing fields
- Extract what is available
- Ask follow-up questions naturally
