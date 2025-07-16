# 🔧 patches.txt – Byte-Level Changes for "Remove the Nag" CrackMe by TDC

This document lists the direct byte-level modifications made to the binary during reverse engineering.

---

## 🧠 Target

- Binary: RemoveTheNag.exe
- Architecture: Win32
- Target subroutine: sub_4011AF
- Patch location: (approx.) offset 0x114A within the .text section

---

## 🧪 Original Assembly Instructions (Disassembly)

```
40114A: push offset String2   ; e.g., 0x406050
40114F: push offset String1   ; e.g., 0x406040
401154: call lstrcmpA
401159: test eax, eax
40115B: jnz  loc_4011B3
```

### Corresponding Hex Bytes (example)
```
68 50 60 40 00   push 0x406050
68 40 60 40 00   push 0x406040
E8 ...           call lstrcmpA
85 C0            test eax, eax
75 56            jnz loc_4011B3
```

---

## 🛠️ Patched Assembly

Goal: Force `lstrcmpA` to always succeed by comparing same string.

```
40114A: push offset String1   ; 0x406040
40114F: push offset String1   ; 0x406040
```

### Patched Hex Bytes
```
68 40 60 40 00   push 0x406040
68 40 60 40 00   push 0x406040
```

Only the first push instruction was changed to match the second one.

---

## ✅ Result

- lstrcmpA returns 0 (strings equal)
- test eax, eax → Zero Flag set → jnz skipped
- byte_4032B0 = 1 → triggers success logic

Message box: “Thank you for registering this software”  
Status box: “Clean crack! Good Job!”  
Nag screen removed

---

📝 Note: Offsets may vary depending on build version. Always verify in your own disassembler before applying patches.
