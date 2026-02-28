Switched 2FA from SMS to Authentication App (Google Authenticator)
1. Checked email account for any associated suspicious activity
1. Reviewed haveibeenpwned.com to check for credential exposure in known breaches
1. Added carrier-level PIN lock to phone account to prevent future SIM attacks

-----

## 📚 Lessons Learned

|Lesson                                   |Application                                        |
|-----------------------------------------|---------------------------------------------------|
|SMS 2FA is not truly secure              |Always use authenticator app when available        |
|Sleep hours are high-risk windows        |Set alerts for after-hours login attempts          |
|Platform anomaly detection saves accounts|Enable all security notifications on every platform|
|IP and device logging provides evidence  |Document all incident details immediately          |
|Fast response limits damage              |Account recovered before significant harm occurred |

-----

## 🔧 Recommended Defenses

For Users:

- Replace SMS 2FA with authenticator apps (Google Authenticator, Authy)
- Use unique passwords per platform (password manager recommended)
- Enable login notifications on all accounts
- Add PIN lock to your mobile carrier account

For Developers/Platform Security:

- Implement device fingerprinting alongside SMS verification
- Flag logins from geographically distant IPs within short timeframes
- Rate-limit OTP requests to prevent brute-force attempts
- Consider FIDO2/WebAuthn as a stronger alternative to SMS OTP

-----

## 🎓 Skills Demonstrated

- Real-world security incident documentation
- Attack vector analysis and threat modeling
- Knowledge of SS7 protocol vulnerabilities
- Understanding of 2FA mechanisms and their weaknesses
- Incident response methodology
- Security hardening recommendations

-----

## 📖 References

- NIST Special Publication 800-63B — Digital Identity Guidelines
- SS7 Vulnerability Research — Positive Technologies (2014–2018)
- Snapchat Security Transparency Report
- OWASP Authentication Cheat Sheet

-----

*This report documents a real security incident experienced by the author. All sensitive personal information has been redacted. This writeup is intended as an educational resource and portfolio demonstration of security analysis skills.*

Author: Cybersecurity Student | CompTIA A+, Network+, Security+ Certified  
GitHub: github.com/xavianab/cybersecurity-labs
