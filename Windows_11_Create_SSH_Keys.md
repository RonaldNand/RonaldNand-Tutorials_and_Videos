# 🔐 Setting Up ED25519 SSH Keys on Windows 11

## 🔧 Step 1: Open PowerShell
Right-click **Start** → **Windows Terminal (Admin)** or open **PowerShell** normally.

---

## 🗝️ Step 2: Generate an ED25519 Key
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- `-C` adds a comment to help identify your key.
- When prompted:
  - **Enter file to save the key** → Press `Enter` to accept default (`C:\Users\<You>\.ssh\id_ed25519`)
  - **Enter passphrase** → Optional but recommended. Leave empty if you want no passphrase.

---

## 📁 Step 3: Key File Location
Your keys are saved in:

```
C:\Users\<YourUsername>\.ssh\
```

- `id_ed25519` — Your **private key** (keep this safe!)
- `id_ed25519.pub` — Your **public key** (you share this one)

---

## 📤 Step 4: Copy Public Key to Remote Server

### Option 1: Using `ssh-copy-id` (if installed)
```bash
ssh-copy-id -i ~/.ssh/id_ed25519.pub user@remote_host
```

### Option 2: Manual Copy
1. Open the public key file in Notepad:
   ```
   notepad $env:USERPROFILE\.ssh\id_ed25519.pub
   ```
2. Connect to your remote server:
   ```bash
   ssh user@remote_host
   ```
3. Paste the contents into the file `~/.ssh/authorized_keys` on the remote server.
   Make sure permissions are correct:
   ```bash
   chmod 700 ~/.ssh
   chmod 600 ~/.ssh/authorized_keys
   ```

---

## 🚀 Step 5: SSH Using Your Key
If your key is in the default location:
```bash
ssh user@remote_host
```

Or specify it manually:
```bash
ssh -i ~/.ssh/id_ed25519 user@remote_host
```

---

## 🛠️ Optional: Use SSH Agent for Convenience

### Start the SSH agent service
```bash
Start-Service ssh-agent
```

### Add your key to the agent
```bash
ssh-add ~\.ssh\id_ed25519
```

This allows you to authenticate without retyping your passphrase each time.

---

## ✅ Done!
You’re now set up to use ED25519 SSH keys on Windows 11 🎉

Need help adding your key to GitHub, GitLab, or another service? Just ask!
