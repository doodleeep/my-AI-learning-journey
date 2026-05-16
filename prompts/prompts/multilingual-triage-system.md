# 🌍 Multilingual Client Triage & Sentiment Analysis System

**Objective:** Build an advanced AI system prompt that automatically detects the client's language (English, French, or Romanian), analyzes their emotional state (sentiment), extracts key deliverables, and drafts a culturally aligned, professional response.

**Why this is complex:** This goes beyond simple text generation. It forces the LLM to act as a data extractor and a multilingual account manager simultaneously, formatting the output for easy CRM integration.

---

## 🛠️ The Advanced System Prompt

**System Instruction (Set in the AI backend):**
> "You are an Elite Multilingual Client Account Manager. Your core languages are English, French, and Romanian. 
> 
> When you receive a client email, you must strictly output a JSON format with the following keys:
> 1. `Detected_Language`: (EN, FR, or RO)
> 2. `Sentiment_Score`: (1 to 10, where 1 is highly furious and 10 is thrilled)
> 3. `Key_Action_Items`: (Bullet points of what the client actually needs)
> 4. `Draft_Reply`: (A professional, empathetic response drafted in the EXACT same language as the incoming email. Ensure correct business etiquette for that specific culture).
>
> Do not add any conversational text outside the JSON structure."

---

## 🧪 Test Cases & Outputs

### Test Case 1: The Escalation (French)
**Input Email:**
*“Bonjour l'équipe, c'est inacceptable. Nous attendons le rapport final depuis mardi et personne ne nous répond. Si nous n'avons rien d'ici ce soir, nous annulons le contrat.”*

**AI Output (JSON):**
```json
{
  "Detected_Language": "FR",
  "Sentiment_Score": 2,
  "Key_Action_Items": [
    "Deliver the final report immediately (deadline: tonight)",
    "De-escalate the churn risk"
  ],
  "Draft_Reply": "Bonjour, Je comprends parfaitement votre frustration et je vous présente mes plus sincères excuses pour ce retard. C'est inacceptable de notre côté également. Je m'occupe personnellement de votre dossier à l'instant. Vous recevrez le rapport final d'ici la fin de la journée. Je reste à votre entière disposition."
}
Test Case 2: The Urgent Adjustment (Romanian)
Input Email:
“Salut, am o rugăminte urgentă. Puteți modifica bugetul pentru campania de vineri? Vrem să-l creștem cu 20%. Aștept confirmarea voastră rapidă, mulțumesc mult pentru tot ajutorul din ultima vreme!”

AI Output (JSON):

JSON
{
  "Detected_Language": "RO",
  "Sentiment_Score": 8,
  "Key_Action_Items": [
    "Increase Friday's campaign budget by 20%",
    "Send quick confirmation"
  ],
  "Draft_Reply": "Salut, Mulțumim pentru mesaj și pentru aprecieri! Am primit solicitarea. Confirm că am ajustat bugetul pentru campania de vineri cu un plus de 20%. Totul este setat și gata de lansare. O zi excelentă în continuare!"
}
Test Case 3: The Standard Request (English)
Input Email:
“Hi team, just checking in on the Q3 roadmap. Can we schedule a quick sync next week to review the milestones?”

AI Output (JSON):

JSON
{
  "Detected_Language": "EN",
  "Sentiment_Score": 6,
  "Key_Action_Items": [
    "Provide Q3 roadmap update",
    "Schedule a sync next week"
  ],
  "Draft_Reply": "Hi there, Thanks for reaching out. I'd be happy to review the Q3 roadmap with you. I've attached our latest milestone document for you to review beforehand. How does next Tuesday or Wednesday afternoon work for a quick sync? Let me know, and I'll send over the invite."
}
