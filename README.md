# Hotel A/B Test: Reminder Emails Reduce No-Shows

📊 **Goal:** Test whether sending reminder emails 48h before check-in reduces hotel no-shows.

---

## 🔹 Background
No-shows waste inventory and revenue in hotels.  
This project simulates an experiment where guests are randomly assigned to:
- **Control** → no reminder
- **Treatment** → reminder email

We test if the treatment lowers the no-show rate.

---

## 🔹 Hypotheses
- **H₀:** No difference in no-show rate between control and treatment.  
- **H₁:** Treatment group has a lower no-show rate.  

---

## 🔹 Dataset
- Based on the Kaggle *Hotel Booking Demand* dataset.  
- Since `"No-show"` values were missing, we **simulate no-shows**:  
  - 8% baseline no-show rate  
  - ~25% of treatment no-shows “flipped” into arrivals (~6% effective rate).  

---

## 🔹 Methods
- Random assignment to groups (50/50).  
- **Two-proportion z-test** (one-sided) for no-show rates.  
- 95% confidence intervals for the difference.  
- Guardrails: cancellation rate, ADR (revenue), channel mix, lead time.

---

## 🔹 Results (from one run)
- Control ≈ 7.96% no-shows  
- Treatment ≈ 6.08% no-shows  
- z = 10.16, p < 0.001  
- 95% CI (p_t – p_c) = [−2.24pp, −1.52pp]  
- Guardrails stable ✅ (no adverse impact)  

---

## 🔹 Business Impact
At an ADR ≈ €120:
- Reduction ~1.8pp  
- Saves ≈ 18 rooms per 1,000 bookings  
- Extra revenue ≈ €2,160 per 1,000 bookings  

---

## 🔹 How to Run
1. Clone this repo  
2. Install requirements:  
   ```bash
   pip install -r requirements.txt
