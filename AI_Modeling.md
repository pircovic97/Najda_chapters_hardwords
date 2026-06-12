# AI Modeling — Possible Jury Questions & Answers

## 1. Why did you build your own dataset instead of using existing medical datasets?

Most existing medical datasets are in English and contain formal clinical language. Our objective was to support Algerian users speaking Darija, Arabizi, and mixed Arabic-French expressions. Therefore, we collected and labeled our own dataset to better represent real-world patient language.

---

## 2. How many samples are in your dataset?

The final dataset contains **859 manually labeled medical sentences**.

---

## 3. What labels did you use?

The dataset contains:

### Urgency Labels

- Consultation
- Urgent

### Medical Specialties

- General Medicine
- Cardiology
- Gynecology
- Dermatology
- Gastroenterology

---

## 4. Why only 859 samples?

The dataset was manually collected, cleaned, anonymized, and labeled. While relatively small, it was sufficient to validate the feasibility of the proposed approach and compare multiple AI models.

---

## 5. How did you preprocess the data?

The preprocessing pipeline included:

- Arabizi normalization
- Spelling normalization
- Removal of emojis and irrelevant symbols
- Data cleaning
- Anonymization of personal information
- Label verification

---

## 6. Why did you choose Embeddings + KNN for urgency prediction?

Urgency classification is a relatively simple classification task.

Using:

- Multilingual E5 embeddings
- FAISS vector search
- KNN classification

provided:

- Faster inference
- Better consistency
- Higher accuracy than the prompted LLM approach

---

## 7. Why did you use Qwen 2.5?

Qwen 2.5 demonstrated strong multilingual reasoning capabilities and performed well with Darija prompts.

It was used to predict the most appropriate medical specialty based on the patient's symptoms.

---

## 8. What is Hybrid RAG in your project?

The Hybrid approach combines:

- Embeddings + KNN for urgency prediction
- Qwen 2.5 for specialty prediction

The outputs are merged into a single triage result.

---

## 9. Why not use only the LLM?

Using only the LLM introduced:

- Higher latency
- Higher computational cost
- Occasional output formatting issues

The Hybrid approach improved reliability while maintaining strong predictive performance.

---

## 10. What evaluation metrics did you use?

We evaluated:

- Accuracy
- Macro F1 Score
- Inference Time

for both:

- Urgency Prediction
- Specialty Prediction

---

## 11. What model achieved the best results?

The Hybrid RAG approach achieved the highest performance across all evaluated metrics.

### Results

| Metric           | LLM  | KNN  | Hybrid |
| ---------------- | ---- | ---- | ------ |
| Urgency Accuracy | 0.81 | 0.89 | 0.90   |
| Urgency F1       | 0.81 | 0.89 | 0.90   |
| Service Accuracy | 0.76 | 0.72 | 0.83   |
| Service F1       | 0.75 | 0.72 | 0.84   |

---

## 12. Why is F1 Score important?

Accuracy alone can be misleading.

F1 Score balances:

- Precision
- Recall

and provides a better measure of classification quality, especially when class distributions are uneven.

---

## 13. What is FAISS?

FAISS (Facebook AI Similarity Search) is a vector search library used to efficiently retrieve the nearest embeddings from the dataset.

It enables fast similarity-based classification.

---

## 14. Why use embeddings?

Embeddings convert text into numerical vectors that preserve semantic meaning.

For example:

"3andi wja3 f kerchi"
and
"بطني توجعني"

can produce similar embeddings even though the wording differs.

---

## 15. What are the limitations of your AI model?

- Limited dataset size (859 samples)
- No clinical validation yet
- Possible errors for unseen expressions
- Limited specialty coverage

---

## 16. Is Najda replacing doctors?

No.

Najda is a decision-support and triage tool.

Its purpose is to guide patients toward the appropriate level of care and medical specialty, not to provide diagnoses or replace healthcare professionals.

---

## 17. How could the model be improved?

Future improvements include:

- Larger Darija datasets
- Clinical validation
- Fine-tuning on medical data
- Additional specialties
- Continuous learning from real-world usage

---

## 18. Why is this project innovative?

Najda combines:

- Darija speech interaction
- Speech-to-text processing
- AI-powered urgency prediction
- Specialty recommendation
- Appointment routing

within a single healthcare platform designed specifically for Algerian users.
