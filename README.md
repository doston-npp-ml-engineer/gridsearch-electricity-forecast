# ⚡ Electricity Price Prediction — GridSearchCV bilan Hyperparameter Tuning

Ushbu loyiha Avstraliyaning New South Wales elektr bozori ma'lumotlari asosida, 
elektr narxining **oshishi (UP)** yoki **tushishi (DOWN)**ni bashorat qiluvchi 
RandomForest classifier modelini quradi va uni **GridSearchCV** yordamida sozlaydi.

## 📊 Dataset

- **Manba:** [OpenML — electricity](https://www.openml.org/search?type=data&status=active&id=151)
- **Hajmi:** 45,312 qator, 8 feature
- **Target:** narx UP yoki DOWN (binary classification)
- **Kontekst:** Avstraliyaning New South Wales elektr bozorida narxlar 
  talab va taklifga qarab har 5 daqiqada belgilanadi

## 🔧 Ishlatilgan texnologiyalar

- Python, scikit-learn, pandas
- RandomForestClassifier
- GridSearchCV (cv=5)
- Streamlit (natijalarni vizuallashtirish uchun)

## 📈 Natijalar

| Model | Test Accuracy |
|---|---|
| Baseline (default) | 0.9062 |
| Tuned (GridSearchCV) | 0.9064 |

**Eng yaxshi parametrlar:** `n_estimators=200`, `max_depth=None`

## 📁 Fayllar tuzilishi

- `notebook.ipynb` — to'liq tahlil: dataset tayyorlash, baseline model, 
  GridSearchCV, natijalarni solishtirish
- `app.py` — Streamlit dashboard (natijalarni interaktiv ko'rsatish)
- `best_model.pkl` — GridSearch topgan eng yaxshi model (saqlangan)
- `requirements.txt` — kerakli kutubxonalar ro'yxati

## 🚀 Ilovani ishga tushirish

\`\`\`bash
pip install -r requirements.txt
streamlit run app.py
\`\`\`

## 📝 Xulosa

GridSearchCV ushbu dataset uchun accuracy'ni sezilarli darajada oshirmadi 
(0.9062 → 0.9064), chunki RandomForest'ning default sozlamalari allaqachon 
bu dataset uchun yaxshi natija bergan edi. Bu — hyperparameter tuning har 
doim katta yaxshilanish bermasligini ko'rsatuvchi misol.
