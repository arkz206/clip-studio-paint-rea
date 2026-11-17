\# Clip Studio Paint - Reverse Engineering Notes (Windows)



Análise do binário ClipStudioPaint.exe (versão 1.5) usando radare2 6.2.6.



\## Status: Em andamento



O binário é \*\*stripped\*\* e \*\*ofuscado\*\* (anti-debug via `rax ^= rsp`).

As notas públicas existentes são para macOS (lihaochen910). Este repo documenta

o progresso na versão Windows.



\## O que já foi identificado



\- Namespace interno: `Planeswalker::Venser` e `Planeswalker::Urza`

\- Classe de verificação: `VEActivationEngine`

\- Classe de resultado: `VEEncryptResultCode`

\- Ponto de patch (documentado p/ macOS): `operator==` de `VEEncryptResultCode`

\- Strings-chave: `diverge\_expirelicense`, `diverge\_unusablelicense`,

&#x20; `applicationlicenserecheck`, `activation\_boot\_old\_version\_license`



\## O que falta



\- Achar o `operator==` (não é virtual, não aparece na vtable)

\- Binário é stripped — sem nomes de funções

\- Vtable é construída em runtime (busca por bytes não achou)



\## Ferramentas



\- radare2 6.2.6 (r2blob.static.exe)

\- Windows 64-bit



\## Aviso



Este projeto é para fins educacionais. A engenharia reversa de software

licenciado pode violar termos de uso e leis locais.   

