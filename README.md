# Event Booking System (EBS)

The **Event Booking System (EBS)** is a workflow built on **Airtable** (with optional Google integrations) to manage and coordinate event requests at Skylinks.  
It provides a streamlined way to collect requests, track availability, and manage scheduling conflicts.

---

## Features

- 📅 **Event Requests Table** – stores all incoming requests with details such as date, contact, and notes.  
- 🔗 **Shared Dates Linking** – automatically links requests that occur on the same day, making it easy to identify conflicts or overlaps.  
- ⚡ **Scripts & Automations** – custom Airtable scripts ensure records stay linked and up-to-date.  
- 🛠️ **Extendable** – designed to integrate with Google Calendar, Slack, or other middleware via Apps Script or Google Cloud Functions.

---

## Repository Structure

```
.
├── scripts/             # Airtable scripts used in the base
│   └── link-shared-dates.js   # Links records with matching dates
├── docs/                # Documentation, policies, and usage guides
├── .gitignore
└── README.md
```

---

## Setup

### Prerequisites
- Airtable base with a table called **`Event Requests`**
- Fields:
  - `Date` (Date or DateTime field)
  - `Shared Dates` (Linked record field, links to the same table, allows multiple records)

### Steps
1. Copy the scripts from `scripts/` into an **Airtable Scripting App** block in your base.
2. Adjust the config section at the top of the script to match your field names if they differ.
3. Run the script to link all records with the same date.

---

## Usage

- **Run manually**: Use the Scripting app to update links across the table.  
- **Automation option**: (coming soon) Scripts can be adapted to run automatically on new/updated records.  
- **Coordinator workflow**: Filter the `Event Requests` table where `Shared Dates` is not empty to quickly see overlaps.

---

## Roadmap

- [ ] Google Calendar sync for confirmed events  
- [ ] Slack integration for event notifications  
- [ ] Web form frontend for public event requests  
- [ ] Automation scripts for always-on linking  

---

## Contributing

1. Fork this repository  
2. Create a feature branch (`git checkout -b feature/new-thing`)  
3. Commit your changes (`git commit -m 'Add feature'`)  
4. Push to the branch (`git push origin feature/new-thing`)  
5. Open a Pull Request

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
