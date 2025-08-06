# KIA — College’s Very Own KnowItAll

**KIA** is an AI-powered assistant built specifically for your college.  
It answers real student questions about clubs, events, rules, and campus life by combining **Prompting**, **Structured Output**, **Function Calling**, and **Retrieval-Augmented Generation (RAG)**.  
It’s not a chatbot for everything — it’s a chatbot that actually knows your campus.

---

## Project Overview

KIA takes a student’s question and figures out the best way to answer using both live and stored information.

It can:

- Look up event schedules and deadlines.
- Find rules and policies in official documents.
- Tell you where to go or who to contact for campus services.
- Answer using verified campus-specific knowledge — not random internet info.

The focus is on **accuracy and relevance** to your college environment.

---

## 1. Prompting

Prompting defines KIA’s role, tone, and scope.  
Instead of “answer this question,” KIA is told exactly how to behave:

**Sample Prompt:**
> You are KIA, a helpful AI assistant for [College Name] students.  
> Only answer questions about campus life using function calls or document search.  
> Speak politely and be concise. If unsure, say you don't know.

This ensures the AI doesn’t hallucinate and stays within the college domain.

---

## 2. Structured Output

KIA returns answers in a consistent JSON structure so the frontend can display them cleanly.

**Example:**
```json
{
  "answer": "The Robotics Club meets every Wednesday at 5 PM in Room 204.",
  "source": "Student Clubs Handbook 2024",
  "reliability": "high"
}
```
This makes it easy to show the answer, its source, and confidence level to the user.

---

## 3. Function Calling

Function calls let KIA fetch real-time or specific information from campus systems.

**Examples:**

- `getEventSchedule(clubName)` – Fetch event times for a club.
- `findPolicyDocument(topic)` – Search official rules for a keyword.
- `contactOffice(department)` – Get office location and contact details.

KIA decides when to use these functions based on the question.

---

## 4. RAG (Retrieval-Augmented Generation)

Before answering, KIA can search a vector database containing:

- Handbooks  
- Campus policies  
- Event guides  
- Club descriptions

It retrieves relevant passages and uses them in the answer so responses are **accurate and sourced**.

**Example:**

**Question:** “When is the cultural fest?”  
**RAG finds:** “Annual Cultural Fest is held in March. The 2025 dates are March 12–14.”  
**Final Answer:** “The Cultural Fest is from March 12–14, 2025, in the Main Quadrangle.”

---

## Tech Stack

- **Frontend** – React + Tailwind  
- **Backend** – Node.js + Express  
- **AI** – OpenAI GPT models  
- **RAG Source** – Campus document vector database  
- **Hosting** – Vercel / Netlify