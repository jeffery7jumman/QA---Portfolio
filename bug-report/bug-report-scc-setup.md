# Bug Report — SCC Setup Fails with “Something Went Wrong” After Final Submission

## Bug ID: `#734127`
**Category:** Secure Credit Card  
**Title:** Final step of Secure Credit Card (SCC) setup fails with generic error

---

### Feature
Credit Builder > Secure Credit Card  

### Test Run
45  

**Severity:** High  
**Priority:** Critical  
**Reproducibility:** ✅ 3/3  

---

### 🌐 Environment

- Device: BrowserStack Emulated Device  
- Platform: WebView within mobile app  
- App Version: [Redacted]  
- OS: Samsung Galaxy S25 and iPhone 16e (version used on BrowserStack)

---

### 🔁 Steps to Reproduce

1. Launch the app and complete user onboarding  
2. From the dashboard, select **Secure Credit Card (SCC)**  
3. In the internal web page:  
   - Enter income and expenses  
   - Set credit limit  
   - Add funding source  
4. On the final screen:  
   - Enter address  
   - Accept Terms of Service  
5. Tap **‘Complete’**

---

### Expected Result

User sees a **success message** with:
- Confirmation of successful setup  
- Estimated delivery date or timeline for the card  
- Option to return to the dashboard or explore more info

---

### Actual Result

After completing the SCC setup, instead of a success message, the user sees:

> **Something Went Wrong. Please try again later.**

---

### Impact

This blocks users from adding the product to their profile.

---

### Suggested Fix

- Investigate backend submission logic for the final SCC setup step  
- Validate if the error stems from:
  - API timeout  
  - Funding source mismatch  
  - Internal server validation failure  
- Improve logging and display a user-friendly fallback message if the error occurs

---
