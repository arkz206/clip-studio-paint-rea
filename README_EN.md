\# Clip Studio Paint - Reverse Engineering Notes (Windows)



Analysis of ClipStudioPaint.exe (version 1.5) using radare2 6.2.6.



\## Status: In progress



The binary is \*\*stripped\*\* and \*\*obfuscated\*\* (anti-debug via `rax ^= rsp`).



Existing public notes are for macOS (lihaochen910). This repo documents

progress on the Windows version.



\## What has been identified



\- Internal namespace: `Planeswalker::Venser` and `Planeswalker::Urza`

\- Verification class: `VEActivationEngine`

\- Result class: `VEEncryptResultCode`

\- Patch point (documented for macOS): `operator==` of `VEEncryptResultCode`

\- Key strings: `diverge\_expirelicense`, `diverge\_unusablelicense`,

&#x20; `applicationlicenserecheck`, `activation\_boot\_old\_version\_license`



\## What's missing



\- Find the `operator==` (not virtual, not in vtable)

\- Binary is stripped — no function names

\- Vtable is built at runtime (byte search found nothing)



\## Tools



\- radare2 6.2.6 (r2blob.static.exe)

\- Windows 64-bit



\## Disclaimer



This project is for educational purposes only. Reverse engineering of

licensed software may violate terms of service and local laws.   

