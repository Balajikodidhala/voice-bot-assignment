# **CreditNirvana Voice Bot Assignment**

Two voice bots built on Sarvam AI for the Prompt Engineer Intern (Voice AI & Agentic AI) assignment at CreditNirvana.
| Bot | Persona | Goal |
| :--- | :--- | :--- |
| **Bot 1: Personal Loan Settlement** | Rohan | Close on full repayment or a settlement with a commitment date |
| **Bot 2: Car Insurance Renewal** | Priya | Renew the policy at the highest achievable value |

# **Bot 1: Personal Loan Settlement - Rohan**
Scenario


* **Loan Status:** A personal loan of ₹5,00,000 has remained unpaid for 8 months, with the customer providing a new excuse on every call.
* **Outstanding Dues:** The total outstanding amount of ₹6,50,000 comprises ₹4,00,000 in principal, ₹2,00,000 in interest, and ₹50,000 in other charges.
* **Settlement Offer:** A special settlement offer is available at ₹4,00,000, which effectively waives ₹2,50,000 of the total dues.

Tone: firm, direct and assertive. Rohan calls out repeated excuses, explains the credit score and legal impact, creates urgency around the offer, negotiates, and closes on a payment date.

Negotiation ladder

* **Single Payment Plan:** A settlement offer of ₹4,00,000 to be paid in a single payment within 7 days.
* **Split Payment Plan:** An initial token payment of ₹1,00,000 due now, with the remaining balance of ₹3,00,000 payable within 15 days.
* **Minimum Threshold & Review:** No lower settlement amounts are permitted; requests require supervisor review along with a firm token date and a callback within 48 hours.

Compliance (RBI fair practices)


* **Identity & Privacy:** Mandatory identity check with strict non-disclosure of the loan details to anyone else.
* **Call Guidelines:** Call recording must be disclosed upfront, and calls are restricted strictly between 8 AM and 7 PM.
* **Prohibited Conduct:** Zero tolerance for abusive language, threats, shaming, or contacting family members or employers.
* **Legal Representation:** Legal consequences must be communicated solely as standard lawful steps and never used as threats.
* **Dispute Handling:** Provides a clean and professional exit strategy for customer disputes, distress, or mentions of lawyers and ombudsmen.

# **Bot 2: Car Insurance Renewal -Priya**

Scenario


* **Vehicle & Policy Status:** Maruti Brezza with policy due for renewal.
* **IDV Adjustment:** Insured Declared Value (IDV) is revised from ₹9,00,000 to ₹8,00,000.
* **Pricing & Discount:** The base premium of ₹20,000 has been discounted to ₹15,000.

Tone: warm, confident and consultative.

Flow: verify, explain the IDV change, give the price, discover needs, pitch two or three add-ons, handle objections, close with a payment link.

Add-ons: zero depreciation, engine protect, roadside assistance, consumables, return to invoice, NCB protection. The bot leads with the zero dep plus engine protect bundle and steps down only if the customer declines.

Test prices used (assumed, not real quotes)

| Add-on | Price |
| :--- | :--- |
| Zero depreciation | ₹3,000 |
| Engine protect | ₹1,200 |
| Roadside assistance | ₹600 |
| Consumables cover | ₹800 |
| Return to invoice | ₹2,000 |
| NCB protection | ₹700 |



# **Repository structure**

.
├── README.md
├── prompts/
│   ├── bot1_loan_settlement.txt
│   └── bot2_car_insurance.txt
├── docs/
│   └── system_prompts_and_design_note.pdf
├── recordings/
│   ├── bot1_test_call.mp3
│   └── bot2_test_call.mp3
└── test_scripts/
    ├── bot1_customer_lines.md
    └── bot2_customer_lines.md
    
    
# **Setup on Sarvam AI**

Create a voice agent in your Sarvam account for each bot.
Paste the matching file from prompts/ as the system prompt.
Set the default language to English with Hindi and Hinglish enabled. Bot 1's sample lines are in Hinglish.
Fill in the variables listed below.
Attach one test phone number to each bot and place a call.



# **Variables to fill**

| Variable | Used In | Example |
| :--- | :--- | :--- |
| `{{lender_name}}` | Bot 1 | Your demo lender name |
| `{{customer_name}}` | Both | Name of the test caller |
| `{{offer_valid_till}}` | Bot 1 | A date a few days ahead |
| `{{grievance_email}}` | Bot 1 | A support email |
| `{{insurer_or_broker_name}}` | Bot 2 | Your demo insurer name |
| `{{vehicle_number}}` | Bot 2 | A sample registration number |
| `{{expiry_date}}` | Bot 2 | The policy expiry date |
| `{{zero_dep_price}}` ... `{{ncb_protect_price}}` | Bot 2 | See the price table above |
| `{{garage_count}}`, `{{ncb_percent}}` | Bot 2 | Sample values |




# **Design choices**

* Written for speech: short turns, one question at a time, numbers spoken in words, and handling for interruptions, silence, and anger.
* Compliance sits above tone: in Bot 1, firmness comes from structure (naming the pattern, redirecting to a date) rather than harsh words.
* Objection pattern: acknowledge briefly, answer with a fact, and move to the next step.
* The amount is protected: Bot 1 never goes below ₹4,00,000 and flexes timing instead, while Bot 2 never invents a discount beyond ₹15,000 and trims add-ons rather than the base discount.
* No invented facts: both bots are instructed to confirm and call back if they do not know something.


# **Test calls**

| Call | Bot | Scenario |
| :--- | :--- | :--- |
| **A** | Bot 1 | Tough customer: a new excuse every time, no commitment |
| **B** | Bot 1 | Negotiation that ends with a UPI payment date |
| **A** | Bot 2 | Tough customer: portal price comparison, refuses add-ons |
| **B** | Bot 2 | IDV explanation, competitor comparison, add-on sale and booking |



# **Test numbers for evaluators**


* Bot 1: +91 7975068626
* Bot 2: +91 9008449851

#**Assumptions**

The assignment did not give add-on prices, the offer expiry date or the grievance contact, so these are variables.
Legal and credit-score statements are general and factual. They are not legal advice.



# **Author & Submission Details**

Balaji Kodidhala

* Email: balajik12072003@gmail.com
* LinkedIn: [https://www.linkedin.com/in/balaji-kodidhala](https://www.linkedin.com/in/balaji-kodidhala)
* GitHub: [https://github.com/Balajikodidhala](https://github.com/Balajikodidhala)
  
Submission deadline: Tuesday, 27 October 2026, 11:59 PM IST
