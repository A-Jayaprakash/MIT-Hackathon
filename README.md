# 🧠 ISL2Voice: Indian Sign Language to Voice Chatbot for Doctor Consultation

## 📌 Executive Summary
**ISL2Voice** is a real-time AI-powered chatbot that translates Indian Sign Language (ISL) into **text and speech** to assist **deaf and dumb individuals** in communicating effectively with doctors. By capturing hand gestures via a webcam, the system converts sign inputs into meaningful voice responses, bridging the communication gap in healthcare settings.

---

## 🗂️ Phase-Based Implementation Timeline

| Phase | Task | Duration |
|-------|------|----------|
| Phase 1 | Dataset Collection & Preprocessing | Day 1 |
| Phase 2 | Model Training & Testing | Day 2 |
| Phase 3 | Integration with Webcam & Real-time Inference | Day 3 |
| Phase 4 | UI/UX, Output to Text + Speech, Testing | Day 4 |
| Phase 5 | Final Fixes, Error Handling, Deployment | Day 5 |

---

## ⚙️ Technical Architecture

**Input:**  
→ Live Webcam Feed (sign language gestures)

**Model:**  
→ CNN / 3D CNN / MediaPipe + LSTM (gesture recognition)  
→ Sign-to-Text NLP Translator  
→ Text-to-Speech (TTS) Engine

**Output:**  
→ Text on screen + Real-time Voice Output

---

## 🧰 Technical Stack

- **Frontend:** HTML, CSS, JavaScript (for UI), Flask or Streamlit for UI rendering  
- **Backend:** Python (Flask API)  
- **Computer Vision:** OpenCV, MediaPipe, TensorFlow/Keras or PyTorch  
- **NLP:** NLTK or Transformers (HuggingFace)  
- **Text-to-Speech:** gTTS / pyttsx3 / Google Cloud TTS  
- **Deployment:** Localhost / Render / HuggingFace Spaces  

---

## ✅ Critical Success Factors & Risk Mitigation

- **Real-time Processing:** Optimize webcam and model latency  
- **Accurate Gesture Detection:** Use reliable datasets + augmentations  
- **Dual-hand Sign Support:** Test model with both single and dual-hand gestures  
- **Fallbacks:** Provide alternative options if signs are not detected  

---

## ⚠️ High-Risk Elements

- Low-light / noisy environments
- Misclassification of similar gestures
- Processing lag for complex sentences
- Limited availability of real-time ISL datasets

---

## 📐 Scope Management

**In Scope:**
- ISL Alphabet/Word recognition
- Real-time text + voice output
- Doctor-patient chatbot interface

**Out of Scope (for MVP):**
- Full sentence construction with context
- Non-Indian sign languages

---

## 👨‍🔬 Professional Opinions & Strategic Recommendations

- Focus on **model precision** for healthcare usage  
- Use **transfer learning** if time-constrained  
- Record custom video dataset for critical signs  
- Consider multilingual TTS support  

---

## 🧩 Strategic Suggestions

- For scaling: add multilingual NLP translation (text → regional language)  
- Add doctor dashboard for quick access to translated messages  
- Extend for classroom / legal use cases  

---

## 🔁 Alternative Simplified Approach

If time-constrained:
- Use **MediaPipe HandLandmarks + Rule-based matching**
- Pre-train on ISL alphabet or words only
- Focus on one-hand gestures for MVP

---

## 🚀 Getting Started

### 💾 Installation & Setup

```bash
git clone https://github.com/yourusername/ISL2Voice.git
cd ISL2Voice
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate (Windows)
pip install -r requirements.txt
