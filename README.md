# 🧠 CrackMe Challenge – "Remove the Nag" by TDC

This repository contains my reverse engineering walkthrough and patch for the classic CrackMe challenge by **The Dutch Cracker (TDC)**.

> 📚 Part of my coursework for Malware Analysis and Cyber Defence  
> 🛠️ Reverse engineered and patched in under 12 hours  
> ✨ Goal: Turn a nagging binary into a grateful one

---

## 🎯 Objectives

- Remove the nag screen at startup  
- Make the "Re-Check" button display:  
  `"Thank you for registering this software"`  
- Change the status box to:  
  `"Clean crack! Good Job!"`

---

## 🗂️ Repository Structure

```text
emove-the-nag-by-tdc/
├── README.md                 # You're reading this!
├── RemoveTheNag.7z           # Original CrackMe binary (unmodified)
├── patch_notes.md            # Patch strategy and byte-level summary
├── screenshots/              # Before/after snapshots from IDA
│   ├── before_patch.png
│   └── after_patch.png
└── patched_binary.exe       # Patched binary if legally shareable
```

---

## 📖 Write-Up

👉 Read the full Medium article for a fun and philosophical breakdown:  
🔗 [https://medium.com/](https://medium.com/@avinasharma.2412/i-patched-a-binary-until-it-thanked-me-reverse-engineering-remove-the-nag-by-the-dutch-cracker-0eacc749b9b3)


---

## ⚠️ Disclaimer

This repository is for **educational purposes only**.  
No copyrighted or malicious software is included or distributed.  
Reverse engineering was performed on a publicly available CrackMe intended for legal, academic learning.

---

## 🧠 Key Learnings

- 🌀 Don’t trust shiny strings — they distract
- 🖱️ GUI apps need interaction — click before you hack
- 📊 Global variables are the heartbeat of binary state
- 🧘‍♂️ Reverse engineering is about listening, not brute-forcing

---

## 🧰 Tools Used

- IDA Free 8.3
- HxD Hex Editor
- Windows 10 VM (FlareVM)

---

Happy reversing! 🎯
