Change Log (2025-11-28) - Added improvements from AI feedback

# Module 2 — Plan Builder (Options → Days)

## Inputs

### **User Preferences**
- Budget per day  
- Pace (relaxed vs. busy)  
- Interests (e.g., culture, food, outdoors, shopping)  
- Accessibility needs (e.g., kid-friendly, mobility)  
- Weather considerations (indoor vs. outdoor bias)

### **Activity Information (from Module 1 Options list)**
- Name and type (attraction, restaurant, park, event)  
- Location (coordinates or address)  
- Estimated duration  
- Cost range (free, low, medium, high)  
- Opening hours / reservation requirements  
- Distance or travel time from lodging and between activities  
- Theme tags (e.g., museum, nature, dining, shopping)

---

## Selection Rules

For each day, build a sequence of activities using the following guidelines:

### **Morning Activity**
- Must be near lodging (short travel time)  
- Check opening hours to ensure availability  
- Prefer lighter activities to ease into the day  

### **Midday Activity**
- Select close to the morning activity to minimize transit  
- Ensure duration fits before lunch or early afternoon  
- Respect budget constraints  

### **Afternoon Activity**
- Choose a different theme than morning/midday (e.g., culture after outdoors)  
- Verify opening hours and travel time feasibility  
- Include buffer for rest or transit  

### **Evening Restaurant or Event**
- Select near the afternoon activity  
- Ensure reservation feasibility if required  
- Optionally substitute with an event based on preferences  

---

## Constraints & Checks

- **Opening hours:** Activities must be open during the planned time slot  
- **Budget:** Daily total cost must remain within the user’s budget  
- **Travel time:** Transit between activities must be reasonable; avoid long cross-town trips  
- **Duration fit:** Activities must fit within their segment window (morning, midday, afternoon, evening)  
- **Theme variety:** Avoid repeating the same theme within a single day  
- **Weather:** Prefer indoor activities on poor weather days; offer outdoor alternatives when suitable  
- **Fallbacks:** If no suitable activity is found, insert rest time, a scenic walk, or a casual café near lodging  

---

## Loop Structure

```text
for each day:
    pick Morning activity (near lodging, open, fits budget)
    pick Midday activity (close by, feasible duration, budget check)
    pick Afternoon activity (different theme, feasible travel, open)
    pick Evening restaurant or optional event (nearby, reservation feasible)
