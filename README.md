# mail_sending_python
This project demonstrates how to send emails using Python's built-in smtplib and email libraries. It serves as a practical example for automating email communication, with a simple yet functional design. This project can be extended for a wide range of applications, from personal notifications to automated systems.
# Email Sending Project

This project demonstrates how to send emails using Python's built-in `smtplib` and `email` libraries. The script is simple yet functional, providing a foundational understanding of email automation with Python. It connects to Gmail's SMTP server to send an email with a predefined subject and message body.

---

## Features

- **Secure Authentication**: Uses `getpass` for secure password entry.
- **SMTP Server Communication**: Connects to Gmail's SMTP server with TLS encryption.
- **Email Drafting**: Automatically drafts the email with a subject, sender, recipient, and body.
- **Simple Design**: Easy to use and understand for beginners.

---

## Requirements

- Python 3.x
- Gmail account

### Python Libraries

The following libraries are used:

- `smtplib`: Handles SMTP connections and email sending.
- `email.mime.text`: Constructs the email content.
- `getpass`: Secures password entry in the terminal.

---

## Setup and Usage

### 1. Clone the Repository
```bash
$ git clone https://github.com/your-username/email-sending-project.git
$ cd email-sending-project
```

### 2. Install Python
Ensure you have Python 3.x installed on your system. You can download it from [python.org](https://www.python.org/downloads/).

### 3. Run the Script

Open the terminal and execute the following command:

```bash
$ python send_email.py
```

### 4. Enter Credentials

When prompted, enter the password for the sender email address securely in the terminal. Ensure the sender email address and password are correct.

---

## Script Overview

### `send_email.py`

```python
def send_email():
    import smtplib
    from email.mime.text import MIMEText
    from getpass import getpass

    sender_address = 'your-email@gmail.com'
    password = getpass("Enter your email password: ")
    subject = 'Testing Email Script'
    msg = '''\nThis is a test email sent using Python's smtplib and email libraries.\n'''

    # Initialize server
    server = smtplib.SMTP('smtp.gmail.com', 587)
    server.starttls()
    server.login(sender_address, password)

    # Draft message
    email = MIMEText(msg)
    email['Subject'] = subject
    email['From'] = sender_address
    email['To'] = 'recipient-email@gmail.com'

    # Send email
    server.sendmail(sender_address, 'recipient-email@gmail.com', email.as_string())
    server.quit()

    print("Email sent successfully!")

send_email()
```

---

## Enhancements

1. **Dynamic Input**: Allow users to input recipient email, subject, and message at runtime.
2. **HTML Emails**: Support rich HTML content for professional email layouts.
3. **Error Handling**: Add robust error handling for invalid credentials, SMTP issues, and other exceptions.
4. **Bulk Emails**: Extend the script to send emails to multiple recipients.
5. **OAuth 2.0**: Implement secure authentication using Gmail's OAuth 2.0.

---

## License

This project is licensed under the MIT License. You are free to use, modify, and distribute it as needed.

---

## Contribution

Feel free to fork this repository and submit pull requests for enhancements or bug fixes. Contributions are always welcome!

