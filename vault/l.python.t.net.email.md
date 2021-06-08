---
id: 448ea565-58e5-4c7c-8de0-264079ac8c38
title: Email
desc: ''
updated: 1611630438786
created: 1611630412463
---


## Cook

### email
```py
import smtplib, ssl

port = 587  # For starttls
smtp_server = ""
sender_email = ""
receiver_email = ""
password = ""
message = """\
Subject: Hi there

This message is sent from Python."""

context = ssl.create_default_context()
with smtplib.SMTP(smtp_server, port) as server:
    server.ehlo()  # Can be omitted
    server.starttls(context=context)
    server.ehlo()  # Can be omitted
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message)
```
