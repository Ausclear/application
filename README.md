# AusClear Application Forms - README

## Overview

This repository contains three application forms for AusClear security clearance services:

1. **Individual Client Application Form** - For individual applicants seeking security clearance
2. **Corporate Client Application Form** - For corporate entities sponsoring security clearances
3. **Nominate Employees Form** - For existing corporate clients to nominate additional employees for security clearances

All forms are designed to streamline the application process and integrate seamlessly with Zoho CRM.

---

## 📋 Individual Client Application Form

### Purpose
Allows individual applicants to apply for Australian Government security clearances (Baseline, NV1, NV2) through AusClear's sponsorship services.

### Features
- **6-page multi-step form** with progress tracking
- **Real-time email validation** via API
- **ABN verification** for sole traders and contractors
- **Google Places address autocomplete** for accurate address entry
- **Date picker** with Australian date format (DD/MM/YYYY)
- **Mobile number validation** (10-digit Australian format)
- **Responsive design** for desktop, tablet, and mobile devices
- **Auto-generated reference number** for tracking
- **Terms and conditions** with declaration signature

### Form Sections

#### Page 1: Personal Information
- Title, legal first name, legal last name
- Preferred name and job title
- Client type selection (Individual, Referral Partner, Referred by Friend)

#### Page 2: Clearance Requirements
- Clearance request type (New, Upgrade, Transfer)
- Clearance level required (Baseline, NV1, NV2)
- Australian citizenship confirmation
- Date of birth and country of birth

#### Page 3: Contact Details
- Email address with real-time validation
- Mobile number (10-digit Australian format)
- Full address with Google Places autocomplete
- Suburb, state, postal code, and country

#### Page 4: Business & Payment
- ABN status and verification (if applicable)
- Payment preference (Upfront or 4 monthly instalments)
- Marketing source tracking
- Industry background selection

#### Page 5: Security Clearance History
- Previous clearance status
- Historical clearance level (if applicable)
- CSID number and sponsoring organisation

#### Page 6: Terms & Conditions
- Full terms and conditions display
- Declaration checkbox with applicant name auto-population
- Final submission

### Technical Requirements
- Modern web browser (Chrome, Firefox, Safari, Edge)
- JavaScript enabled for form navigation and date picker
- Internet connection for Zoho form submission and CDN resources

### API Endpoints Used
**None** - Form submits directly to Zoho Forms. All validation is client-side.

### Form Submission
Forms submit to Zoho CRM via the configured endpoint. Upon successful submission:
- Reference number is generated and displayed
- Confirmation message shown
- Option to return to AusClear website

**Note**: Form uses `mode: 'no-cors'` for Zoho submission, so success is assumed after POST.

---

## 🏢 Corporate Client Application Form

### Purpose
Allows corporate entities to register as sponsors for employee security clearances and manage bulk clearance applications.

### Features
*(To be documented - similar structure to Individual form with corporate-specific fields)*

### Form Sections
*(To be completed based on corporate form requirements)*

---

## 👥 Nominate Employees Form

### Purpose
Allows existing corporate clients to quickly nominate additional employees for security clearances without completing the full corporate application process.

### Features
- **Simplified single-page form** for quick employee nominations
- **Minimal required fields** for fast processing
- **Mobile-responsive design**
- **Auto-generated reference number** for tracking
- **Direct Zoho CRM integration**

### Form Fields

#### Employee Information
- **Name** (First and Last)
- **Email address**
- **Mobile number** (10-digit Australian format)

#### Clearance Details
- **Clearance type required** (Baseline, NV1, NV2)
- **Request type** (New, Upgrade, Transfer)

### Use Case
Perfect for corporate clients who:
- Already have an account with AusClear
- Need to nominate multiple employees quickly
- Want to streamline the nomination process
- Have completed initial corporate onboarding

### Deployment URL
`https://application.ausclear.au/nominate.html`

---

## 🎨 Design & Branding

### Colour Scheme
- **Primary Blue**: `#003366` - Header and primary buttons
- **Secondary Blue**: `#004080` - Hover states
- **Success Green**: `#4CAF50` - Verification indicators
- **Warning Yellow**: `#ffc107` - Notice boxes
- **Error Red**: `#e74c3c` - Validation errors
- **Background**: Subtle gradient from `#f8fbff` to `#ffffff`

### Typography
- **Font Family**: `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
- **Headings**: Bold, 24-28px
- **Body Text**: Regular, 16px
- **Help Text**: 14px

### Layout
- **Max Width**: 800px (centered)
- **Responsive Breakpoint**: 600px
- **Padding**: 30px (desktop), 20px (mobile)

---

## 🔧 Configuration

### Zoho Form Integration

**Individual Form**: Already configured with Zoho CRM integration:
```html
<form action="https://forms.zohopublic.com.au/AusClear/form/AusClearClientLeadForm/formperma/qn7JcSrpxW50HttROlH7UtL8LgPaV1JOPBHLVtHxdcA/htmlRecords/submit" method="POST">
```

**Corporate Form**: Zoho form action to be configured upon Zoho form creation.

**Nominate Employees Form**: Zoho form action to be configured upon Zoho form creation.

### External Libraries
- **Flatpickr**: Date picker component (loaded via CDN)
- **Font Awesome**: Icons for UI elements (loaded via CDN)

### Form Submission
Forms submit directly to Zoho using standard HTML form POST. No backend API required for submission.

---

## 📱 Browser Support

| Browser | Minimum Version |
|---------|----------------|
| Chrome  | 90+            |
| Firefox | 88+            |
| Safari  | 14+            |
| Edge    | 90+            |

---

## 🔒 Security & Privacy

### Data Handling
- All form data submitted directly to Zoho via HTTPS
- No data stored in browser localStorage or sessionStorage
- No intermediate server processing
- PII handled in accordance with Australian Privacy Principles
- Zoho CRM handles all data storage and processing

### Validation
- Client-side validation for immediate user feedback
- HTML5 form validation for required fields
- Custom JavaScript validation for specific formats (mobile, date, etc.)
- Final validation handled by Zoho upon submission

---

## 📝 Form Field Reference

### Required Fields (Individual Form)
- Title
- Legal First Name
- Legal Last Name
- Client Type
- Clearance Request Type
- Clearance Required
- Australian Citizen
- Date of Birth
- Country of Birth
- Email
- Mobile Number
- Street Address
- Suburb
- State
- Postal Code
- Country
- ABN Status
- Payment Preference
- Previous Clearance Status
- Terms & Conditions Acceptance

### Optional Fields
- Preferred Name
- Job Title
- ABN Number (if applicable)
- CSID Number
- Sponsoring Organisation
- How did you hear about us?
- Industry Background

---

## 🚀 Deployment

### Steps
1. Update API_BASE constant to `https://application.ausclear.au/api`
2. Verify Zoho form action URL (Individual form already configured)
3. Configure Zoho form action for Corporate form when created
4. Test all API endpoints in production environment
4. Verify email validation service
5. Test ABN verification service
6. Confirm Google Places API integration
7. Test form submission and confirmation flow
8. Verify mobile responsiveness
9. Check cross-browser compatibility
10. Deploy to web server

### File Structure
```
/forms
  ├── individual-application.html
  ├── corporate-application.html
  ├── README.md
  └── /assets (if any images/additional CSS)
```

---

## 🐛 Troubleshooting

### Common Issues

**Form won't submit**
- Check all required fields are completed
- Verify Zoho form action URL is correct
- Check browser console for JavaScript errors
- Ensure internet connection is active

**Date picker not working**
- Verify Flatpickr CDN is loading
- Check browser console for errors
- Try clearing browser cache

**Mobile responsiveness issues**
- Check viewport meta tag is present
- Test on actual devices, not just browser resize
- Verify CSS media queries are working

**Reference number not displaying**
- Check JavaScript is enabled
- Verify `generateReferenceNumber()` function is working
- Check browser console for errors

---

## 📞 Support

For technical support or questions:
- **Website**: https://www.ausclear.com.au
- **Individual Applications**: https://application.ausclear.au/individual.html
- **Corporate Applications**: https://application.ausclear.au/corporate.html
- **Employee Nominations**: https://application.ausclear.au/nominate.html
- **Support Email**: support@ausclear.com.au

---

## 📄 License

Proprietary - © 2025 AusClear. All rights reserved.

---

## 🔄 Version History

### Version 1.0.0 (Current)
- Initial release of Individual Client Application Form
- Multi-step form with 6 pages
- Real-time validation for email and ABN
- Google Places address autocomplete
- Responsive design
- Zoho CRM integration

### Planned Updates
- Corporate Client Application Form
- Nominate Employees Form (simple version)
- Document upload functionality (future consideration)
- Save and resume capability (future consideration)
- Multi-language support (future consideration)
- Enhanced analytics tracking

---

## 👥 Development Team

**Developed for AusClear**
- Design: Professional security clearance form optimised for conversions
- Development: HTML5, CSS3, Vanilla JavaScript
- Integration: Zoho CRM, Google Places API, Custom validation APIs

---

*Last Updated: October 2025*
