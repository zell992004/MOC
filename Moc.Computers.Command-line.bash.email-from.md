---
id: 34hgzpnooj3mgn4pzsyo8lg
title: email-from
desc: ''
updated: 1702827452784
created: 1702827433002
---

# email from bash


Yes, you can send an email through the command line using Gmail's SMTP (Simple Mail Transfer Protocol) server. You can achieve this by using a command-line tool called `sendmail` or using the `swaks` (Swiss Army Knife for SMTP) tool. Here are the steps for both methods:

Using `sendmail`:

1. Install the `ssmtp` package by running the following command:

   ```bash
   sudo apt-get install ssmtp
   ```

2. Configure `ssmtp` by editing the `/etc/ssmtp/ssmtp.conf` file. Open the file using a text editor and update it with the following configuration:

   ```conf
   mailhub=smtp.gmail.com:587
   UseSTARTTLS=YES
   FromLineOverride=YES
   AuthUser=your_email@gmail.com
   AuthPass=your_gmail_password
   ```

   Replace `your_email@gmail.com` with your Gmail email address and `your_gmail_password` with your Gmail account password. Save and close the file.

3. Use the `echo` command to compose the email content and pipe it to `sendmail`:

   ```bash
   echo "Subject: Your email subject" | sudo sendmail -f from_email@gmail.com to_email@gmail.com
   ```

   Replace `from_email@gmail.com` with your Gmail email address and `to_email@gmail.com` with the recipient's email address. Modify the subject and content of the email as needed.

Using `swaks`:

1. Install `swaks` by running the following command:

   ```bash
   sudo apt-get install swaks
   ```

2. Use the following command to send an email:

   ```bash
   swaks --from from_email@gmail.com --to to_email@gmail.com --server smtp.gmail.com:587 --auth-user your_email@gmail.com --auth-password your_gmail_password --tls --header "Subject: Your email subject" --body "Your email content"
   ```

   Replace `from_email@gmail.com` with your Gmail email address, `to_email@gmail.com` with the recipient's email address, `your_email@gmail.com` with your Gmail email address, `your_gmail_password` with your Gmail account password, and modify the subject and content of the email as needed.

Please note that using your Gmail account credentials in the command line can pose a security risk. Make sure to keep your credentials confidential and consider alternative secure methods like using an application-specific password or setting up 2-step verification for your Gmail account.

```bash
echo -e "Subject: Your email subject\nFrom: from_email@gmail.com\nTo: to_email@gmail.com\nMIME-Version: 1.0\nContent-Type: multipart/mixed; boundary=boundary-string\n\n--boundary-string\nContent-Type: text/plain\n\nYour email body\n\n--boundary-string\nContent-Type: application/octet-stream\nContent-Disposition: attachment; filename=vpnclient.mobileconfig\n\n" | cat - vpnclient.mobileconfig | sendmail -t -oi
```