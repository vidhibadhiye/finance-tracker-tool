# UPAY – NGO Finance Tracker

## 📁 Folder Structure

```
upay-project/
│
├── backend/
│   ├── server.js              ← START HERE – runs the server
│   ├── storage.js             ← All Excel read/write logic
│   ├── package.json           ← Library list
│   ├── upay-data.xlsx         ← YOUR DATA (auto-created on first run)
│   │
│   ├── middleware/
│   │   └── auth.js            ← Checks login tokens
│   │
│   └── routes/
│       ├── auth.js            ← Login / logout
│       ├── transactions.js    ← Add, edit, delete, list transactions
│       ├── logs.js            ← Activity log (admin only)
│       └── users.js           ← Manage user accounts (admin only)
│
└── frontend/
    └── index.html             ← The app UI – open in browser
```

---

## 🚀 How to Run

### Step 1 – Install Node.js (once ever)
Download from https://nodejs.org → choose the **LTS** version → install normally.

Verify it worked:
```
node --version
```

### Step 2 – Open a terminal in the backend folder
```bash
cd upay-project/backend
```

### Step 3 – Install libraries (once ever)
```bash
npm install
```

### Step 4 – Start the server
```bash
node server.js
```

You should see:
```
✅  UPAY server running  →  http://localhost:3000
📊  Data file            →  backend/upay-data.xlsx
✅  upay-data.xlsx created with default users + sample transactions
```

### Step 5 – Open the app
Go to **http://localhost:3000** in your browser.

---

## 🔑 Default Login Credentials

| Role  | Username | Password  |
|-------|----------|-----------|
| Admin | admin    | admin123  |
| Staff | staff1   | staff123  |

> ⚠️ To change passwords: open `upay-data.xlsx` → go to the **Users** sheet → edit the password column → save the file.

---

## 📊 About the Excel File

`upay-data.xlsx` is created automatically the first time you start the server.
It has **3 sheets**:

| Sheet        | What it stores                              |
|--------------|---------------------------------------------|
| Transactions | All financial records                       |
| Users        | Login credentials for admin and staff       |
| Logs         | History of every add / edit / delete action |

You can open this file in Excel or Google Sheets anytime to view your data,
make bulk edits, or create custom reports — just don't rename the sheets or columns.

---

## 💡 Tips

**Auto-restart when you edit code:**
```bash
npm run dev
```

**To add a new staff member:** Open `upay-data.xlsx` → Users sheet → add a new row
with id, username, password, name, role (`staff`), created_at.

**To reset all data:** Delete `upay-data.xlsx` and restart the server.
It will recreate fresh with sample data.

---

## 🆘 Troubleshooting

| Problem | Solution |
|---------|----------|
| `Cannot find module` error | Run `npm install` inside the `backend` folder |
| Port 3000 already in use | Change `const PORT = 3000` in `server.js` to `3001`, then visit `http://localhost:3001` |
| "Login failed" in browser | Make sure `node server.js` is running first |
| App shows no data | Check the terminal – look for any error messages |
| Want to reset everything | Delete `upay-data.xlsx` and restart the server |
