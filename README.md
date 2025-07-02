# Password-Checker

Password Security Analysis This repository provides a guide to creating strong passwords, evaluating their strength using cracklib, and understanding common password attacks. Follow the steps below to create a set of sample passwords, test their complexity, and learn how to improve password security. Introduction Passwords are a critical line of defense in cybersecurity. This project demonstrates how to:

Create passwords with varying complexity. Evaluate their strength using cracklib. Research common password attacks (e.g., brute force, dictionary attacks). Summarize how complexity impacts security.

The process is based on the instructions in the provided document and uses tools like cracklib and Kali Linux wordlists to analyze password strength and vulnerabilities. Prerequisites

Linux Environment: Preferably Ubuntu or Kali Linux. Tools: cracklib for password strength checking. hydra or john for simulating brute force attacks (optional, for Kali Linux users). Access to /usr/share/wordlists/rockyou.txt (available in Kali Linux for dictionary attack research).

Permissions: Root or sudo access to install packages and access files.

Install required tools: sudo apt update sudo apt install libcrack2

For dictionary attack research (Kali Linux): gunzip /usr/share/wordlists/rockyou.txt.gz

Usage Follow these steps to create, evaluate, and analyze passwords. Step 1: Create Sample Passwords

Create a file named passwords.txt with sample passwords of varying complexity:nano passwords.txt

Add the following passwords (or your own):password password123 Pass@20251 S3cur3P@ssword1! VeryStrong&Long@ss20251

Save with Ctrl + O, Enter, then exit with Ctrl + X.

Step 2: Test Password Strength Use cracklib-check to evaluate the passwords: while read password; do echo "$password" | cracklib-check done < passwords.txt

Example Output: password: It is based on a dictionary word password123: It is based on a dictionary word Pass@20251: OK S3cur3P@ssword1!: OK VeryStrong&Long@ss20251: OK

Step 3: Save Evaluation Results Save the cracklib-check output to a file: while read password; do echo "$password" | cracklib-check >> results.txt done < passwords.txt cat results.txt

Step 4: Document Password Tips Create a file to note best practices for strong passwords: nano password_tips.txt

Add tips:

Use 12+ characters.
Include symbols (e.g., #, @, !, &).
Mix uppercase, lowercase, and numbers.
Avoid dictionary words.
Avoid keyboard patterns (e.g., qwerty).
Save and exit. Step 5: Research Common Password Attacks Understand vulnerabilities by researching common attacks:

Brute Force Attack: Tools like hydra or john try all possible combinations. Complex passwords take longer to crack. Dictionary Attack: Uses wordlists like rockyou.txt (millions of real leaked passwords).head /usr/share/wordlists/rockyou.txt

This displays common passwords to avoid.

Step 6: Summarize Password Complexity Document how complexity improves security: nano password_summary.txt

Add summary: Password complexity greatly increases security.

Longer passwords reduce brute-force success.
Symbols defeat pattern-based guesses.
Avoiding dictionary words blocks simple dictionary attacks.
Save and exit. Files Created

File Name Description

passwords.txt List of sample passwords

results.txt Output from cracklib-check

password_tips.txt Best practices for strong passwords

password_summary.txt Impact of password complexity on security

Best Practices

Length: Use passwords with 12+ characters. Diversity: Combine uppercase, lowercase, numbers, and symbols. Avoid Common Words: Do not use dictionary words or predictable patterns. Unique Passwords: Use different passwords for each account. Password Managers: Consider tools like Bitwarden for secure storage. Two-Factor Authentication (2FA): Enable 2FA for added security.

Security Considerations

Avoid Hardcoding Passwords: Never store passwords in plain text in scripts or repositories. Use environment variables or configuration files excluded from version control (e.g., .gitignore). Check for Breaches: Use tools like haveibeenpwned to check if passwords have been leaked. Secure Repositories: Ensure sensitive data is not exposed in public GitHub repositories. Consider adding a SECURITY.md file for vulnerability reporting.

Contributing Contributions are welcome! Please submit a pull request or open an issue to suggest improvements or report bugs. See CONTRIBUTING.md for guidelines. License This project is licensed under the MIT License. See the LICENSE file for details.
