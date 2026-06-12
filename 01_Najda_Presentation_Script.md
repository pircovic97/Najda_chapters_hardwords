# Najda — Defense Presentation Scripts

**Total speaking time:** ~16 minutes (after ~2 min video + ~2 min live demo)
**Presenters:** Rim · Nasreddine · Akram

**Split:**

- **Rim** — Presentation/Intro (slides 3–7) + Market & Value (40–48) + Limitations & Conclusion (49–52)
- **Nasreddine** — Design System (8–20)
- **Akram** — System Design (21–29) + AI Modeling (30–35) + Development (36–39)

**Pacing notes:**

- On a divider slide (just a section title), say one line and move on.
- Slow down on slides with **tables and graphs** — slides 7, 34, 42, 45, 47, 48. Those are where the jury looks closely.
- Speak slowly. It always feels faster to the audience than to you.

---

## TITLE SLIDE (Slide 1) — _whoever opens, suggest Rim_

> Good morning. We are Akram, Nasreddine, and Rim, and we present our project: **Najda** — a voice-driven AI system in Darija for medical urgency and appointment management. Our supervisor is Dr. Boustil Amel.

_(Skip slide 2, the summary table — or one line:)_

> Here is the plan of our presentation. I will start with the problem and the idea.

---

# PART 1 — RIM

## Slide 3 — "Presentation" (divider)

> Let me begin with the context and the problem we want to solve.

## Slide 4 — Introduction

> Najda is an AI healthcare triage system made for Algerian patients. Today, many patients face three problems: they cannot tell how urgent their symptoms are, they don't know which medical service to go to, and they struggle to get care quickly — especially in emergencies.
>
> To solve this, we built Najda. It brings together AI triage, voice interaction in Darija, speech-to-text, and smart appointment booking — all in one platform.

## Slide 5 — The Problem

> Picture an Algerian hospital early in the morning. It is already full. A pregnant woman with chest pain is waiting in the same line as a child with a small fever. Same queue, same desk.
>
> There is no tool to sort patients by urgency. There are three clear problems. **First, booking is broken** — it is done by phone, lines are busy, and the next free slot can be weeks away. **Second, there is no triage before arrival** — patients guess their own urgency and just go to the emergency room. **Third, there is a language gap** — more than 80% of Algerians speak Darija, but almost no medical software understands it.

## Slide 6 — What Najda Does

> The idea is simple. The patient describes their symptoms in Darija — by voice or by text. Najda returns two things: an urgency level and a recommended medical service.
>
> The flow is: Darija input goes to AI triage, which produces urgency plus service, and then an action follows. One important point — **the AI advises, the doctor decides.** Najda supports the medical staff, it does not replace them.

## Slide 7 — Competitors Analysis _(TABLE — slow down)_

> We compared Najda with three existing solutions. **DZDOC**, a local Algerian app — it does booking, but no AI and no Darija. **Ada Health**, a global AI symptom checker — it has AI triage, but no Darija and no booking. And **Zocdoc**, a booking platform — again, no AI triage and no Darija.
>
> If you read across this table, every column has gaps — except Najda. We are the only one that combines Darija voice input, AI urgency triage, service recommendation, booking, emergency with GPS dispatch, and a design built for the Algerian context. That last column is our position in the market.

_(Rim hands over to Nasreddine.)_

> Now Nasreddine will present the design system behind Najda.

---

# PART 2 — NASREDDINE

## Slide 8 — "Design System" (divider)

> Before writing a single line of code, we built a complete design system. Let me walk you through it.

## Slide 9 — Who We Design For

> Najda has to work for three kinds of users. **The patient**, who needs to know fast — is it the ER, a same-day visit, or home care. **The doctor**, who wants to see only the patients who truly need their specialty. And **the receptionist**, who is buried under repetitive phone calls. We designed for all three from the start.

## Slide 10 — Brand & Design System

> We created a full visual identity that is calm, fast, and clearly medical. Three core colors anchor everything you will see in the app.

## Slide 11 — Color Palette

> Here, color is not decoration — it is information. Each color maps to a state the patient must understand instantly. We use a neutral ramp for the interface, a blue ramp for the brand, and — most importantly — an urgency scale: orange for a normal **Consultation**, and red for **Urgent**. So a patient can read their situation by color alone.

## Slide 12 — Typography

> One typeface, Inter, in two main weights. Large and very legible — readable from the back of a stressed, crowded waiting room. Clarity was the only rule, one important remark , when we deploy to iOS however, we follow apple's guidelines and use SF Pro instead of Inter.

## Slide 13 — Iconography

> Our icons sit on a 24-pixel grid with a consistent line weight, so they look clean on every screen. We used Lucide and Nucleo for Web platform, and Material Symbols on mobile. Rounded shapes keep the interface approachable but still professional.

## Slide 14 — Najda Logo Concept

> The logo is a custom "N" monogram, built around clarity, speed, and recognition. It stays recognizable everywhere — on a phone home screen, at small favicon size, and on printed signage.

## Slide 15 — Logo Safety Margin

> To protect the logo, we defined a minimum clear space around it, so no text or graphic ever crowds it. This keeps the brand consistent across all our materials.

## Slide 16 & 17 — Components

> Every screen in Najda is built from one shared component system, organized in three layers: **primitives** like buttons and inputs at the bottom, **composite components** like forms and navigation in the middle, and **domain components** like the urgency badge and emergency button at the top. The same building blocks are reused everywhere, so the interface stays predictable and easy to use under pressure.

_(For slide 17, just point:)_

> Here you can see those components in real screens — buttons, inputs, and the emergency alert.

## Slide 18 & 19 — Najda Screens

> These are real screens from the system. On mobile, the doctor sees a prioritized patient list with urgency badges and AI confidence. On the web dashboard, the patient describes symptoms in Darija by voice, and the AI returns a full analysis — here you can see an emergency case flagged in red, with the primary symptom, severity, and the recommended specialist.

_(Slide 19, one line:)_

> And here is the emergency case detail and the analysis result on the web side.

## Slide 20 — Graphic Charter

> Finally, we built a unified graphic charter — the marketing and communication style — so Najda looks recognizable and trustworthy across both digital and print.

_(Nasreddine hands over to Akram.)_

> Now Akram will explain the system design and the AI behind Najda.

---

# PART 3 — AKRAM

## Slide 21 — "System Design" (divider)

> Thank you. Let me show how the system is built.

## Slide 22 — System Architecture

> Najda uses a modular microservices architecture, with **five core services**. The frontend — React and Flutter. The backend — Node.js with Express. The AI service — Python and FastAPI, which is the triage engine. A separate speech-to-text service using faster-whisper. And a PostgreSQL database on Supabase.
>
> We separated them on purpose. The AI and speech work is heavy, so keeping those as independent services lets us scale them on demand without slowing the rest of the system.

## Slide 23 — UML Diagrams

> Before building, we modeled the whole system with UML — use-case, sequence, activity, and class diagrams. This let us define the behavior first, which gave us strong consistency between the interface, the backend logic, and the database.

## Slide 24 — Use Case Diagram

> This diagram shows what each actor can do. The **patient** does voice triage, booking, and emergency alerts. The **doctor** manages records, validates triage, and sets availability. The **administrator** handles monitoring and user management.

## Slide 25 — Class Diagram

> This is our data structure in PostgreSQL. The key relationships are: **users and profiles** with secure authentication, **triage records** that link the patient's voice input to the AI urgency level, and **appointments** that connect a triage result to a doctor's availability.

## Slide 26 — Sequence Diagram

> This shows the full triage-to-appointment lifecycle. The patient sends a voice query in Darija. The speech-to-text service converts audio to text. The AI engine processes the text and returns a priority score. Then the backend filters available appointment slots based on that priority.

## Slide 27 — AI Triage Flow

> Here is the core workflow in detail. Darija symptom input — by voice or text — then speech-to-text, then AI urgency prediction, then specialty recommendation, and finally the triage result. One important branch at the bottom: **if the urgency is Urgent, the system creates a priority appointment; if it is a Consultation, it creates a standard booking.** The triage result directly drives the booking.

## Slide 28 — Emergency Alert Flow

> For critical cases, we have a separate emergency flow. When an emergency is detected, the system captures the patient's GPS location, creates an emergency case, and notifies reception and the ambulance team. It then escalates — dispatching the ambulance and tracking the case until it is resolved.

## Slide 29 — Appointment Scheduling Flow

> And this connects triage to a confirmed appointment. The request is created, availability is checked, the doctor is assigned, and the patient gets a confirmation. From symptom to confirmed consultation, in one connected flow.

## Slide 30 — "AI Modeling" (divider)

> Now the heart of the project — the AI.

## Slide 31 — Data Sourcing

> Our biggest challenge: there was no ready dataset for Algerian medical Darija. So we built our own. We collected real discussions from Algerian Facebook medical groups, health forums, and community Q&A.
>
> The language is exactly what real patients use — Darija, Arabizi (Arabic written in Latin letters), and Arabic-French code-switching. Our final dataset has **859 labeled entries, across 2 urgency levels and 5 medical specialties.**

## Slide 32 — Preprocessing Pipeline _(GRAPHS — slow down)_

> Raw social media text is messy, so we cleaned it in several stages: we normalized Arabizi, removed noise and emojis, standardized the symptoms, mapped them to a clinical category, and anonymized any personal information.
>
> For example — _"3ndi wja3 fi sadri"_, which means "I have pain in my chest," maps to **Cardiology**. _"Rassi ywj3ni"_, "my head hurts," maps to **Neurology**.
>
> The charts on the right show our dataset balance. By **medical service**, it is well spread — Cardiology, Neurology, and Emergency Medicine are each around 23%, then Internal Medicine and Gynecology. By **urgency**, it is almost balanced — about 52% Urgent and 48% Consultation. This balance matters, because it means the model is not biased toward one class.

## Slide 33 — AI Approaches

> We did not pick one model blindly — we built and compared three. **Approach 1: a prompted LLM**, Qwen 2.5 — strong at understanding mixed Darija, but slower and more costly. **Approach 2: Embeddings plus KNN**, using E5 and FAISS — very fast and cheap, but depends on similarity to known examples. **Approach 3: a Hybrid RAG pipeline** — it combines embedding-based urgency detection with LLM-based specialty prediction, balancing speed and reasoning.
>
> We chose these three because they fit our project's needs and they run well on our own machine — we did not need a huge external server. And as you will see on the next slide, **the third approach, the Hybrid RAG, gives the best results so far.**

## Slide 34 — Evaluation Results _(KEY TABLE — slowest slide, this is the core result)_

> We evaluated all three on the same 859 queries, with the same metrics. Let me read the numbers.
>
> For **urgency**, the LLM scored 0.81 accuracy. Embeddings plus KNN jumped to 0.89. And the Hybrid RAG reached **0.90**.
>
> For **medical service** — the harder task, because there are five classes — the LLM got 0.76, the KNN actually dropped to 0.72 because services are harder to separate by similarity alone, but the Hybrid RAG reached **0.83 accuracy and 0.84 macro F1.**
>
> The conclusion is clear: the Hybrid RAG wins on every metric. It keeps the fast urgency detection from the embeddings, and adds the reasoning of the LLM for the specialty. That is why **Hybrid RAG is our deployment choice**, with KNN kept as a fast fallback if we are latency-limited.

## Slide 35 — Speech-to-Text Pipeline

> For voice, we use faster-whisper, the large-v3-turbo model, running **locally**. The pipeline is: speech input, microphone capture, audio processing, voice activity detection with faster-whisper, transcript, then into the AI triage. We chose local processing for four reasons — lower latency, offline capability, better medical privacy, and less cloud dependency. It runs on common GPUs like a GTX 1660 Ti.

## Slide 36 — "Development" (divider)

> Now, briefly, how we built it.

## Slide 37 — Database Architecture

> We turned the UML class diagram into a hardened PostgreSQL schema on Supabase — 13 tables, 6 enumerated types, and 24 indexes for performance. It covers users, hospitals, doctors, appointments, triage records, and services.
>
> We chose **PostgreSQL** because our data is highly relational — patients, doctors, appointments, and triage records are all linked together — and a relational database keeps that data consistent and reliable, which is critical in healthcare.

## Slide 38 — Backend Architecture

> The backend is a modular Node.js system. We chose **Node.js with Express** because it handles many requests at once without blocking, which fits a real-time system where patients, doctors, and the AI service all talk to the server together. It uses an MVC structure, asynchronous processing, strict validation, and structured logging.
>
> One security point we are proud of: **authentication and JWT are handled by Supabase**, so identity is managed by a trusted service. And the client is never trusted with its own identity — every protected route checks JWT ownership on the server.

## Slide 39 — Frontend Development

> The frontend is cross-platform: **React with TypeScript** for the hospital web dashboard, because doctors and staff work on computers and need a rich, fast interface; and **Flutter** for the patient mobile app, because it lets us build one app for both Android and iOS from a single codebase. We use Tailwind for styling and the Web Audio API for voice capture. The two share a modular component library, and the design is voice-first for Darija-speaking users.

_(Akram hands back to Rim.)_

> To finish, Rim will cover the market value and conclusion.

---

# PART 4 — RIM

## Slide 40 — "Market & Value" (divider)

> Finally, why this matters beyond the technology.

## Slide 41 — Market & Value Proposition

> Algeria's healthcare system is under heavy pressure — millions of consultations a year, overloaded emergency rooms, very little digital intake, and almost no AI triage adapted to Darija. Most hospitals still rely on manual intake and non-prioritized routing, which causes delays and overcrowding. Najda's value is three things: Darija voice interaction, AI triage, and smart appointment routing.

## Slide 42 — Market Analysis (SWOT) _(read it as four quick blocks)_

> A quick SWOT. **Strengths:** Darija-native triage, a local speech pipeline, and end-to-end coverage — triage, booking, and emergency in one platform. **Weaknesses:** we are early — limited sales capacity, no clinical track record yet, and a small dataset compared to English. **Opportunities:** healthcare is going digital in Algeria, and there is no direct Darija-first competitor. **Threats:** public skepticism toward medical AI, slow institutional adoption, and changing data regulations.

## Slide 43 — Business Model Canvas

> Our business model connects patients, hospitals, and AI triage. The value proposition is the Darija-first experience; revenue comes from doctor and clinic subscriptions, healthcare advertising, and appointment services; and our customers are patients, doctors, and clinics.

## Slide 44 — Go-To-Market Strategy

> We roll out in three phases. **Phase one — pilot**: integrate with a few local clinics to validate the workflow. **Phase two — awareness**: digital campaigns to bring in users. **Phase three — regional expansion**: scale through multi-hospital partnerships.

## Slide 45 — Key Metrics & Projections _(TABLE — slow down)_

> These are our Year 1 targets. From an ad campaign reaching 800,000 people, we project a 6% click rate, a 25% install rate giving about 12,000 installs, at roughly 19 dinars per install. We target 25% retention at 30 days, 9,000 completed triages, a 20% booking rate, and a return on marketing investment of about +150%.

## Slide 46 — Initial Investment _(TABLE — read the total)_

> To launch and validate the first real version, we estimate a total initial investment of **1,665,000 dinars** — covering hosting, marketing, advertising, the maps API, legal costs, dataset expansion, and a contingency.

## Slide 47 — Year 1 Revenue Projection _(TABLE — read the total)_

> In the first year, with a small network, we project around **1,006,000 dinars** in revenue — mainly from doctor and clinic subscriptions, plus advertising and appointment fees.

## Slide 48 — Scaling Projection _(TABLE — read the total, show the jump)_

> And once the network expands, the model scales strongly — to about **6,756,000 dinars per year.** The same revenue streams, but with more doctors and clinics, show that Najda is financially sustainable as it grows.

## Slide 49 — "Limitations & Future Work" (divider)

> Of course, this is a prototype, and we are honest about its limits.

## Slide 50 — Limitations & Future Work

> Najda proves that Darija-aware AI triage is feasible. But three limits remain. **Dataset size** — 859 sentences is a strong start but still small. **Clinical validation** — this is a prototype, not a certified medical device. And **speech recognition** — accuracy drops in noisy environments and strong dialects.
>
> One more honest point: today we run on our own student machine, which limits the size of the model we can use. **At launch, we will have a stronger machine**, so we can run a larger, more accurate model — and we will also add more medical services beyond the current five.
>
> Our future work answers each limit: a **larger Darija corpus** for more coverage, **audio fine-tuning** on our own collected speech, and proper **evaluation metrics** like word and character error rate for the speech model.

## Slide 51 — "Conclusion" (divider)

> To conclude.

## Slide 52 — Conclusion

> Najda shows that dialect-aware AI triage is both technically feasible and practically valuable. It combines Darija speech interaction, intelligent urgency assessment, and healthcare routing in one platform. By reducing uncertainty in those first stressful moments of seeking care, Najda helps patients reach the right service faster, and helps hospitals work smarter.
>
> Thank you for your attention. We are happy to answer your questions.

---

## Quick handoff cheat-sheet

| Moment         | Who                | Line                                                                   |
| -------------- | ------------------ | ---------------------------------------------------------------------- |
| Open           | Rim                | "Good morning, we are Akram, Nasreddine and Rim…"                      |
| After slide 7  | Rim → Nasreddine   | "Now Nasreddine will present the design system."                       |
| After slide 20 | Nasreddine → Akram | "Now Akram will explain the system design and the AI."                 |
| After slide 39 | Akram → Rim        | "To finish, Rim will cover the market and conclusion."                 |
| Close          | Rim                | "Thank you for your attention. We are happy to answer your questions." |

## Tips for all three

- One presenter speaks; the other two stay quiet and still.
- If you blank, the slide title is your prompt — just describe what is on screen.
- For the demo and video: introduce it before you play it. ("Now we will show a short live demo of the main triage feature.")
- Practice the handoffs once out loud — they are where teams stumble most.
