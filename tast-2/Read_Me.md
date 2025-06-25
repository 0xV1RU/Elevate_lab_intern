# 🛡️ Phishing Email Analysis Report – Task 2
## 🎯 Objective Objective: 
Identify phishing characteristics in a suspicious email sample.

##  Header Analysis
    
    Delivered-To: themajoronearth@gmail.com
    Received: by 2002:a92:bd02:0:0:0:0:0 with SMTP id c2csp3604485ile;
            Mon, 25 Jan 2021 22:41:18 -0800 (PST)
    X-Google-Smtp-Source: ABdhPJxMrOAiiW/tZAHOxAwohqg8F8fLpv1xou4CoJ8r9tPXaBGlDruGLq5PtDzenNW5arGU5A99
    X-Received: by 2002:adf:9b92:: with SMTP id d18mr4483603wrc.170.1611643278636;
            Mon, 25 Jan 2021 22:41:18 -0800 (PST)
    ARC-Seal: i=1; a=rsa-sha256; t=1611643278; cv=none;
            d=google.com; s=arc-20160816;
            b=hedJHzoAUpL4fSk43IZn1a4IxMtoAw3SxCmqyefMYowCr5P8cUwV6ZZPNCjSjQXlXe
             5NtMZQ5klqjPo2Pt7XZbK2X9DZfKIfqsZFw2IoGm1/q9FiPvXlv/Ob7s7WL9l7Do+4y0
             jRlfqFJ7RXwZaTKVUJk5FjyxR+PAsMTerOHzbGZBb5PuWscS+kRzwJ+8ktN/vm7E9C6/
             4md9RAKtLW3wpnsHarorYjo0sz/x1hqLUSK7gvqukXo9QCVwdQOs4h1lQ9G3LZMT5QMU
             kvBZXstcDfuwQBI99LIhs0RsiylE8r0qU0N39gI0IMupEXV7oQxAVGofic2dRgAP1jUe
             lgAA==
    ARC-Message-Signature: i=1; a=rsa-sha256; c=relaxed/relaxed; d=google.com; s=arc-20160816;
            h=date:message-id:mime-version:reply-to:errors-to:importance:from
             :subject:to;
            bh=GfMK2s9MDbqBDZeyMDCQoZLpa7Z72oNds1X0SgpqoDs=;
            b=VlLJrpR1Dzc0LUdlnU4WvAn9c2tV54CNGDtba7AyTQmRXWjoPzpad25jlZ5eOt6OdJ
             bvqSxiY0ovvAiSfUIPkcsGcPXnJyd8RfaG0WTJXOCcKwQh0dE2pxhEcok5GCkAtVQTqd
             Ebjj4vKG1/+e5E5KVan5X/KAKDJ1EWxpJnpB9YLW1Fn07Lm/xAVpmfoFo8xw7xc82Urr
             mXbeSoIf1E5/SOYr9Y/wvQa0X/fZpx3hXqgalEdw4Dq4JCUfldzI9x1wI+F7ckiCneci
             GWDcoNBZCiE6T8DvVPNbDK4KZap03JE62nfph6zUKm8NfYorfQTt3GVbr/iKxEq2G5WN
             V1cw==
             ARC-Authentication-Results: i=1; mx.google.com;
           spf=fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) smtp.mailfrom=billjobs@microapple.com
    Return-Path: <billjobs@microapple.com>
    Received: from localhost (emkei.cz. [93.99.104.210])
            by mx.google.com with ESMTPS id s16si170171wmj.176.2021.01.25.22.41.18
            for <themajoronearth@gmail.com>
            (version=TLS1_2 cipher=ECDHE-ECDSA-CHACHA20-POLY1305 bits=256/256);
            Mon, 25 Jan 2021 22:41:18 -0800 (PST)
    Received-SPF: fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) client-ip=93.99.104.210;
    Authentication-Results: mx.google.com;
           spf=fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) smtp.mailfrom=billjobs@microapple.com
    Received: by localhost (Postfix, from userid 33)
    	id 1993E221F8; Tue, 26 Jan 2021 01:41:18 -0500 (EST)
    To: themajoronearth@gmail.com
    Subject: A Hope to CoCanDa
    From: "Bill" <billjobs@microapple.com>
    X-Priority: 3 (Normal)
    Importance: Normal
    Errors-To: billjobs@microapple.com
    Reply-To: negeja3921@pashter.com
    MIME-version: 1.0
    Content-Type: multipart/mixed; boundary=BOUND_600FB98E0DCEE8.49207210
    Message-Id: <20210126064118.1993E221F8@localhost>
    Date: Tue, 26 Jan 2021 01:41:18 -0500 (EST)


### ✉️Breakdown:

- **Delivered-To:** `themajoronearth@gmail.com` — final delivery address.
- **Received (Google):** Email was accepted by Gmail's internal SMTP server on `25 Jan 2021 at 10:41 PM PST`.
- **ARC-Seal & ARC-Message-Signature:** Indicates Google's email authentication process. The field `cv=none` suggests that this email did not come with a valid authentication chain, which reduces trust.
- **Subject:** `A Hope to CoCanDa`  Indicates a scam-style story intended to grab attention.
- **From:** `"Bill" <billjobs@microapple.com>`  Spoofed email address using a fake domain to appear trustworthy.
- **Errors-To:** `billjobs@microapple.com` Bounce emails return to spoofed address — attacker controlled.
- **Reply-To:** `negeja3921@pashter.com` Replies redirected to attacker’s own mailbox, not the original sender.
- **Content-Type:** `multipart/mixed`  Confirms presence of attachment, which could contain malware or scam document.
- **Message-ID:** `<...@localhost>`  Message generated from a local system instead of a real email provider — a strong sign of spoofing.


## Authentication & Spoofing Proof
        ARC-Authentication-Results: i=1; mx.google.com;
           spf=fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) smtp.mailfrom=billjobs@microapple.com
    Return-Path: <billjobs@microapple.com>
    Received: from localhost (emkei.cz. [93.99.104.210])
            by mx.google.com with ESMTPS id s16si170171wmj.176.2021.01.25.22.41.18
            for <themajoronearth@gmail.com>
            (version=TLS1_2 cipher=ECDHE-ECDSA-CHACHA20-POLY1305 bits=256/256);
            Mon, 25 Jan 2021 22:41:18 -0800 (PST)
    Received-SPF: fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) client-ip=93.99.104.210;
    Authentication-Results: mx.google.com;
           spf=fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210 as permitted sender) smtp.mailfrom=billjobs@microapple.com
    Received: by localhost (Postfix, from userid 33)
    	id 1993E221F8; Tue, 26 Jan 2021 01:41:18 -0500 (EST)
- **SPF Fail:**  spf=fail (google.com: domain of billjobs@microapple.com does not designate 93.99.104.210...) The SPF record for the sender domain (`microapple.com`) does not authorize this IP to send mail. ***Strong proof of spoofing.***
- **Return-Path:** billjobs@microapple.com (Shows spoofed sender email. Bounce messages also go to a fake domain.)
- **Mail Origin (Received):**  from emkei.cz. [93.99.104.210] The email originated from ***emkei.cz***, a known spoofing service. This clearly shows that the email was forged using a public spoofing tool.
- **Authentication-Results:**  spf=fail ...   Gmail failed to authenticate the sender. This marks the email as ***not trusted***.
- **Postfix via localhost:**  The email was crafted and sent via local server setup — ***not an official provider like Gmail, Outlook, etc.***

## 📎 Attachment Header Analysis
### The following headers in the email confirm the presence of a suspicious attachment:
        Content-Type: application/pdf; name="PuzzleToCoCanDa.pdf"
        Content-Transfer-Encoding: base64
        Content-Disposition: attachment; filename="PuzzleToCoCanDa.pdf"

This header confirms that a suspicious PDF file named PuzzleToCoCanDa.pdf is attached. Since PDF files are commonly used to hide phishing forms or malware, this is a red flag. The attachment is base64-encoded, making it difficult to inspect its contents without decoding. This is often used to hide malicious payloads.The PDF is attached directly as a downloadable file, further confirming that the attacker wants the user to open it manually — a common phishing method.

⚠️ **Conclusion:** The attachment poses a high risk and should not be opened without sandbox or antivirus scanning.
