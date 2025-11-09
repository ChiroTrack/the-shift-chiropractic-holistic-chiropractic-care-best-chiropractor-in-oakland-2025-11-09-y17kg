# The Shift Chiropractic Landing Page - Maintenance & Customization Guide

A comprehensive guide for maintaining, updating, and customizing your chiropractic landing page. This document covers everything from basic text updates to advanced customizations, written for developers at all skill levels.

---

## Table of Contents

1. [Quick Start Overview](#quick-start-overview)
2. [Part 1: Updating Text and Content](#part-1-updating-text-and-content)
3. [Part 2: Fixing Broken Links](#part-2-fixing-broken-links)
4. [Part 3: Linking Privacy and Terms Pages](#part-3-linking-privacy-and-terms-pages)
5. [Understanding the Design System](#understanding-the-design-system)
6. [Tailwind CSS Classes Guide](#tailwind-css-classes-guide)
7. [Common Customizations](#common-customizations)
8. [Troubleshooting](#troubleshooting)

---

## Quick Start Overview

This landing page is built with:
- **HTML5** - The structure and content
- **Tailwind CSS** - For responsive styling (via CDN)
- **Font Awesome** - For icons
- **Vanilla JavaScript** - For interactive features (mobile menu, FAQ accordion)

### File Structure You Should Have
```
your-project-folder/
├── index.html          (Main landing page)
├── privacy.html        (Privacy policy - needs to be created)
├── terms.html          (Terms of service - needs to be created)
└── blog.html           (Blog page - optional)
```

### Before Making Changes
1. **Make a backup** of your `index.html` file
2. **Use a code editor** like VS Code, Sublime Text, or Notepad++
3. **Test changes** in a browser after saving
4. **Use browser DevTools** (F12 or right-click → Inspect) to debug

---

## Part 1: Updating Text and Content

This section shows you exactly where to find and modify every piece of text on your landing page.

### Section 1.1: Header & Navigation Text

**Location:** Lines 44-65 (approximately)

The header contains your logo name and navigation menu links.

#### Current Code:
```html
<!-- Logo -->
<div class="flex items-center gap-3">
    <div class="w-10 h-10 rounded-full" style="background-color: var(--primary);"></div>
    <span class="font-bold text-xl hidden sm:block">The Shift</span>
</div>
```

#### How to Update:
To change "The Shift" to your business name:

1. Find the text `The Shift` in the header section
2. Replace it with your business name
3. Save the file (Ctrl+S or Cmd+S)

**Example:**
```html
<span class="font-bold text-xl hidden sm:block">Your Clinic Name</span>
```

**Understanding the Classes:**
- `font-bold` - Makes text bold
- `text-xl` - Sets text size (extra large)
- `hidden sm:block` - Hides on mobile, shows on small screens and up

#### Navigation Menu Items:
**Location:** Lines 50-57 (Desktop menu)

```html
<div class="hidden md:flex items-center gap-8">
    <a href="#features" class="text-gray-300 hover:text-white transition-colors duration-300">Features</a>
    <a href="#benefits" class="text-gray-300 hover:text-white transition-colors duration-300">Benefits</a>
    <a href="#about" class="text-gray-300 hover:text-white transition-colors duration-300">About</a>
    <a href="#testimonials" class="text-gray-300 hover:text-white transition-colors duration-300">Testimonials</a>
    <a href="#faq" class="text-gray-300 hover:text-white transition-colors duration-300">FAQ</a>
```

To add or remove menu items:

1. To **add a new menu item**, copy an existing line:
```html
<a href="#contact" class="text-gray-300 hover:text-white transition-colors duration-300">Contact</a>
```

2. To **remove a menu item**, delete the entire `<a>` line

3. The `href="#section-id"` links to sections with matching `id` attributes (e.g., `id="features"`)

**Important:** Keep the same classes to maintain consistent styling.

---

### Section 1.2: Hero Section (Main Banner)

**Location:** Lines 96-142

This is the large banner at the top with your main headline and call-to-action.

#### Current Hero Text:
```html
<h1 class="section-heading mb-6">
    The Shift Chiropractic
</h1>
<p class="section-subheading">
    Experience holistic chiropractic care from the best chiropractor in Oakland, CA. 
    We're dedicated to restoring your body's natural alignment and vitality through 
    personalized, hands-on treatment.
</p>
```

#### How to Update:

**To change the main headline:**
```html
<h1 class="section-heading mb-6">
    Your New Headline Here
</h1>
```

**To change the subheading (description):**
```html
<p class="section-subheading">
    Your new description text here. Make it compelling and clear about your services.
</p>
```

**Class Breakdown:**
- `section-heading` - Large, responsive headline (defined in `<style>` section)
- `section-subheading` - Medium-sized descriptive text
- `mb-6` - Margin bottom (space below the element)

#### Hero Statistics Section:
**Location:** Lines 131-148

```html
<div class="grid grid-cols-3 gap-4 pt-8">
    <div class="flex flex-col gap-2">
        <p class="text-3xl font-bold text-[#FF5A5F]">7</p>
        <p class="text-sm text-gray-400">Days Open Weekly</p>
    </div>
    <div class="flex flex-col gap-2">
        <p class="text-3xl font-bold text-[#FFD166]">500+</p>
        <p class="text-sm text-gray-400">Happy Patients</p>
    </div>
    <div class="flex flex-col gap-2">
        <p class="text-3xl font-bold text-[#FF5A5F]">10+</p>
        <p class="text-sm text-gray-400">Years Experience</p>
    </div>
</div>
```

**To update statistics:**

1. Change the number (e.g., `7` → `6` or `500+` → `1000+`)
2. Change the label (e.g., `Days Open Weekly` → `Hours Daily`)

**Example:**
```html
<p class="text-3xl font-bold text-[#FF5A5F]">24/7</p>
<p class="text-sm text-gray-400">Emergency Support</p>
```

---

### Section 1.3: Features Section

**Location:** Lines 155-210

This section has three feature cards highlighting your key differentiators.

#### Current Structure:
```html
<h2 class="section-heading mb-4">Why Choose The Shift Chiropractic?</h2>
<p class="section-subheading max-w-3xl mx-auto">
    We've revolutionized chiropractic care in Oakland with a patient-first approach 
    that combines traditional expertise with modern wellness practices.
</p>
```

**To update the Features heading:**
```html
<h2 class="section-heading mb-4">Your New Features Heading</h2>
```

**To update the Features subheading:**
```html
<p class="section-subheading max-w-3xl mx-auto">
    Your new description of why customers should choose you.
</p>
```

#### Feature Cards - Detailed Breakdown:

**Location:** Lines 176-210

Each feature card contains:
1. An icon (SVG)
2. A title
3. A description

**Feature 1 - Example:**
```html
<div class="card-base group">
    <div class="w-16 h-16 rounded-2xl flex items-center justify-center mb-6" 
         style="background-color: rgba(255, 90, 95, 0.1);">
        <svg class="w-8 h-8" style="color: var(--primary);" fill="none" 
             stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" 
                  d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path>
        </svg>
    </div>
    <h3 class="text-xl font-bold mb-3 text-white">Open 7 Days a Week</h3>
    <p class="text-gray-400 leading-relaxed">
        We understand that your schedule matters. That's why we're open every 
        single day of the week...
    </p>
</div>
```

**To update a feature card:**

1. **Change the title:**
```html
<h3 class="text-xl font-bold mb-3 text-white">Your New Feature Title</h3>
```

2. **Change the description:**
```html
<p class="text-gray-400 leading-relaxed">
    Your new feature description. Explain the benefit clearly and concisely.
</p>
```

3. **Change the icon color** (optional):
- Find `style="background-color: rgba(255, 90, 95, 0.1);"` 
- Keep the format but adjust the RGB values
- Current colors: Red (255, 90, 95) and Yellow (255, 209, 102)

**Class Guide for Feature Cards:**
- `card-base` - Base styling with hover effects
- `group` - Enables group hover effects
- `text-xl` - Title size
- `text-gray-400` - Lighter gray text for descriptions
- `leading-relaxed` - Line spacing for readability

---

### Section 1.4: Benefits Section

**Location:** Lines 214-310

This section has a two-column layout with benefits on the left and an image placeholder on the right.

#### Section Heading:
```html
<h2 class="section-heading mb-4">Experience Comprehensive Care</h2>
<p class="section-subheading max-w-3xl mx-auto">
    Our holistic approach to chiropractic care addresses your unique health needs 
    with personalized treatment plans designed for optimal wellness.
</p>
```

**To update:**
```html
<h2 class="section-heading mb-4">Your New Benefits Heading</h2>
<p class="section-subheading max-w-3xl mx-auto">
    Your new description of your comprehensive care approach.
</p>
```

#### Individual Benefit Items:

**Location:** Lines 233-280 (three benefit items)

**Structure of One Benefit:**
```html
<div class="flex gap-6">
    <div class="flex-shrink-0">
        <div class="flex items-center justify-center h-12 w-12 rounded-full" 
             style="background-color: rgba(255, 90, 95, 0.2);">
            <svg class="w-6 h-6" style="color: var(--primary);" fill="none" 
                 stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" 
                      d="M14 10l-2 1m0 0l-2-1m2 1v2.5M20 7l-2 1m2-1l-2-1m2 1v2.5M14 4l-2 1m2-1l-2-1m2 1v2.5"></path>
            </svg>
        </div>
    </div>
    <div>
        <h3 class="text-lg font-bold mb-2">Hands-On Full Body Adjustments</h3>
        <p class="text-gray-400 leading-relaxed">
            Our expert chiropractors use advanced techniques to realign your entire body...
        </p>
    </div>
</div>
```

**To update a benefit:**

1. **Change the benefit title:**
```html
<h3 class="text-lg font-bold mb-2">Your New Benefit Title</h3>
```

2. **Change the benefit description:**
```html
<p class="text-gray-400 leading-relaxed">
    Your detailed explanation of this benefit and why it matters to customers.
</p>
```

3. **Change the icon color** (optional):
- Red: `rgba(255, 90, 95, 0.2)`
- Yellow: `rgba(255, 209, 102, 0.2)`

---

### Section 1.5: About Us Section

**Location:** Lines 314-340

This section provides background information about your business.

#### Current Structure:
```html
<h2 class="section-heading mb-4">About The Shift Chiropractic</h2>
```

**To update the heading:**
```html
<h2 class="section-heading mb-4">About Your Business Name</h2>
```

#### About Us Content:

**Location:** Lines 343-360

```html
<div class="space-y-8 text-gray-300 leading-relaxed">
    <p class="text-lg">
        Founded in 2014, The Shift Chiropractic emerged from a simple yet powerful vision...
    </p>
    <p class="text-lg">
        At The Shift Chiropractic, our mission is to empower every patient...
    </p>
</div>
```

**To update the About Us text:**

1. **First paragraph** - Usually covers history and founding
```html
<p class="text-lg">
    Your business history goes here. When was it founded? By whom? What was the original vision?
</p>
```

2. **Second paragraph** - Usually covers mission and values
```html
<p class="text-lg">
    Your mission statement goes here. What do you do? Why do you do it? What are your core values?
</p>
```

**Class Breakdown:**
- `space-y-8` - Vertical spacing between paragraphs
- `text-lg` - Large text size
- `text-gray-300` - Light gray text color
- `leading-relaxed` - Comfortable line spacing

---

### Section 1.6: Testimonials Section

**Location:** Lines 364-428

This section displays customer reviews and ratings.

#### Section Heading:
```html
<h2 class="section-heading mb-4">What Our Patients Say</h2>
<p class="section-subheading max-w-3xl mx-auto">
    Real stories from real patients who've experienced the transformative power 
    of The Shift Chiropractic's personalized care approach.
</p>
```

#### Individual Testimonial Cards:

**Location:** Lines 381-410 (first testimonial as example)

```html
<div class="testimonial-card">
    <div class="flex items-center gap-4 mb-4">
        <div class="w-12 h-12 rounded-full" style="background-color: var(--primary);"></div>
        <div>
            <p class="font-bold text-white">Sarah Mitchell</p>
            <p class="text-sm text-gray-400">Marketing Executive</p>
        </div>
    </div>
    <div class="star-rating">
        <span class="star">★</span>
        <span class="star">★</span>
        <span class="star">★</span>
        <span class="star">★</span>
        <span class="star">★</span>
    </div>
    <p class="text-gray-300 leading-relaxed">
        "I came to The Shift Chiropractic suffering from chronic neck and shoulder pain..."
    </p>
</div>
```

**To update a testimonial:**

1. **Change the customer name:**
```html
<p class="font-bold text-white">New Customer Name</p>
```

2. **Change the customer title/role:**
```html
<p class="text-sm text-gray-400">Their Job Title or Description</p>
```

3. **Adjust the star rating:**
   - Each `★` represents one star
   - Remove stars for lower ratings
   - Add stars for higher ratings (max 5)

```html
<!-- 4-star rating -->
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>

<!-- 3-star rating -->
<span class="star">★</span>
<span class="star">★</span>
<span class="star">★</span>
```

4. **Change the testimonial text:**
```html
<p class="text-gray-300 leading-relaxed">
    "The actual testimonial from the customer goes here. Keep it authentic and specific."
</p>
```

5. **Change the avatar color:**
```html
<!-- Red avatar -->
<div class="w-12 h-12 rounded-full" style="background-color: var(--primary);"></div>

<!-- Yellow avatar -->
<div class="w-12 h-12 rounded-full" style="background-color: var(--accent);"></div>
```

---

### Section 1.7: Call-to-Action (CTA) Section

**Location:** Lines 432-450

This is the section encouraging visitors to book an appointment.

#### Current Structure:
```html
<h2 class="section-heading mb-6">Ready to Experience the Shift?</h2>
<p class="section-subheading mb-8 max-w-2xl mx-auto">
    Don't let pain hold you back any longer. Schedule your first appointment today 
    and discover why hundreds of Oakland residents trust The Shift Chiropractic 
    for their wellness journey.
</p>
```

**To update:**

1. **Change the headline:**
```html
<h2 class="section-heading mb-6">Your New CTA Headline</h2>
```

2. **Change the description:**
```html
<p class="section-subheading mb-8 max-w-2xl mx-auto">
    Your compelling call-to-action message that motivates visitors to book.
</p>
```

---

### Section 1.8: FAQ Section

**Location:** Lines 454-520

This section contains frequently asked questions with expandable answers.

#### Section Heading:
```html
<h2 class="section-heading mb-4">Frequently Asked Questions</h2>
<p class="section-subheading">
    Find answers to common questions about our chiropractic services and treatment approach.
</p>
```

#### Individual FAQ Items:

**Location:** Lines 471-520 (five FAQ items)

**Structure of One FAQ Item:**
```html
<div class="faq-item">
    <div class="faq-question">
        <span>What conditions can chiropractic care treat?</span>
        <svg class="faq-icon" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" 
                  d="M19 14l-7 7m0 0l-7-7m7 7V3"></path>
        </svg>
    </div>
    <div class="faq-answer hidden">
        <p>
            Chiropractic care is effective for a wide range of conditions including 
            back pain, neck pain, headaches...
        </p>
    </div>
</div>
```

**To update an FAQ item:**

1. **Change the question:**
```html
<span>Your new FAQ question goes here?</span>
```

2. **Change the answer:**
```html
<div class="faq-answer hidden">
    <p>
        Your detailed answer to the question. Be clear, helpful, and informative.
    </p>
</div>
```

3. **To add a new FAQ item**, copy the entire `<div class="faq-item">` block and paste it before the closing `</div>` of the FAQ container

4. **To remove an FAQ item**, delete the entire `<div class="faq-item">` block

**Important:** Keep the `hidden` class on new `faq-answer` divs - JavaScript handles showing/hiding them.

---

### Section 1.9: Footer Section

**Location:** Lines 525-600

The footer contains company info, links, and contact details.

#### Company Info:
```html
<div>
    <div class="flex items-center gap-3 mb-4">
        <div class="w-10 h-10 rounded-full" style="background-color: var(--primary);"></div>
        <span class="font-bold text-lg">The Shift</span>
    </div>
    <p class="text-gray-400 text-sm leading-relaxed mb-4">
        Oakland's premier chiropractic clinic dedicated to holistic wellness and personalized care.
    </p>
</div>
```

**To update:**

1. **Change company name:**
```html
<span class="font-bold text-lg">Your Company Name</span>
```

2. **Change company description:**
```html
<p class="text-gray-400 text-sm leading-relaxed mb-4">
    Your company description. Keep it brief and compelling.
</p>
```

#### Footer Contact Information:

**Location:** Lines 577-590

```html
<li class="flex items-center gap-2">
    <i class="fas fa-envelope text-[#FF5A5F]"></i>
    <a href="mailto:Theshiftchiropractic@gmail.com" class="text-gray-400 hover:text-white transition-colors duration-300">
        Theshiftchiropractic@gmail.com
    </a>
</li>
<li class="flex items-center gap-2">
    <i class="fas fa-phone text-[#FF5A5F]"></i>
    <span class="text-gray-400">(510) 555-0123</span>
</li>
<li class="flex items-center gap-2">
    <i class="fas fa-map-marker-alt text-[#FF5A5F]"></i>
    <span class="text-gray-400">Oakland, CA</span>
</li>
```

**To update email:**
```html
<a href="mailto:your-email@example.com" class="text-gray-400 hover:text-white transition-colors duration-300">
    your-email@example.com
</a>
```

**To update phone:**
```html
<span class="text-gray-400">(555) 123-4567</span>
```

**To update location:**
```html
<span class="text-gray-400">Your City, State</span>
```

#### Footer Copyright:

**Location:** Lines 603-604

```html
<p class="text-gray-400 text-sm">
    &copy; 2025 The Shift Chiropractic. All rights reserved.
</p>
```

**To update:**
```html
<p class="text-gray-400 text-sm">
    &copy; 2025 Your Company Name. All rights reserved.
</p>
```

---

## Part 2: Fixing Broken Links

This section helps you identify and fix all links on your landing page.

### Section 2.1: Understanding Links

A link in HTML looks like this:
```html
<a href="destination-url">Link Text</a>
```

**Components:**
- `<a>` - The link tag
- `href` - The destination (where the link goes)
- `Link Text` - What visitors see and click on

### Section 2.2: Types of Links on This Page

#### Type 1: Internal Links (Anchor Links)
These jump to sections on the same page.

**Format:** `href="#section-id"`

**Examples on your page:**
```html
<a href="#features">Features</a>
<a href="#benefits">Benefits</a>
<a href="#about">About</a>
<a href="#testimonials">Testimonials</a>
<a href="#faq">FAQ</a>
```

**How they work:**
1. The `href="#features"` tells the browser to find an element with `id="features"`
2. The page scrolls to that element
3. This happens because of the CSS: `scroll-behavior: smooth;`

**To verify these work:**
1. Check that the corresponding section has the matching `id` attribute
2. For example, the Features section should have: `<section id="features" ...>`

**Current matching IDs on your page:**
- `id="features"` - Line 156
- `id="benefits"` - Line 214
- `id="about"` - Line 314
- `id="testimonials"` - Line 364
- `id="faq"` - Line 454

✅ **All anchor links are correctly set up!**

---

#### Type 2: External Links (Booking System)
These go to external websites.

**Location:** Multiple places in the HTML

**Current booking link:**
```html
href="https://app.acuityscheduling.com/schedule.php?owner=13033735"
```

**This link appears in:**
1. Desktop navigation (Line 60)
2. Mobile navigation (Line 68)
3. Hero section primary button (Line 122)
4. Hero section secondary button (Line 127)
5. CTA section button (Line 447)

**To verify this link works:**
1. Copy the URL into your browser
2. Check if it loads the booking page
3. If it doesn't work, contact Acuity Scheduling support

**To update the booking link:**

If you switch to a different booking system (like Calendly, Setmore, etc.):

1. Get your new booking URL from your booking platform
2. Find and replace all instances of the old URL

**Using Find & Replace (easiest method):**
1. In your code editor, press `Ctrl+H` (or `Cmd+H` on Mac)
2. In "Find" field, paste: `https://app.acuityscheduling.com/schedule.php?owner=13033735`
3. In "Replace" field, paste your new booking URL
4. Click "Replace All"

---

#### Type 3: Footer Links (Currently Broken)

**Location:** Lines 592-594

```html
<a href="privacy.html" class="text-gray-400 hover:text-white text-sm transition-colors duration-300">Privacy Policy</a>
<a href="terms.html" class="text-gray-400 hover:text-white text-sm transition-colors duration-300">Terms of Service</a>
<a href="blog.html" class="text-gray-400 hover:text-white text-sm transition-colors duration-300">Blog</a>
```

**Status:** ⚠️ **BROKEN** - These files don't exist yet

These links point to:
- `privacy.html` - Doesn't exist
- `terms.html` - Doesn't exist
- `blog.html` - Doesn't exist

**What happens when visitors click these:**
- They see a 404 error (page not found)
- This looks unprofessional

**Solutions:**

**Option A: Remove broken links** (Quick fix)
Delete these lines entirely if you don't need them yet.

**Option B: Create the pages** (Proper fix)
See Part 3 for detailed instructions.

---

#### Type 4: Social Media Links

**Location:** Lines 557-565

```html
<a href="#" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Facebook">
    <i class="fab fa-facebook-f text-gray-400"></i>
</a>
<a href="#" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Instagram">
    <i class="fab fa-instagram text-gray-400"></i>
</a>
<a href="#" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-gray-400"></i>
</a>
```

**Status:** ⚠️ **BROKEN** - All social links point to `#` (nowhere)

**To fix social media links:**

1. **Find your social media URLs**
   - Facebook: `https://www.facebook.com/your-page-name`
   - Instagram: `https://www.instagram.com/your-username/`
   - Twitter: `https://twitter.com/your-handle`

2. **Replace the `href="#"` with your actual URLs**

**Example - Facebook:**
```html
<!-- Before (broken) -->
<a href="#" class="..." aria-label="Facebook">

<!-- After (fixed) -->
<a href="https://www.facebook.com/your-clinic-name" class="..." aria-label="Facebook">
```

**Complete fixed example:**
```html
<a href="https://www.facebook.com/theshiftchiropractic" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Facebook">
    <i class="fab fa-facebook-f text-gray-400"></i>
</a>
<a href="https://www.instagram.com/theshiftchiropractic/" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Instagram">
    <i class="fab fa-instagram text-gray-400"></i>
</a>
<a href="https://twitter.com/theshiftchiro" class="w-10 h-10 rounded-full flex items-center justify-center hover:bg-gray-800 transition-colors duration-300" aria-label="Twitter">
    <i class="fab fa-twitter text-gray-400"></i>
</a>
```

**Pro Tip:** Make sure to open the link in a new tab by adding `target="_blank"`:
```html
<a href="https://www.facebook.com/your-page" target="_blank" class="...">
```

---

#### Type 5: Email Link

**Location:** Line 582

```html
<a href="mailto:Theshiftchiropractic@gmail.com" class="text-gray-400 hover:text-white transition-colors duration-300">
    Theshiftchiropractic@gmail.com
</a>
```

**To update with your email:**

```html
<a href="mailto:your-email@example.com" class="text-gray-400 hover:text-white transition-colors duration-300">
    your-email@example.com
</a>
```

**Note:** Change both the `href` AND the displayed text to match.

---

### Section 2.3: Link Testing Checklist

After updating links, test each one:

| Link Type | Location | Status | Action |
|-----------|----------|--------|--------|
| Features anchor | Navigation menu | ✅ Works | No action needed |
| Benefits anchor | Navigation menu | ✅ Works | No action needed |
| About anchor | Navigation menu | ✅ Works | No action needed |
| Testimonials anchor | Navigation menu | ✅ Works | No action needed |
| FAQ anchor | Navigation menu | ✅ Works | No action needed |
| Book Now (desktop) | Navigation | ⚠️ Check | Verify booking URL works |
| Book Now (mobile) | Mobile menu | ⚠️ Check | Verify booking URL works |
| Schedule button (hero) | Hero section | ⚠️ Check | Verify booking URL works |
| Call Us button | Hero section | ❌ Broken | Needs implementation |
| Book Now (CTA) | CTA section | ⚠️ Check | Verify booking URL works |
| Privacy Policy | Footer | ❌ Broken | Create privacy.html |
| Terms of Service | Footer | ❌ Broken | Create terms.html |
| Blog | Footer | ❌ Broken | Create blog.html or remove |
| Facebook | Footer | ❌ Broken | Add your Facebook URL |
| Instagram | Footer | ❌ Broken | Add your Instagram URL |
| Twitter | Footer | ❌ Broken | Add your Twitter URL |
| Email | Footer | ⚠️ Check | Update to your email |

---

### Section 2.4: The "Call Us" Button Issue

**Location:** Line 127

```html
<button class="px-8 py-3 rounded-full border-2 border-white text-white font-semibold 
            hover:bg-white hover:text-gray-900 transition-all duration-300 
            flex items-center justify-center gap-2">
    <i class="fas fa-phone"></i>
    Call Us
</button>
```

**Current Status:** ❌ This button doesn't do anything when clicked

**To make it functional:**

**Option 1: Make it a phone link (Recommended)**
```html
<a href="tel:(510)555-0123" class="px-8 py-3 rounded-full border-2 border-white text-white font-semibold 
            hover:bg-white hover:text-gray-900 transition-all duration-300 
            flex items-center justify-center gap-2">
    <i class="fas fa-phone"></i>
    Call Us
</a>
```

Replace `(510)555-0123` with your actual phone number (no spaces or dashes in the `href`).

**Option 2: Make it a WhatsApp link**
```html
<a href="https://wa.me/15105550123" target="_blank" class="px-8 py-3 rounded-full border-2 border-white text-white font-semibold 
            hover:bg-white hover:text-gray-900 transition-all duration-300 
            flex items-center justify-center gap-2">
    <i class="fas fa-phone"></i>
    Call Us
</a>
```

Replace `15105550123` with your WhatsApp number (country code + number, no special characters).

---

## Part 3: Linking Privacy and Terms Pages

This section shows you how to create and link your Privacy Policy and Terms of Service pages.

### Section 3.1: Why You Need These Pages

- **Legal Requirement:** Most jurisdictions require privacy policies
- **Trust:** Shows visitors you take their data seriously
- **Professional:** Looks more established and credible
- **SEO:** Helps with search engine rankings

---

### Section 3.2: Step-by-Step: Create Privacy.html

#### Step 1: Create a new file

1. In your code editor, create a new file
2. Save it as `privacy.html` in the same folder as `index.html`

#### Step 2: Add the basic structure

Copy this template and paste it into your new `privacy.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Privacy Policy - The Shift Chiropractic">
    <title>Privacy Policy - The Shift Chiropractic</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Inter', sans-serif;
        }
        
        :root {
            --primary: #FF5A5F;
        }
        
        header {
            position: sticky;
            top: 0;
            z-index: 50;
            background-color: rgba(26, 26, 26, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header -->
    <header class="w-full">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-full" style="background-color: var(--primary);"></div>
                <span class="font-bold text-xl hidden sm:block">The Shift</span>
            </div>
            <a href="index.html" class="text-gray-300 hover:text-white transition-colors duration-300">← Back to Home</a>
        </nav>
    </header>

    <!-- Content -->
    <main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <h1 class="text-4xl font-bold mb-8">Privacy Policy</h1>
        
        <div class="space-y-8 text-gray-300 leading-relaxed">
            <section>
                <h2 class="text-2xl font-bold text-white mb-4">1. Introduction</h2>
                <p>
                    The Shift Chiropractic ("we," "us," "our," or "Company") is committed to protecting your privacy. 
                    This Privacy Policy explains how we collect, use, disclose, and safeguard your information when you 
                    visit our website and use our services.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">2. Information We Collect</h2>
                <p>We may collect information about you in a variety of ways. The information we may collect on the 
                Site includes:</p>
                <ul class="list-disc list-inside space-y-2 mt-4">
                    <li><strong>Personal Data:</strong> Name, email address, phone number, and appointment information</li>
                    <li><strong>Device Data:</strong> Browser type, IP address, and pages visited</li>
                    <li><strong>Usage Data:</strong> How you interact with our website</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">3. Use of Your Information</h2>
                <p>Having accurate information about you permits us to provide you with a smooth, efficient, and 
                customized experience. Specifically, we may use information collected about you via the Site to:</p>
                <ul class="list-disc list-inside space-y-2 mt-4">
                    <li>Process your appointment bookings</li>
                    <li>Send periodic emails regarding your appointment or other related information</li>
                    <li>Follow up with you after your visit</li>
                    <li>Improve our website and services</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">4. Disclosure of Your Information</h2>
                <p>We may share information we have collected about you in certain situations:</p>
                <ul class="list-disc list-inside space-y-2 mt-4">
                    <li><strong>By Law or to Protect Rights:</strong> If required by law or if we believe in good faith 
                    that disclosure is necessary to protect our rights</li>
                    <li><strong>Third-Party Service Providers:</strong> We may share your information with vendors, 
                    consultants, and other service providers who need access to such information to carry out work on our behalf</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">5. Security of Your Information</h2>
                <p>
                    We use administrative, technical, and physical security measures to protect your personal information. 
                    However, no method of transmission over the Internet or method of electronic storage is 100% secure.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">6. Contact Us</h2>
                <p>
                    If you have questions or comments about this Privacy Policy, please contact us at:
                </p>
                <div class="mt-4 p-4 bg-gray-800 rounded-lg">
                    <p><strong>Email:</strong> Theshiftchiropractic@gmail.com</p>
                    <p><strong>Phone:</strong> (510) 555-0123</p>
                    <p><strong>Location:</strong> Oakland, CA</p>
                </div>
            </section>

            <section class="pt-8 border-t border-gray-700">
                <p class="text-sm text-gray-400">
                    Last updated: January 2025
                </p>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-8 px-4 sm:px-6 lg:px-8 mt-16">
        <div class="max-w-7xl mx-auto text-center text-gray-400 text-sm">
            <p>&copy; 2025 The Shift Chiropractic. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
```

#### Step 3: Customize the privacy policy

Update these sections with your actual information:

1. **Company name** - Replace "The Shift Chiropractic" with your company name
2. **Contact information** - Update email, phone, and location
3. **Data practices** - Customize based on your actual data collection practices
4. **Last updated date** - Change to current date

---

### Section 3.3: Step-by-Step: Create Terms.html

#### Step 1: Create a new file

1. In your code editor, create a new file
2. Save it as `terms.html` in the same folder as `index.html`

#### Step 2: Add the basic structure

Copy this template and paste it into your new `terms.html` file:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Terms of Service - The Shift Chiropractic">
    <title>Terms of Service - The Shift Chiropractic</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            font-family: 'Inter', sans-serif;
        }
        
        :root {
            --primary: #FF5A5F;
        }
        
        header {
            position: sticky;
            top: 0;
            z-index: 50;
            background-color: rgba(26, 26, 26, 0.95);
            backdrop-filter: blur(10px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
        }
    </style>
</head>
<body class="bg-gray-900 text-white">
    <!-- Header -->
    <header class="w-full">
        <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex items-center justify-between">
            <div class="flex items-center gap-3">
                <div class="w-10 h-10 rounded-full" style="background-color: var(--primary);"></div>
                <span class="font-bold text-xl hidden sm:block">The Shift</span>
            </div>
            <a href="index.html" class="text-gray-300 hover:text-white transition-colors duration-300">← Back to Home</a>
        </nav>
    </header>

    <!-- Content -->
    <main class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
        <h1 class="text-4xl font-bold mb-8">Terms of Service</h1>
        
        <div class="space-y-8 text-gray-300 leading-relaxed">
            <section>
                <h2 class="text-2xl font-bold text-white mb-4">1. Agreement to Terms</h2>
                <p>
                    By accessing and using this website and booking services with The Shift Chiropractic, you accept 
                    and agree to be bound by and abide by the terms and provision of this agreement.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">2. Use License</h2>
                <p>
                    Permission is granted to temporarily download one copy of the materials (information or software) 
                    on The Shift Chiropractic's website for personal, non-commercial transitory viewing only. This is 
                    the grant of a license, not a transfer of title, and under this license you may not:
                </p>
                <ul class="list-disc list-inside space-y-2 mt-4">
                    <li>Modify or copy the materials</li>
                    <li>Use the materials for any commercial purpose or for any public display</li>
                    <li>Attempt to reverse engineer any software contained on the website</li>
                    <li>Remove any copyright or other proprietary notations from the materials</li>
                    <li>Transfer the materials to another person or "mirror" the materials on any other server</li>
                </ul>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">3. Disclaimer</h2>
                <p>
                    The materials on The Shift Chiropractic's website are provided on an 'as is' basis. The Shift 
                    Chiropractic makes no warranties, expressed or implied, and hereby disclaims and negates all other 
                    warranties including, without limitation, implied warranties or conditions of merchantability, fitness 
                    for a particular purpose, or non-infringement of intellectual property or other violation of rights.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">4. Limitations</h2>
                <p>
                    In no event shall The Shift Chiropractic or its suppliers be liable for any damages (including, 
                    without limitation, damages for loss of data or profit, or due to business interruption) arising 
                    out of the use or inability to use the materials on the website.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">5. Appointment Cancellation Policy</h2>
                <p>
                    Appointments must be cancelled or rescheduled at least 24 hours in advance. Cancellations made 
                    less than 24 hours before the scheduled appointment may be subject to a cancellation fee.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">6. Medical Disclaimer</h2>
                <p>
                    The information provided on this website is not intended to diagnose, treat, cure, or prevent any disease. 
                    Always consult with a qualified healthcare professional before beginning any treatment. Chiropractic care 
                    is not a substitute for medical advice.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">7. Modifications to Terms</h2>
                <p>
                    The Shift Chiropractic may revise these terms of service for its website at any time without notice. 
                    By using this website, you are agreeing to be bound by the then current version of these terms of service.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">8. Governing Law</h2>
                <p>
                    These terms and conditions are governed by and construed in accordance with the laws of California, 
                    and you irrevocably submit to the exclusive jurisdiction of the courts in that location.
                </p>
            </section>

            <section>
                <h2 class="text-2xl font-bold text-white mb-4">9. Contact Information</h2>
                <p>
                    If you have any questions about these Terms of Service, please contact us at:
                </p>
                <div class="mt-4 p-4 bg-gray-800 rounded-lg">
                    <p><strong>Email:</strong> Theshiftchiropractic@gmail.com</p>
                    <p><strong>Phone:</strong> (510) 555-0123</p>
                    <p><strong>Location:</strong> Oakland, CA</p>
                </div>
            </section>

            <section class="pt-8 border-t border-gray-700">
                <p class="text-sm text-gray-400">
                    Last updated: January 2025
                </p>
            </section>
        </div>
    </main>

    <!-- Footer -->
    <footer class="bg-gray-950 border-t border-gray-800 py-8 px-4 sm:px-6 lg:px-8 mt-16">
        <div class="max-w-7xl mx-auto text-center text-gray-400 text-sm">
            <p>&copy; 2025 The Shift Chiropractic. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
```

#### Step 3: Customize the terms page

Update these sections with your actual information:

1. **Company name** - Replace "The Shift Chiropractic" with your company name
2. **Cancellation policy** - Update the 24-hour policy if different
3. **Jurisdiction** - Change "California" to your state
4. **Contact information** - Update email, phone, and location
5. **Last updated date** - Change to current date

---

### Section 3.4: Verify Links Work

After creating both files, verify the links work:

#### Step 1: Test from index.html

1. Open `index.html` in your browser
2. Scroll to the footer
3. Click "Privacy Policy" - should load `privacy.html`
4. Click "Terms of Service" - should load `terms.html`
5. Click "← Back to Home" on either policy page - should return to `index.html`

#### Step 2: Check file structure

Your folder should now contain:
```
your-project-folder/
├── index.html          ✅
├── privacy.html        ✅
├── terms.html          ✅
└── blog.html           (optional)
```

---

### Section 3.5: Optional - Create Blog.html

The footer currently links to `blog.html`. You can either:

**Option A: Remove the blog link** (if you don't need a blog)

In `index.html`, find line 594:
```html
<a href="blog.html" class="text-gray-400 hover:text-white text-sm transition-colors duration-300">Blog</a>
```

Delete this line.

**Option B: Create a blog page** (if you want a blog)

Create a new file called `blog.html` with similar structure to `privacy.html` and `terms.html`, then add blog content.

---

## Understanding the Design System

This section explains how the design works so you can make consistent customizations.

### Section 4.1: Color System

The page uses a simple three-color system defined in the `<style>` section:

```css
:root {
    --primary: #FF5A5F;      /* Red/Pink */
    --secondary: #1A1A1A;    /* Dark Gray/Black */
    --accent: #FFD166;       /* Yellow/Gold */
}
```

**Where colors are used:**

1. **Primary Color (#FF5A5F - Red/Pink)**
   - Call-to-action buttons
   - Icons
   - Accent lines
   - Hover effects

2. **Secondary Color (#1A1A1A - Dark)**
   - Background
   - Text
   - Not visible (used as base)

3. **Accent Color (#FFD166 - Yellow)**
   - Secondary highlights
   - Alternative buttons
   - Star ratings

### Section 4.2: Changing Colors

**To change the primary color (red):**

Find this line in the `<style>` section (around line 26):
```css
--primary: #FF5A5F;
```

Replace with your color:
```css
--primary: #3498db;  /* Example: Blue */
```

**To change the accent color (yellow):**

Find this line (around line 28):
```css
--accent: #FFD166;
```

Replace with your color:
```css
--accent: #2ecc71;  /* Example: Green */
```

**Finding hex color codes:**
- Use Google: "color picker"
- Visit: https://htmlcolorcodes.com
- Use Figma, Adobe Color, or similar tools

### Section 4.3: Responsive Design

This page uses **Tailwind CSS** for responsive design. Tailwind uses breakpoints:

- `sm:` - Small screens (640px+)
- `md:` - Medium screens (768px+)
- `lg:` - Large screens (1024px+)
- `xl:` - Extra large (1280px+)

**Example from the code:**
```html
<div class="hidden md:flex items-center gap-8">
    <!-- This is hidden on mobile, but shows as flex on medium+ screens -->
</div>
```

**What this means:**
- On mobile: Element is hidden
- On tablet and up: Element displays as flexbox

### Section 4.4: Spacing System

Tailwind uses a consistent spacing scale:

- `p-4` - Padding of 1rem (16px)
- `m-6` - Margin of 1.5rem (24px)
- `gap-8` - Gap between items of 2rem (32px)
- `py-16` - Padding top & bottom of 4rem (64px)

**Common spacing values:**
- `p-2` = 8px
- `p-4` = 16px
- `p-6` = 24px
- `p-8` = 32px
- `p-16` = 64px

---

## Tailwind CSS Classes Guide

This section explains the most important Tailwind classes used in your landing page.

### Section 5.1: Text Classes

| Class | Effect |
|-------|--------|
| `text-white` | White text |
| `text-gray-300` | Light gray text |
| `text-gray-400` | Medium gray text |
| `text-gray-900` | Very dark gray text |
| `font-bold` | Bold text |
| `font-semibold` | Semi-bold text |
| `text-sm` | Small text (14px) |
| `text-lg` | Large text (18px) |
| `text-xl` | Extra large text (20px) |
| `text-2xl` | 2x large text (24px) |
| `text-3xl` | 3x large text (30px) |
| `text-4xl` | 4x large text (36px) |

**Example:**
```html
<p class="text-white font-bold text-lg">
    This is bold, large, white text
</p>
```

### Section 5.2: Background Classes

| Class | Effect |
|-------|--------|
| `bg-gray-900` | Dark gray background |
| `bg-gray-800` | Lighter gray background |
| `bg-white` | White background |
| `bg-opacity-50` | 50% opacity |

**Example:**
```html
<div class="bg-gray-900 text-white">
    Dark background with white text
</div>
```

### Section 5.3: Spacing Classes

| Class | Effect |
|-------|--------|
| `p-4` | Padding all sides: 16px |
| `px-4` | Padding left & right: 16px |
| `py-4` | Padding top & bottom: 16px |
| `m-4` | Margin all sides: 16px |
| `gap-4` | Space between items: 16px |
| `mb-6` | Margin bottom: 24px |
| `mt-8` | Margin top: 32px |

**Example:**
```html
<div class="px-4 py-8 gap-6">
    Padding left/right 16px, top/bottom 32px, gap 24px
</div>
```

### Section 5.4: Layout Classes

| Class | Effect |
|-------|--------|
| `flex` | Display as flexbox |
| `grid` | Display as grid |
| `items-center` | Center items vertically |
| `justify-center` | Center items horizontally |
| `gap-4` | Space between flex/grid items |
| `grid-cols-1` | 1 column on mobile |
| `md:grid-cols-2` | 2 columns on medium+ screens |
| `lg:grid-cols-3` | 3 columns on large+ screens |

**Example:**
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
    <!-- 1 column on mobile, 2 on tablet, 3 on desktop -->
</div>
```

### Section 5.5: Border & Rounded Classes

| Class | Effect |
|-------|--------|
| `border` | Add border |
| `border-2` | Thicker border |
| `border-gray-800` | Gray border |
| `rounded-lg` | Slightly rounded corners |
| `rounded-full` | Fully rounded (circle) |
| `rounded-3xl` | Very rounded corners |

**Example:**
```html
<div class="border-2 border-white rounded-lg p-4">
    Box with white border and rounded corners
</div>
```

### Section 5.6: Hover & Transition Classes

| Class | Effect |
|-------|--------|
| `hover:text-white` | Change to white on hover |
| `hover:bg-gray-800` | Change background on hover |
| `transition-colors` | Smooth color transition |
| `duration-300` | Transition takes 300ms |
| `cursor-pointer` | Show pointer cursor |

**Example:**
```html
<a href="#" class="text-gray-300 hover:text-white transition-colors duration-300">
    Link that smoothly changes color on hover
</a>
```

### Section 5.7: Visibility Classes

| Class | Effect |
|-------|--------|
| `hidden` | Hide element |
| `block` | Show as block |
| `flex` | Show as flexbox |
| `md:hidden` | Hide on medium+ screens |
| `md:block` | Show on medium+ screens |
| `hidden md:flex` | Hide on mobile, show on medium+ |

**Example:**
```html
<div class="hidden md:flex">
    This only shows on tablet and larger screens
</div>
```

---

## Common Customizations

This section covers frequently needed customizations.

### Section 6.1: Change the Booking Link

**Current booking system:** Acuity Scheduling

**To switch to a different system:**

1. Get your new booking URL
2. Use Find & Replace to update all instances:
   - Press `Ctrl+H` (or `Cmd+H`)
   - Find: `https://app.acuityscheduling.com/schedule.php?owner=13033735`
   - Replace: Your new booking URL
   - Click "Replace All"

**Common booking systems:**
- **Calendly:** `https://calendly.com/your-username`
- **Setmore:** `https://setmore.com/your-business`
- **Mindbody:** `https://clients.mindbodyonline.com/`

---

### Section 6.2: Add a New Section

**To add a new section between existing sections:**

1. Choose where to insert it (e.g., after Benefits, before About)
2. Copy an existing section as a template
3. Update the content
4. Add an `id` if you want it in the navigation menu

**Example - New "Services" section:**

```html
<!-- Add this after the Benefits section -->
<section id="services" class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-gray-800">
    <div class="max-w-7xl mx-auto">
        <div class="text-center mb-16">
            <div class="accent-line mx-auto"></div>
            <h2 class="section-heading mb-4">Our Services</h2>
            <p class="section-subheading max-w-3xl mx-auto">
                We offer a comprehensive range of chiropractic services tailored to your needs.
            </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Add your service cards here -->
        </div>
    </div>
</section>
```

Then add it to the navigation menu:
```html
<a href="#services" class="text-gray-300 hover:text-white transition-colors duration-300">Services</a>
```

---

### Section 6.3: Change Button Colors

**Primary buttons (red):**

Find any button with `class="primary-btn"` and it will use the primary color automatically.

**To change button color:**

Modify the `--primary` variable in the style section (see Section 4.2).

**To create an alternative button color:**

Add a new CSS class in the `<style>` section:

```css
.secondary-btn {
    background-color: var(--accent);
    color: #1A1A1A;
    border-radius: 9999px;
    padding: 12px 32px;
    font-weight: 600;
    transition: all 300ms ease-out;
    cursor: pointer;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
}

.secondary-btn:hover {
    transform: scale(1.05);
    box-shadow: 0 10px 40px rgba(255, 209, 102, 0.3);
    filter: brightness(1.1);
}
```

Then use it:
```html
<a href="#" class="secondary-btn">Click Me</a>
```

---

### Section 6.4: Add a Video Background

**To add a video to the hero section:**

Find the hero section (around line 96) and replace the image placeholder with:

```html
<div class="hidden lg:flex items-center justify-center relative">
    <video autoplay muted loop class="w-full h-96 rounded-3xl object-cover">
        <source src="your-video.mp4" type="video/mp4">
        Your browser doesn't support HTML5 video.
    </video>
</div>
```

Replace `your-video.mp4` with your video file path.

---

### Section 6.5: Modify the Color Scheme

**Example: Change from Red/Yellow to Blue/Purple**

Find the color definitions in the `<style>` section:

```css
:root {
    --primary: #3498db;      /* Blue */
    --secondary: #1A1A1A;    /* Keep dark */
    --accent: #9b59b6;       /* Purple */
}
```

This will automatically update all elements using these colors throughout the page.

---

### Section 6.6: Add a Newsletter Signup

**To add an email signup form:**

Add this before the footer:

```html
<!-- Newsletter Section -->
<section class="py-16 md:py-24 px-4 sm:px-6 lg:px-8 bg-gray-800">
    <div class="max-w-2xl mx-auto text-center">
        <h2 class="text-3xl font-bold mb-4">Subscribe to Our Newsletter</h2>
        <p class="text-gray-400 mb-8">Get wellness tips and updates delivered to your inbox.</p>
        
        <form class="flex gap-4">
            <input type="email" placeholder="Enter your email" 
                   class="flex-1 px-4 py-3 rounded-full bg-gray-700 text-white placeholder-gray-500 focus:outline-none focus:ring-2 focus:ring-[#FF5A5F]">
            <button type="submit" class="primary-btn">Subscribe</button>
        </form>
    </div>
</section>
```

**To make it functional, you'll need:**
1. A backend service (like Mailchimp, ConvertKit)
2. Or a form service (like Formspree)

---

## Troubleshooting

This section helps you fix common issues.

### Section 7.1: Links Not Working

**Problem:** A link doesn't work when clicked

**Solutions:**

1. **Check the URL is correct**
   - Copy the URL from the `href` attribute
   - Paste it in your browser address bar
   - Does it work there?

2. **Check file paths for local links**
   - `privacy.html` should be in the same folder as `index.html`
   - Use relative paths: `href="privacy.html"` (not `href="/privacy.html"`)

3. **Check anchor links have matching IDs**
   - Link: `href="#features"`
   - Section: `id="features"`
   - They must match exactly (case-sensitive)

4. **External links need full URLs**
   - ❌ Wrong: `href="facebook.com/page"`
   - ✅ Right: `href="https://www.facebook.com/page"`

---

### Section 7.2: Text Not Showing

**Problem:** Text I added doesn't appear on the page

**Solutions:**

1. **Save the file**
   - Press `Ctrl+S` (or `Cmd+S`)
   - Check the file tab shows no unsaved indicator

2. **Refresh the browser**
   - Press `F5` or `Ctrl+R`
   - Or hard refresh: `Ctrl+Shift+R`

3. **Check for typos in HTML tags**
   - ❌ Wrong: `<p>Text</div>` (mismatched tags)
   - ✅ Right: `<p>Text</p>` (matching tags)

4. **Check text isn't white on white background**
   - Look for `text-white` on `bg-white` sections
   - Change text color: `class="text-gray-900"`

---

### Section 7.3: Styling Not Applying

**Problem:** Tailwind classes aren't working

**Solutions:**

1. **Check class names are spelled correctly**
   - ❌ Wrong: `text-whte` (typo)
   - ✅ Right: `text-white`

2. **Check you're using valid Tailwind classes**
   - Not all CSS properties have Tailwind equivalents
   - Use inline styles for unsupported properties: `style="color: red;"`

3. **Check classes are in the right place**
   - Classes go in the `class=""` attribute
   - ❌ Wrong: `<div style="text-white">` (should be class)
   - ✅ Right: `<div class="text-white">`

4. **Check Tailwind CDN is loading**
   - Open browser DevTools (F12)
   - Go to Network tab
   - Refresh page
   - Look for `cdn.tailwindcss.com` - should have status 200

---

### Section 7.4: Mobile Menu Not Working

**Problem:** Mobile menu button doesn't open/close

**Solutions:**

1. **Check JavaScript is enabled**
   - Browser settings > JavaScript
   - Make sure it's enabled

2. **Check browser console for errors**
   - Press F12
   - Go to Console tab
   - Look for red error messages
   - Check if they reference your code

3. **Check mobile menu HTML is present**
   - Look for `<div class="mobile-menu hidden">`
   - It should be in the header section

4. **Test on actual mobile device or use browser DevTools**
   - Press F12
   - Click device icon (top-left of DevTools)
   - Select a mobile device size

---

### Section 7.5: FAQ Accordion Not Working

**Problem:** FAQ items don't expand/collapse when clicked

**Solutions:**

1. **Check FAQ structure is correct**
   - Each FAQ item should have: `<div class="faq-item">`
   - Each should have: `<div class="faq-question">`
   - Each should have: `<div class="faq-answer hidden">`

2. **Check the `hidden` class is present**
   - The answer div should start with `hidden`
   - JavaScript toggles this class to show/hide

3. **Check JavaScript is enabled**
   - Same as mobile menu troubleshooting

4. **Test in browser console**
   - Press F12
   - Go to Console tab
   - Type: `document.querySelectorAll('.faq-item').length`
   - Should return a number (not 0)

---

### Section 7.6: Images Not Loading

**Problem:** Images or icons don't appear

**Solutions:**

1. **Check image file exists**
   - Make sure file is in correct folder
   - Check file name spelling

2. **Check image path is correct**
   - Relative path: `src="images/photo.jpg"`
   - Absolute path: `src="/images/photo.jpg"`
   - Web URL: `src="https://example.com/photo.jpg"`

3. **Check file format is supported**
   - ✅ JPG, PNG, GIF, WebP, SVG
   - ❌ Other formats may not work

4. **For Font Awesome icons**
   - Check CDN link is loading (Network tab in DevTools)
   - Check icon name is correct: `<i class="fas fa-phone"></i>`
   - Visit https://fontawesome.com/icons for icon names

---

### Section 7.7: Page Layout Broken on Mobile

**Problem:** Page looks broken on mobile devices

**Solutions:**

1. **Check viewport meta tag**
   - Should be in `<head>`: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
   - This is already in your code ✅

2. **Check responsive classes**
   - Use `hidden md:block` to hide on mobile
   - Use `block md:hidden` to show only on mobile
   - Test with browser DevTools responsive mode

3. **Check padding/margins**
   - Add `px-4` for horizontal padding on mobile
   - Use `sm:px-6 lg:px-8` for larger screens

4. **Test on real device**
   - Use phone or tablet
   - Or use browser DevTools device emulation

---

### Section 7.8: Colors Look Wrong

**Problem:** Colors don't match what you expected

**Solutions:**

1. **Check hex color codes**
   - Hex format: `#RRGGBB`
   - ❌ Wrong: `#FF5A` (too short)
   - ✅ Right: `#FF5A5F` (6 characters)

2. **Check color values in CSS variables**
   - Find `:root` in `<style>`
   - Check `--primary`, `--secondary`, `--accent` values
   - Are they the colors you want?

3. **Check inline styles override**
   - Inline `style=""` attributes override class styles
   - Make sure you're editing the right place

4. **Clear browser cache**
   - Old CSS might be cached
   - Hard refresh: `Ctrl+Shift+R`

---

### Section 7.9: Performance Issues (Page Slow)

**Problem:** Page loads slowly or feels sluggish

**Solutions:**

1. **Optimize images**
   - Use compressed images
   - Use modern formats (WebP)
   - Reduce image dimensions

2. **Check external resources**
   - CDN links might be slow
   - Use faster CDNs if available

3. **Minimize custom CSS**
   - Keep custom CSS minimal
   - Use Tailwind classes instead

4. **Check browser extensions**
   - Disable browser extensions
   - See if page is faster
   - Some extensions slow down pages

5. **Use browser DevTools Performance tab**
   - F12 > Performance tab
   - Click record, interact with page, stop
   - See what's taking time

---

## Final Checklist

Before launching your landing page, verify:

- [ ] All text has been customized (business name, descriptions, etc.)
- [ ] All links work (test each one)
- [ ] Contact information is correct (email, phone, address)
- [ ] Booking link points to your scheduling system
- [ ] Privacy Policy page is created and linked
- [ ] Terms of Service page is created and linked
- [ ] Social media links are updated
- [ ] Page looks good on mobile (use DevTools)
- [ ] All images load correctly
- [ ] Mobile menu works
- [ ] FAQ accordion works
- [ ] No broken links in footer
- [ ] Color scheme matches your branding
- [ ] All testimonials are relevant
- [ ] Meta description is accurate
- [ ] Page title is correct

---

## Additional Resources

- **Tailwind CSS Documentation:** https://tailwindcss.com/docs
- **HTML Guide:** https://www.w3schools.com/html/
- **CSS Guide:** https://www.w3schools.com/css/
- **Font Awesome Icons:** https://fontawesome.com/icons
- **Color Tools:** https://htmlcolorcodes.com
- **Responsive Design Tester:** https://responsivedesignchecker.com

---

## Support & Questions

If you encounter issues not covered in this guide:

1. **Check browser console** (F12 > Console) for error messages
2. **Validate HTML** at https://validator.w3.org
3. **Test in different browsers** (Chrome, Firefox, Safari, Edge)
4. **Search for solutions** on Stack Overflow or MDN Web Docs

---

**Last Updated:** January 2025  
**Document Version:** 1.0

This comprehensive guide should help you maintain and customize your landing page effectively. Remember to always make backups before making significant changes, and test thoroughly before deploying to production!