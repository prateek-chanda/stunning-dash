# 📡 SMU ELDIS Radar Dashboard Generator

```
 ███████╗██╗     ██████╗ ██╗███████╗    ██████╗  █████╗ ██████╗  █████╗ ██████╗ 
 ██╔════╝██║     ██╔══██╗██║██╔════╝    ██╔══██╗██╔══██╗██╔══██╗██╔══██╗██╔══██╗
 █████╗  ██║     ██║  ██║██║███████╗    ██████╔╝███████║██║  ██║███████║██████╔╝
 ██╔══╝  ██║     ██║  ██║██║╚════██║    ██╔══██╗██╔══██║██║  ██║██╔══██║██╔══██╗
 ███████╗███████╗██████╔╝██║███████║    ██║  ██║██║  ██║██████╔╝██║  ██║██║  ██║
 ╚══════╝╚══════╝╚═════╝ ╚═╝╚══════╝    ╚═╝  ╚═╝╚═╝  ╚═╝╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝
                     Operations Dashboard Generator v1.0
```

> 🎯 **A fun, practical Python tool for generating professional Excel dashboards** to manage SMU ELDIS Radar operations and GoI-style project lifecycles!

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 📊 **Control Panel** | One-page KPI dashboard with metrics overview |
| 📋 **Routine Tracking** | Pre-populated SMU action items (Sl.No 43-51) |
| 🏗️ **Project Lifecycle** | GoI-style tender tracking with stages |
| 🎨 **Conditional Formatting** | 🔴 Red for overdue • 🟡 Yellow for due soon • 🟢 Green for completed |
| 📝 **Data Validation** | Dropdown menus for Status, Priority, SLA |
| ❄️ **Frozen Headers** | Easy scrolling with fixed header rows |
| 📐 **Auto-Fit Columns** | Professional column widths |

---

## 🚀 Quick Start

### Installation

```bash
# Clone the repository
git clone https://github.com/prateek-chanda/stunning-dash.git
cd stunning-dash

# Install dependencies
pip install -r requirements.txt
```

### Usage

```bash
# Generate the dashboard
python generate_dashboard.py
```

This creates `SMU_Lite_Dashboard.xlsx` in the current directory.

---

## 📁 Output Structure

The generated Excel workbook contains **4 sheets**:

### 1️⃣ Control_Panel (Dashboard)
A summary view with key metrics:
- 📋 Total Actions count
- 🟡 Open / In Progress counts
- ✅ Completed count
- 🔴 Overdue count
- ⏱️ Average Days Remaining
- ⚠️ Backlog > 30 Days

### 2️⃣ Routine_Table
Pre-populated with SMU action items (Sl.No 43-51):

| Sl.No | Action Point | Status |
|-------|-------------|--------|
| 43 | Finalization of policy for routine optimization of RADARs | Open |
| 44 | Expansion of in-house repair capabilities for ADS-B sensors | Open |
| 45 | Advance Factory Training Policy for SMU executives | Open |
| 46 | Policy for Dedicated Vehicles for SMUs | Open |
| 47 | Establishment of Test System Facility at SMU A-SMGCS | In Progress |
| 48 | In-House ITC for RADARs | Open |
| 49 | Provision of broadband & firewall at A-SMGCS stations | Open |
| 50 | Standard packing & insurance for spares sent to SMU | In Progress |
| 51 | Surveillance SMU rep in CNS/ATM Automation spec committees | Open |

**Calculated columns:**
- **Days Remaining**: Due Date - Today
- **Days Open**: Today - Open Date
- **Overdue Flag**: "OVERDUE" if past due and not completed

### 3️⃣ Project_Table
GoI-style tender lifecycle tracking:

| Project ID | Project Title | Stage |
|------------|---------------|-------|
| P-01 | ASMGCS Test System Procurement | Procurement |
| P-02 | ADS-B In-house Repair Capability | Tech Validation |
| P-03 | Radar ITC In-house Implementation | Proposal |

### 4️⃣ Lists
Reference data for dropdown validations:
- **Status**: Open, In Progress, Completed, Blocked
- **Priority**: High, Medium, Low
- **SLA**: Routine, Strategic, Project, Emergency
- **Project Stages**: Concept → Feasibility → AA → FC → RFP → Bidding → Evaluation → Award → Execution → Testing → Closure

---

## 🎨 Visual Styling

### Conditional Formatting
| Color | Meaning |
|-------|---------|
| 🔴 Red | Overdue items (past due date, not completed) |
| 🟡 Yellow | Items due within 7 days |
| 🟢 Green | Completed items |

### Professional Styling
- **Headers**: Bold white text on dark blue background
- **Borders**: Thin borders around all data cells
- **Alignment**: Centered headers, wrapped text

---

## 📸 Screenshot

*Dashboard preview coming soon!*

```
┌─────────────────────────────────────────────────────────────────┐
│  📊 SMU ELDIS RADAR DASHBOARD                                   │
│  Operations Control Panel | Generated: 2025-12-04              │
├─────────────────────────────────────────────────────────────────┤
│  📈 KEY PERFORMANCE INDICATORS                                  │
│  ┌──────────────────┬───────┬────────────────────────────────┐  │
│  │ 📋 Total Actions │   9   │ Total tracked action items     │  │
│  │ 🟡 Open/Progress │  7/2  │ Items awaiting action          │  │
│  │ ✅ Completed     │   0   │ Successfully closed items      │  │
│  │ 🔴 Overdue       │   9   │ Items past due date            │  │
│  └──────────────────┴───────┴────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🛠️ Technical Details

- **Python Version**: 3.8+
- **Dependencies**: openpyxl >= 3.1.0
- **Output Format**: `.xlsx` (Excel 2007+)

---

## 🔄 Regenerating the Dashboard

The script is **reusable** - simply run it again to generate a fresh dashboard with updated dates:

```bash
python generate_dashboard.py
```

Each run recalculates:
- Days Remaining
- Days Open
- Overdue flags
- Dashboard metrics

---

## 📜 License

MIT License - Feel free to use and modify!

---

## 🤝 Contributing

Contributions welcome! Feel free to:
- 🐛 Report bugs
- 💡 Suggest features
- 🔧 Submit pull requests

---

<p align="center">
  Made with ❤️ for SMU Operations Management<br>
  <sub>🛰️ Keeping the radars running smoothly!</sub>
</p>
