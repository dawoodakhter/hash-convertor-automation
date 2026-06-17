# 🔐 Google Drive File Hash Generator

An n8n automation workflow that automatically generates SHA-256 cryptographic hashes for files stored in Google Drive — ensuring file integrity verification without any manual processing.

---

## 🚨 The Problem

When sharing or storing important files, how do you know a file hasn't been tampered with or corrupted?

Manually generating hashes for files is:
- Time-consuming, especially at scale
- Requires technical knowledge of command-line tools
- Not practical for non-technical teams

---

## ✅ The Solution

This workflow automates file integrity verification by automatically downloading files from Google Drive, computing their SHA-256 hash, and logging the result — ready to share or verify at any time.

---

## ⚙️ How It Works

```
Google Drive File
    │
    ▼
📂 Google Drive Node (downloads target file as binary)
    │
    ▼
🔐 Crypto / Code Node (computes SHA-256 hash)
    │
    ▼
📋 Output (hash logged / returned for verification)
```

### Step-by-step:
1. **Google Drive Node** — fetches the target file from Drive as a binary stream
2. **Code Node** — runs SHA-256 hashing on the binary data using JavaScript's built-in crypto
3. **Output** — the resulting hash is logged or passed to the next step (Sheets, email, etc.)

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| [n8n](https://n8n.io) | Workflow automation platform |
| Google Drive API | File access and download |
| JavaScript (Code Node) | SHA-256 hash computation |

---

## 📋 Prerequisites

- n8n Cloud account (or self-hosted n8n)
- Google account with Drive access
- Google Drive OAuth2 credential configured in n8n

---

## 🚀 Setup

1. **Import** the `workflow.json` into your n8n instance
2. **Configure credentials:**
   - Add Google Drive OAuth2 credential in n8n
3. **Update the Google Drive node** with the target File ID you want to hash
4. **Run the workflow** — the SHA-256 hash will be output in the execution results
5. **Optionally extend** the workflow to log results to Google Sheets or send via email
6. **Publish** the workflow in n8n Cloud to activate it on a schedule if needed

---

## 🔑 What is SHA-256?

SHA-256 (Secure Hash Algorithm 256-bit) is a cryptographic hash function that produces a unique 64-character fingerprint for any file. Even a single byte change in the file produces a completely different hash — making it ideal for verifying file integrity.

**Example output:**
```
e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855
```

---

## 💡 Use Cases

- Verify files haven't been tampered with after sharing
- Academic file submission integrity checks
- Audit trails for document management
- Pre/post transfer file verification

---

## 📁 Project Structure

```
google-drive-file-hash-generator/
├── workflow.json          # n8n workflow export
├── README.md              # This file
```

---

## 👤 Author

**Daud** — AI Automation Engineer  
[LinkedIn](https://linkedin.com/in/your-profile) • [GitHub](https://github.com/your-username)

---

## 📄 License

MIT License — feel free to use and adapt this workflow for your own projects.
