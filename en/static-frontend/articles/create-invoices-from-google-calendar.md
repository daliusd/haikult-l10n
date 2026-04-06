---
title: 'How to Create Invoices from Google Calendar Events (Step-by-Step Guide)'
date: '2026-01-08'
modified: '2026-01-08'
showDate: true
---

If you're a consultant, coach, therapist, or any service professional who bills by appointment, you know the monthly drill: open your calendar, count sessions for each client, then manually create invoices one by one. It's tedious, time-consuming, and prone to errors.

What if your calendar could simply become your invoices?

That's exactly what Haiku.lt's "Create from Calendar" feature does. In this guide, I'll walk you through how to transform your Google Calendar appointments into professional invoices in minutes, not hours.

## Who Benefits from This Feature?

This feature is perfect for anyone who bills by appointment or session:

- **Consultants** - Strategy sessions, advisory calls, project meetings
- **Coaches** - Life coaching, business coaching, career counseling
- **Therapists & Psychologists** - Individual therapy sessions, group sessions
- **Tutors & Teachers** - Language lessons, music lessons, academic tutoring
- **Personal Trainers** - One-on-one training sessions, group classes
- **Dance Teachers** - Private lessons, group classes
- **Healthcare Professionals** - Physiotherapy, massage therapy, alternative medicine
- **Legal Advisors** - Consultation hours
- **Nutritionists & Dietitians** - Client consultations

If you schedule appointments in Google Calendar and need to invoice for those sessions, this feature will save you hours every month.

## The Problem: Manual Invoice Creation

Let's meet Sofia, a psychotherapist in Amsterdam with a busy practice. She sees about 30 clients per week, offering both individual and couples therapy sessions at different rates.

Every month, Sofia faces the same tedious task: reviewing her calendar, counting sessions for each client, and creating 25-30 invoices manually. Between checking appointment histories, calculating quantities, and entering data, it takes her nearly 2 hours.

And she's not alone. Whether you're a yoga instructor in Rome, a business coach in Paris, or a piano teacher in Vienna, if you bill by appointment, you've experienced this frustration.

## The Solution: Calendar-to-Invoice Automation

Haiku.lt's calendar integration automatically converts your Google Calendar events into invoices. Here's the magic:

- **Each unique event title becomes a client invoice**
- **The number of appointments becomes the quantity**
- **All your billing data is pre-filled from previous invoices**
- **You review and customize before creating anything**

What used to take Sofia 2 hours now takes 10 minutes.

## Prerequisites: What You Need

Before starting, make sure you have:

1. **A Haiku.lt account** - Sign up at haiku.lt (free for up to 500 invoices)
2. **Google Calendar with your appointments** - Use client names as event titles for best results
3. **Google Calendar permission** - Granted when you sign in with Google

Important: Haiku.lt doesn't store your calendar data. It only fetches event titles and dates temporarily to create invoices. Your calendar remains private.

## Step 1: Access the Feature

After signing in to Haiku.lt, you'll see your dashboard. Look for the "Create from Calendar" button. Click it to launch the 4-step wizard.

The button's tooltip explains: "Create multiple invoices from Google Calendar events. Each unique event name becomes a buyer, and the number of occurrences becomes the quantity."

## Step 2: Configure Your Calendar Import

The first screen asks you to configure how invoices will be created. Let's walk through each field:

### Select Calendar

Choose which Google Calendar contains your billable appointments. If you have multiple calendars, select the one where you track client sessions. Your primary calendar will be marked as "(Primary)".

**Pro tip:** Consider creating a dedicated "Billable Sessions" calendar separate from your personal appointments. This makes invoicing cleaner and faster.

### Date Range

Set the period for which you want to create invoices. The system defaults to the current month (first to last day), but you can choose any date range.

As you adjust the dates, the system counts how many events exist in that period and displays the count. If you see "No events found," double-check your calendar selection and date range.

**Common pattern:** Most professionals invoice monthly, so selecting the previous month at the start of each new month works perfectly.

### Invoice Series

Enter a series name for these invoices (for example, "CONSULTING", "THERAPY", "LESSONS"). If you've created invoices before, the system suggests your recent series names.

Invoice series help you organize invoices by type or year. For example, "2026-COACHING" or simply "SESSIONS".

### Seller Information

Enter your business details - your name or company name, address, tax ID, and any other information you want on the invoice. If you've created invoices in this series before, this field auto-fills with your previous information.

### Invoice Issued By

Enter the name of who's issuing the invoice (usually your name). Like the seller field, this auto-fills from your previous invoices.

### Line Item Configuration

Now configure what appears on each invoice as the billable service:

**Line Item Name** - What you're billing for (e.g., "Therapy Session", "Consulting Hour", "Piano Lesson"). The system remembers your previous line items and suggests them.

**Default Price (per unit)** - Your standard rate per session. Enter the amount in your currency (euros for Eurozone users).

**VAT %** - If you're a VAT-registered business, enter your VAT percentage. This field only appears if you've enabled VAT in your settings.

**Unit** - The unit of measurement for your service. The default is "pieces" which works for most session-based billing. You can also choose "hours" or other units from the dropdown.

**Pro tip:** When you start typing in Line Item Name, if you've used that item before, the system automatically fills in the price, VAT, and unit based on your history. This ensures consistency.

Once all required fields are filled and the system finds at least one calendar event, the "Next" button becomes active.

## Step 3: Review and Edit Your Invoices

This is where the magic happens. The system has grouped your calendar events by title and prepared draft invoices. Here's what you'll see:

### How Events Become Invoices

The system analyzes your calendar events and applies this logic:

- **Groups events by title** - All events with the same name are grouped together
- **Each unique title becomes one invoice** - "Marie Dubois" appointments become one invoice for Marie
- **Counts occurrences** - If "Marie Dubois" appears 4 times, the quantity is 4
- **Automatically excludes** - Events without titles and appointments you've declined are skipped

### Smart Pre-filling

For each client name, Haiku.lt looks at your invoice history and automatically fills in:

- Email address
- Country
- Tax ID
- Preferred invoice language
- Last price you charged them for this specific service

This is incredibly powerful. If you charged Marie €80 per session last month and Pierre €100 per session (perhaps he's a corporate client), the system remembers and sets those prices automatically.

### The Review Table

You'll see a table with one row per client, showing:

- **Buyer Name** - The event title from your calendar (editable)
- **Quantity** - Number of appointments (editable)
- **Email** - Client's email if previously used (editable)
- **Country** - Client's country (editable)
- **Tax ID** - Client's tax ID if known (editable)
- **Invoice Language** - Which language for the PDF, with 39 options including English, German, French, Spanish, Italian, Dutch, Portuguese, and more (editable)
- **Price (per unit)** - The rate for this specific client (editable)

Everything is editable. You can:

- Adjust quantities if you counted differently
- Update email addresses
- Change pricing for specific clients
- Set different invoice languages for international clients
- Remove clients you don't want to invoice yet
- Add additional clients manually with the "+ Add Buyer" button

**Example scenario:** Sofia sees these grouped appointments:

- Marie Dubois: 4 sessions
- Jan de Vries: 4 sessions  
- Anna Schmidt: 5 sessions
- Combined couples session (Marie & Jan): 2 sessions

She can adjust the "Combined couples session" to split between the two clients, or leave it as a separate invoice. The flexibility is yours.

If you're creating more than 50 invoices, the system shows a warning that it may take several minutes. For most users, though, batch sizes are 10-30 invoices which complete very quickly.

When everything looks correct, click "Create X Invoice(s)" to proceed.

## Step 4: Creating Invoices

The system now creates your invoices one by one. You'll see a progress bar showing "Creating invoice X of Y..." as it works through your list.

Behind the scenes, the system:

- Creates each invoice with an auto-incrementing number
- Generates a professional PDF
- Applies your PDF style preferences (you can choose from 5 styles in your settings)
- Runs any automation rules you've configured
- Checks your account limits (free accounts: 500 invoices total, Pro: unlimited)

For most batches, this completes in under 2 minutes. Larger batches may take longer, but the system keeps working - you can wait or come back later.

If you're on the free plan and approaching the 500 invoice limit, the system will alert you before creating invoices that would exceed your limit.

## Step 5: Review Results

Success! The final screen shows you what was created:

The summary badge displays: "X succeeded, Y failed out of Z total"

### Successfully Created Invoices

You'll see a table of all created invoices with:

- Series and number (e.g., "THERAPY-045")
- Buyer name
- "View" link to see the invoice details

### Failed to Create (if any)

If any invoices couldn't be created (perhaps due to validation errors or limit reached), they're shown here with error messages so you can understand what went wrong.

### Next Steps

From this screen, you can:

- **Back to Dashboard** - Return to your main invoice list
- **Create More from Calendar** - Start the wizard again for another date range
- **Use Multi-Edit to Send/Save** - This is powerful! It takes you to the Multi-Edit wizard where you can:
  - Send all invoices via Gmail in one batch
  - Save all PDFs to Google Drive at once
  - Lock all invoices after sending
  - Mark them as paid when payments arrive

## Real-World Workflow Example

Let's see how Luca, a business coach in Milan, uses this feature monthly:

### Luca's Setup

- **Google Calendar:** "Client Coaching" calendar separate from personal calendar
- **Event naming:** Client name as event title (e.g., "Startup Italia", "Marco Rossi")
- **Billing cycle:** First week of each month for previous month
- **Rates:** Standard €120/hour, some VIP clients at €150/hour

### Luca's Monthly Process

**Day 1 of new month:**

1. Opens Haiku.lt, clicks "Create from Calendar"
2. Selects "Client Coaching" calendar
3. Sets date range: Previous month (e.g., December 1-31)
4. Configures:
   - Series: "2026-COACHING"
   - Line item: "Business Coaching Session"
   - Default price: €120
   - Unit: hours
5. Clicks "Next"

**Review screen:**

6. Sees 18 invoices for 10 different clients
7. Most clients have correct €120 rate (auto-filled from history)
8. Adjusts 2 VIP clients to €150 (the system remembered this from last month, but he double-checks)
9. Changes invoice language:
   - Italian for local clients
   - English for international startup clients
10. Removes one test event that was in his calendar
11. Clicks "Create 17 Invoices"

**Results:**

12. All 17 invoices created successfully in about 90 seconds
13. Clicks "Use Multi-Edit to Send/Save"
14. Selects all invoices, sends them via Gmail with his custom template
15. Saves all PDFs to his "2026 Invoices" folder in Google Drive

**Total time:** 8 minutes from start to finish

**Previous manual process:** Would have taken 90-120 minutes

**Monthly time savings:** 82-112 minutes (about 17 hours per year!)

## Pro Tips and Best Practices

### Calendar Organization

**Use consistent event naming:** Make sure each client's events use the exact same name. "Marie Dubois" and "marie dubois" are treated as different clients. Pick a naming convention and stick to it.

**Create a dedicated billable calendar:** Instead of mixing personal and billable events, create a separate Google Calendar for client sessions. This makes the feature cleaner and faster to use.

**Decline events you don't want billed:** If you have a pro bono session or a meeting that shouldn't be invoiced, decline it in Google Calendar. The system automatically excludes events you've declined.

**Use calendar colors:** Color-code different types of sessions or client categories in Google Calendar. While this doesn't affect invoicing, it helps you visually organize your schedule.

### Pricing Strategies

**Let the system remember client-specific rates:** The system stores the last price you used for each client and line item combination. If you have tiered pricing (standard clients at €80, premium at €100), after the first month, these rates auto-fill correctly.

**Set your default rate for new clients:** In the configuration step, your default price applies to any client who doesn't have a history. Set it to your most common rate.

**Review before creating:** Always check the review table before clicking create. It's your chance to catch any scheduling irregularities or apply special discounts.

### Batch Operations

After creating calendar invoices, the Multi-Edit wizard is your best friend:

**Send all at once:** Select all newly created invoices and send them via Gmail in one action. You can choose different email templates and customize the message.

**Save to Google Drive:** Batch-save all PDFs to a specific folder in your Google Drive for record-keeping.

**Lock invoices:** After sending, lock all invoices at once to prevent accidental edits.

**Track payments:** As payments arrive, use Multi-Edit to mark multiple invoices as paid.

### Multi-language Considerations

If you work with international clients across Europe:

- **Set language per client:** In the review step, you can set each invoice to a different language
- **39 languages supported:** All EU languages plus Norwegian, Serbian, Ukrainian, Turkish, and more
- **Language is remembered:** Once you set a client's preferred language, the system remembers for next time

Example: Elena, a yoga instructor in Barcelona, teaches both locals and expats. Her Spanish clients get invoices in Spanish (Español), her English students get English invoices, and her German clients get German (Deutsch) invoices. The system remembers each person's preference.

### Avoiding Common Mistakes

**Check event titles before starting:** Review your calendar first. If you see inconsistent naming (some events say "Client: John" and others say "John Smith"), clean those up first for cleaner grouping.

**Review quantities:** Before clicking create, verify the quantities make sense. If a client shows 12 sessions but you know they only had 4, check your calendar for duplicates or incorrectly titled events.

**Don't forget email addresses:** While optional, having email addresses in the review step saves time later when you want to send invoices. Add any missing emails during review.

**Use meaningful series names:** Instead of "2026-1", use descriptive series like "2026-COACHING" or "JAN-THERAPY". Future-you will appreciate clear organization.

## Frequently Asked Questions

**Q: Does Haiku.lt store my calendar data?**

A: No. Calendar data is fetched temporarily only when you use this feature. Only the event titles and dates are read to calculate quantities. Your calendar contents are never permanently stored, and Haiku.lt can't access calendar data unless you're actively using this feature.

**Q: What if I have recurring events in my calendar?**

A: Perfect! Recurring events are automatically expanded to individual occurrences. If you have "Marie Dubois - Weekly Session" repeating every Tuesday, each occurrence counts separately. So 4 Tuesdays = quantity of 4.

**Q: Can I exclude certain events without deleting them from my calendar?**

A: Yes, two ways: (1) Decline the event in Google Calendar - declined events are automatically excluded, or (2) Simply remove that client from the review table before clicking create.

**Q: What if I have more than 50 clients in one month?**

A: The feature works fine, though you'll see a warning that creation may take a few minutes. If you have this volume regularly, consider upgrading to Pro (€5/month) for unlimited invoices. The free plan includes 500 invoices total, which might run out quickly with high volume.

**Q: Can I use different prices for different clients?**

A: Absolutely! This is one of the best features. In the review step, each client's price is editable. The system remembers what you charged them last time, so if you have tiered pricing, it auto-fills correctly after the first month.

**Q: What about all-day events?**

A: They're included and count as one occurrence each. The system treats all-day events the same as timed events for billing purposes.

**Q: My calendar has appointments in two different categories (individual and group sessions). Can I handle both?**

A: You can run the wizard twice - once for each line item type. First create invoices for "Individual Therapy Session" at one rate, then run it again for "Group Therapy Session" at a different rate. Or you can manually adjust in the review step.

**Q: What if I made a mistake and want to delete the invoices?**

A: No problem. You can delete invoices individually or use the Multi-Edit wizard to select and delete multiple invoices at once. Just make sure you haven't sent them yet, as deleting sent invoices may confuse clients.

## Beyond Calendar Invoices: Other Haiku.lt Features

Once your invoices are created, explore these features:

**Multi-Edit Wizard** - Batch operations for sending, locking, marking as paid, and more. Essential after creating calendar invoices.

**Custom Email Templates** - Design beautiful invoice emails with your logo and brand colors using MJML templates, or choose from 5 built-in templates.

**Google Drive Integration** - Automatically save invoice PDFs to Google Drive with one click. Keep organized folders by month or client.

**JavaScript Automation** - For power users: write JavaScript programs to automatically fill the "Additional Information" field with payment terms, due dates, or conditional content.

**39-Language Support** - Create invoices in any European language plus many others. Perfect for international work.

**Multi-Currency Support** - Bill in any of 150+ currencies, with proper formatting and symbols.

**Statistics & Reporting** - Track income by client, compare periods, analyze payment patterns, and export to CSV for your accountant.

## Conclusion: Save Time, Bill More

If you bill by appointment, the calendar-to-invoice feature is a game-changer. What used to take hours now takes minutes, and the risk of underbilling (forgetting to count a session) or overbilling (double-counting) virtually disappears.

Whether you're a therapist in Brussels, a coach in Dublin, or a dance teacher in Lisbon, your calendar already contains your billing data. Why enter it twice?

### Ready to Try It?

**For Existing Users:** Sign in to Haiku.lt and click "Create from Calendar" on your dashboard. If you haven't granted calendar permission yet, you'll be prompted to re-authenticate.

**New Users:** Sign up free at haiku.lt (no credit card required). You get 500 invoices on the free plan, which is plenty to test this feature and see the time savings for yourself.

**Questions?** Email support at dalius.dobravolskas@gmail.com

The next time you face the monthly invoicing task, remember: your calendar is already done. Just convert it to invoices and get back to what you do best - serving your clients.

---

**More helpful guides:**

- [How to Send Professional Invoices from Your Gmail Account](/en/gmail-invoice-sending)
- [Invoice Management for Freelancers](/en/invoice-management)
- [Multi-Language Invoicing Across Europe](/en/help)
