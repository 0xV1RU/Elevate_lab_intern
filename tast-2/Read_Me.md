# 🛡️ Phishing Email Analysis Report
## 🎯 Objective Objective: 
Identify phishing characteristics in a suspicious email sample.

## 🎯 Header Analysis
    
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


### ✉️Breakdown:

- **Delivered-To:** `themajoronearth@gmail.com` — final delivery address.
- **Received (Google):** Email was accepted by Gmail's internal SMTP server on `25 Jan 2021 at 10:41 PM PST`.
- **ARC-Seal & ARC-Message-Signature:** Indicates Google's email authentication process. The field `cv=none` suggests that this email did not come with a valid authentication chain, which reduces trust.
