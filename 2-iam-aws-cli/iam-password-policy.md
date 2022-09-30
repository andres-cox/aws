# IAM password policy

Strong Passwords = higher security for your account

In AWS you can setup a password policy:

    - Set a minimun password length
    - Require specific character type
    - Allow all IAM users to change their passwords
    - Require users to change their password after some time (password expiration)
    - Prevent password re-use

# Multi Factor Authentication - MFA

MFA = password you know + security device you own

Main benefit: if a password is stolen or hacked, the account is not compromised

Devices option

    - Virtual MFA device (phone, other devices)
    - Universal 2nd Factor (U2F) Security key -> usb
    - Hardware Key Fob MFA device -> usb
    - Hardware Key Fob MFA device for AWS GovCloud (US) -> usb surepassID 