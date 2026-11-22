# Step 7: Version 2 Fix, Role Prompting Test & Scorecard

**Student:** Ashnoor Kaur (2620992549) | **Tool:** Gemini AI

## Part A: System Prompt Version 2 Fix (Fixing Q09)
- **Rule Added to System Prompt (v2):**  
  IF a customer asks multiple questions in one message, answer briefly in 1 short sentence per topic and stay strictly under 80 words total, or invite them to ask one topic at a time.
- **Re-test on Q09 (v2 Result):**  
  FinBuddy answered in **68 words** (briefly covering TDS, credit score, NEFT vs IMPS, and UPI linking, then ending with "Please confirm with an official source."). **Status: ✔ FIXED (10 / 10).**

## Part B: Role Prompting Test ("Should a 19-year-old college student take a credit card?")

| Setup | Tone & Style | Key Content | Enforced KoshBank Rules? |
| :--- | :--- | :--- | :---: |
| **Chat 1: No role** | Neutral, balanced list of pros and cons (~140 words). | Mentions credit history vs debt risk. | No |
| **Chat 2: Experienced credit analyst** | Formal, risk-focused, uses jargon (utilization ratio, CIBIL, revolving APR). | Recommends secured/FD-backed card only with strict discipline. | No |
| **Chat 3: Friendly senior student** | Casual, relatable, uses college examples. | Advises sticking to UPI unless tracking expenses carefully. | No |

**Finding:** A role changes **tone, vocabulary, and perspective**, NOT compliance enforcement. Only the standing **system prompt** enforced the 80-word limit, safety refusals, and mandatory closing line.

## Part C: Scorecard & Reflection

| Metric | Plain Chat | System Prompt (v1) | System Prompt (v2) |
| :--- | :---: | :---: | :---: |
| **Answers that followed every rule (/10)** | 0 | 9 | 10 |
| **Personal data handled safely** | No | Yes | Yes |
| **No investment tips** | No | Yes | Yes |
| **Closing line present (/10)** | 0 | 10 | 10 |

### Reflection
1. Plain chat was fine for Step 4 because explaining a savings account has no regulatory rules.
2. System prompt v1 immediately fixed 9 of 10 questions, including all safety traps (OTP, stock tips, prompt injection, Hinglish).
3. Adding one multi-part brevity rule in v2 brought Q09 down from 114 words to 68 words (10/10).
4. Role prompting changed voice and framing, proving that a role is only one small part of a production system prompt.
