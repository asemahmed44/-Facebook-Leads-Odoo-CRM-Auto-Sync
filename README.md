# 📣 Facebook Leads → Odoo CRM Auto-Sync

> Automatically captures leads from Facebook Ad campaigns and creates them instantly as CRM opportunities in Odoo — zero manual entry.

---

## 🎯 Problem Solved

The sales team was manually copying leads from Facebook Ads Manager into Odoo CRM every day — slow, error-prone, and leads were going cold before anyone could follow up.

This automation captures every new lead **the moment** someone submits a Facebook Lead Ad form and creates a full CRM opportunity in Odoo in real time.

---

## ⚡ How It Works

```
Facebook Lead Ad Form Submitted
        ↓
Facebook Lead Ads Trigger (n8n)
        ↓
Map form fields + identify campaign
        ↓
Create Opportunity in Odoo CRM
```

![Workflow Screenshot](workflow.png)

---

## 🔧 Tech Stack

| Tool | Role |
|------|------|
| **n8n** | Workflow automation engine |
| **Facebook Lead Ads API** | Trigger on new lead submission |
| **Odoo CRM** | Destination — creates `crm.lead` record |

---

## 📋 What Gets Created in Odoo

Each new Facebook lead automatically creates a CRM opportunity with:

- ✅ **Full Name** — from the form
- ✅ **Phone Number**
- ✅ **Email**
- ✅ **City**
- ✅ **Opportunity Name** — auto-formatted as `[Name] - [Campaign Name]`
- ✅ **Assigned Salesperson** — pre-configured
- ✅ **Sales Team** — pre-configured
- ✅ **Description** — includes extra form fields (apartment size, location, best time to call, etc.)

---

## 🗂️ Supported Campaigns

The workflow supports **15+ Facebook campaigns** simultaneously, each mapped by Form ID to a campaign name:

| Campaign | Product |
|----------|---------|
| lvx 1-me3margy | General LVX |
| home cinema | Home Cinema System |
| smart kitchen | Smart Kitchen |
| lvx meeting room | Meeting Room Automation |
| security cam | Security Cameras |
| knx course | KNX Training Course |
| smart doorlock | Smart Door Lock |
| vacuum cleaner | Vacuum Cleaner |
| parking system | Parking System |
| *(+ more)* | |

New campaigns can be added by simply adding one line to the `formMap` in the Code node.

---

## 🚀 Setup

### Prerequisites
- n8n instance (self-hosted or cloud)
- Facebook Business account with Lead Ads access
- Odoo instance with CRM module

### Steps

1. **Import the workflow** — upload `Facebook_Leads_to_Odoo.json` into n8n
2. **Connect Facebook credentials** — OAuth2 via Facebook Lead Ads node
3. **Connect Odoo credentials** — add your Odoo URL, database, username, and API key
4. **Update the Form IDs** in the Code node to match your actual Facebook form IDs
5. **Set Salesperson ID and Team ID** to match your Odoo users
6. **Activate the workflow** — it runs live via webhook

---

## 📁 Repository Structure

```
facebook-leads-odoo/
├── Facebook_Leads_to_Odoo.json   # n8n workflow (import this)
├── workflow.png                   # Workflow screenshot
└── README.md
```

---

## 💡 Notes

- The workflow runs **24/7** as a live webhook — no polling, no delays
- Adding a new campaign = 1 line of code in the `formMap` object
- Built for **LVX** (Smart Home & Lighting Systems) — adaptable to any business using Facebook Lead Ads + Odoo

---

*Built by [Asem Ahmed](https://linkedin.com/in/asem-ahmed-823b60353) — AI Automation Engineer*
