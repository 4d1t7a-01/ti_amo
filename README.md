# ti_amo
ti amo event
# Ti Amo - Valentine's Art Therapy Event Booking Page

A premium event booking page for **Ti Amo**, featuring UPI payment integration and automatic Google Forms data collection.

## 🎨 Event Details

- **Event**: Ti Amo - Paint Your Partner Art Therapy
- **Date**: 14th February 2026 (Valentine's Day)
- **Time**: 12:00 Noon
- **Venue**: Sunder Nursery
- **Price**: ₹650 per couple
- **Includes**: Canvas painting activity, brunch, and freebies
- **Presented by**: Blessings Atelier

---

## 🚀 Quick Setup (3 Steps)

### Step 1: Upload to GitHub Pages

1. **Create GitHub Account** (if you don't have one)
   - Go to https://github.com and sign up (FREE)

2. **Create New Repository**
   - Click "+" icon → "New repository"
   - Name it: `tiamo` (or any name you like)
   - Make it **Public**
   - Click "Create repository"

3. **Upload Your File**
   - Click "Add file" → "Upload files"
   - Upload the `index.html` file
   - Click "Commit changes"

4. **Enable GitHub Pages**
   - Go to repository "Settings"
   - Click "Pages" in left sidebar
   - Under "Source", select "main" branch
   - Click "Save"
   - Wait 2-3 minutes

**Your booking page will be live at:**
```
https://YOUR-USERNAME.github.io/tiamo/
```

### Step 2: Setup Google Forms (To Receive Bookings)

**Why Google Forms?**
- FREE forever
- Get all booking data in email + spreadsheet
- No coding or database needed
- Easy to view and manage

**Setup Instructions:**

1. **Create the Form**
   - Go to https://forms.google.com
   - Click "Blank" to create new form
   - Title it "Ti Amo Bookings 2026"

2. **Add These Fields** (in this exact order):
   ```
   ✓ Partner 1 Name (Short answer, Required)
   ✓ Partner 1 Age (Short answer, Required)
   ✓ Partner 1 Email (Short answer, Required)
   ✓ Partner 1 Phone (Short answer, Required)
   ✓ Partner 2 Name (Short answer, Required)
   ✓ Partner 2 Age (Short answer, Required)
   ✓ Partner 2 Email (Short answer, Required)
   ✓ Partner 2 Phone (Short answer, Required)
   ```

3. **Get Form URL and Entry IDs**
   - Fill your form with DUMMY data:
     * Partner 1 Name: `John Doe`
     * Partner 1 Age: `25`
     * Partner 1 Email: `john@test.com`
     * Partner 1 Phone: `9876543210`
     * (same for Partner 2)
   
   - **BEFORE submitting**, click the **⋮** (three dots) menu
   - Click "Get pre-filled link"
   - Click "Get Link" and COPY the entire URL
   
   - The URL looks like:
     ```
     https://docs.google.com/forms/d/e/1FAIpQLSe...xyz/viewform?usp=pp_url&entry.123456789=John&entry.234567890=25&entry.345678901=john@test.com...
     ```

4. **Extract Information from URL**

   **A) Get Form ID:**
   - Copy the part between `/d/e/` and `/viewform`
   - Example: `1FAIpQLSe_LONG_RANDOM_STRING`
   
   **B) Get Entry Numbers:**
   - Look for `entry.XXXXXXXXX=` in the URL
   - Write them down in order:
     ```
     entry.123456789 = Partner 1 Name
     entry.234567890 = Partner 1 Age
     entry.345678901 = Partner 1 Email
     entry.456789012 = Partner 1 Phone
     entry.567890123 = Partner 2 Name
     entry.678901234 = Partner 2 Age
     entry.789012345 = Partner 2 Email
     entry.890123456 = Partner 2 Phone
     ```

5. **Update index.html File**
   
   Open `index.html` in a text editor and find this section (around line 668):
   
   ```javascript
   // ===== CONFIGURATION SECTION =====
   
   // 1. YOUR UPI ID
   const UPI_ID = "yourupiid@paytm"; // ← CHANGE THIS!
   
   // 2. YOUR GOOGLE FORM URL
   const GOOGLE_FORM_URL = "https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse";
   // ↑ Replace YOUR_FORM_ID with your actual form ID
   
   // 3. YOUR GOOGLE FORM FIELD IDs
   const FORM_FIELDS = {
       partner1_name: "entry.111111111",   // ← Replace with YOUR entry numbers
       partner1_age: "entry.222222222",
       partner1_email: "entry.333333333",
       partner1_phone: "entry.444444444",
       partner2_name: "entry.555555555",
       partner2_age: "entry.666666666",
       partner2_email: "entry.777777777",
       partner2_phone: "entry.888888888"
   };
   ```
   
   Replace:
   - `yourupiid@paytm` with your actual UPI ID
   - `YOUR_FORM_ID` with your form ID
   - All the `entry.XXXXXXX` numbers with yours

6. **Re-upload to GitHub**
   - Go to your GitHub repository
   - Click on `index.html`
   - Click the pencil icon (Edit)
   - Paste the updated code
   - Click "Commit changes"

### Step 3: Setup UPI Payment

**Option A: Your Personal UPI ID (Simplest)**
- Just update `UPI_ID` in the code with your UPI address
- Examples: `yourname@paytm`, `9876543210@ybl`, `yourname@oksbi`
- When users click "Proceed to Payment", their UPI app will open with ₹650 pre-filled

**Option B: Business UPI (More Professional)**
- Use Razorpay, Paytm, or PhonePe business account
- They provide a dedicated UPI ID for your business
- Follow same steps as Option A

---

## 📱 Creating QR Code

Once your page is live:

1. Copy your GitHub Pages URL
2. Go to any FREE QR code generator:
   - https://www.qr-code-generator.com/
   - https://www.qrcode-monkey.com/
   - Canva (search "QR code")

3. Paste your URL
4. Customize design (optional)
5. Download and print

**Print the QR code on:**
- Posters
- Flyers
- Social media graphics
- WhatsApp status

---

## 📧 How to View Bookings

### Method 1: Google Form Responses

1. Open your form at https://forms.google.com
2. Click "Responses" tab
3. See all bookings in a list
4. Download as Excel/CSV

### Method 2: Link to Google Sheets (Recommended)

1. In form's "Responses" tab
2. Click the Sheets icon (📊)
3. Create new spreadsheet
4. All bookings auto-populate in real-time!

### Method 3: Email Notifications

1. In form's "Responses" tab
2. Click ⋮ (three dots)
3. Select "Get email notifications for new responses"
4. Get instant email for each booking!

---

## ✅ Testing Your Setup

### Test the Form Submission:

1. Open your live page
2. Fill booking form with test data
3. Click "Proceed to Payment"
4. Check your Google Form → you should see the test entry!

### Test UPI Payment:

1. Use your phone
2. Click "Proceed to Payment"
3. Your UPI app should open with ₹650 pre-filled
4. Cancel the test transaction

---

## 🎯 What Happens When Someone Books?

1. **User fills booking form** on your website
2. **Clicks "Proceed to Payment"**
3. **Data is saved** to your Google Form (you get it via email/spreadsheet)
4. **UPI payment app opens** on their phone with ₹650
5. **They complete payment** using any UPI app
6. **You receive payment** in your linked bank account
7. **You confirm their booking** via email/WhatsApp manually

---

## 💡 Important Notes

### ⚠️ Manual Confirmation Required

Since UPI payments happen outside your website, you need to:
1. **Match payments to bookings**: Check time stamps
2. **Send confirmation emails**: Manually after verifying payment
3. **Keep a spreadsheet**: Track who paid vs who didn't

### 💰 Payment Tracking

Create a simple Google Sheet with these columns:
```
Name | Email | Phone | Booking Time | Payment Received? | Confirmed?
```

### 🔒 Security

- Never share your Google Form's edit link publicly
- Only share the booking page URL
- Keep UPI ID secure (but it's okay to show on payment page)

---

## 🎨 Customization Guide

### Change Event Description

Find this in the HTML (around line 625):
```html
<p class="event-description">
    Lorem ipsum dolor... <!-- Replace this text -->
</p>
```

### Change Brunch Menu

Find this (around line 650):
```html
<li>🥗 Garden Fresh Salad Bowl</li>
<!-- Change these menu items -->
```

### Change Colors

Find this in CSS (around line 11):
```css
:root {
    --color-cream: #FAF8F3;      /* Background */
    --color-charcoal: #2A2A2A;   /* Text */
    --color-gold: #C9A961;        /* Accent color */
}
```

### Change Contact Info

Find this in footer (around line 743):
```html
contact@tiamo.event  <!-- Change email -->
+91 98765 43210      <!-- Change phone -->
```

---

## 🔧 Troubleshooting

**Page not loading?**
- Wait 2-3 minutes after enabling GitHub Pages
- Check if file is named `index.html` (not `event-booking.html`)
- Make sure repository is Public

**Form not saving data?**
- Double-check entry IDs match exactly
- Make sure form URL ends with `/formResponse` not `/viewform`
- Test by filling form manually on Google Forms first

**UPI not opening?**
- Only works on mobile phones with UPI apps installed
- Desktop users need to scan QR code
- Make sure UPI_ID is correct format: `name@bank`

**Email notifications not working?**
- Check spam folder
- Enable notifications in Google Forms settings
- Add `no-reply@google.com` to contacts

---

## 🚀 Going Live Checklist

Before sharing your QR code:

- [ ] Test booking form with your own details
- [ ] Test UPI payment (cancel before completing)
- [ ] Verify data appears in Google Form responses
- [ ] Setup email notifications
- [ ] Update event description (remove Lorem Ipsum)
- [ ] Add your real UPI ID
- [ ] Add your real contact email/phone
- [ ] Test QR code on mobile
- [ ] Test on different devices (phone, tablet, desktop)
- [ ] Create social media graphics with QR code

---

## 📞 Need Help?

**Common Questions:**

1. **Can I use this without UPI?**
   - Yes! Share bank details manually via email after booking
   - Or use payment links from Razorpay/Instamojo

2. **How many bookings can I receive?**
   - Unlimited! Google Forms is free forever
   - GitHub Pages can handle thousands of visitors

3. **Can I edit the page after it's live?**
   - Yes! Just update the file on GitHub
   - Changes reflect in 1-2 minutes

4. **Do I need to pay for hosting?**
   - NO! Everything is 100% FREE
   - GitHub Pages is free
   - Google Forms is free
   - UPI is free

---

## 📊 Expected Workflow

**Day 1-10 (Before Event):**
```
Visitor scans QR → Fills form → Makes payment → You confirm booking
```

**Day 11 (Before Event):**
```
Send reminder emails to all confirmed bookings
```

**Day 12 (Event Day):**
```
Check attendees against your Google Sheet
Welcome them to Ti Amo! 🎨💕
```

---

**Made with ❤️ for Ti Amo**

*Presented by Blessings Atelier*