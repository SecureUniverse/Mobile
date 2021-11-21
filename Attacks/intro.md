# Intro

## OWASP
- API security in backend

- Profiling & passive monitoring in SOC
  - Find security bridges and api hook

- Obfuscation
  - MSTG-RESILIENCE-5 
  - DexProtector (better than ProGaurd & DesxGaurd)
    - Just some function of app should be obfuscated 
  - Frida Hooking (Objection)

- Root/Jailbreak detection
  - Frida is possible to work non-root (very advanced)
  - 90% of apps use RootGear
    - Change Function names & strings in root detection libraries
  - Library methods
    - Access to /usr/bin 
    - Check syscal requests to kernel
    - Use of .so files 
  - Root detection should check in
    - Sign up
    - Card to card
    - Send OTP

- Emulator detection
  - MSTG-RESILIENCE-5 
  - Android: Genymotion
  - IOS: Nothing
  - Check in sign-up process and then lock the app

- Certificate / Public / SSL Pinning
  - MSTG-NETWORK-4 
  - Attackers want to access api, abuse it and proxy the traffic
  - Do not use pulic libraries (Frida => Universal SSL unpinning) and we should customize it

- Check Local Storage
  - MSTG-STORAGE-1 & MSTG-STORAGE-2
  - Encrypt data that we need to store in user device storage
  - Do not use pulic libraries (Frida => hook encrypted library and convert it to plain (in runtime))
    - Offline: Encrption
    - Online: Chech request that are send from app to server with state of local storage encryption and lock the app and it's ID

- Message Encryption (Body Level)
  - MSTG-NETWORK-1 & MSTG-NETWORK-2
  - We assume that SSL Pining (protocol security) can be bypassed, then message body should be encrypted (application security)

- Testing File Integrity Checks 
  - MSTG-RESILIENCE-3
  - Decompile => Smali => Compile
  - Check Integrity with SHA1 to prevent reverse

- All can be bypassed by a lot of memory dump, to find functions

- SOC Detection
  - Many transaction from an IP
  - Many sing up from an IP 

## Fraud Detection


## Process

