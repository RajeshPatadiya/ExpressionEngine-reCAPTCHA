ExpressionEngine-reCAPTCHA
==========================

Replaces the built-in ExpressionEngine 2.x CAPTCHA with reCAPTCHA on member registration and comment forms.

## Installation

1. Copy the **recaptcha** folder to **../system/expressionengine/third_party**
2. Enable and configure the extension via **Add-Ons... Extensions**
3. Remove the hard-coded CAPTCHA input field from your member registration template (**../themes/profile_themes/[theme_name]/registration_form.html**) and any comment submission form templates so that the CAPTCHA's conditional block looks like:

```
{if captcha}
    {captcha}
{/if}
```

### F.A.Q.

#### Can I use reCAPTCHA with the Contact or Tell-a-Friend form?

Currently the Email module uses its own functions for creating the CAPTCHA, so only member registration and comment forms are supported at this time.

#### Can I use this with the MSM?

It should work as long as you use a Global key by ticking **Enable this key on all domains (global key)** when you create your reCAPTCHA key.

#### I keep getting "Unable to receive your comment at this time." when testing the comment submission form?

If you’re testing with the same comment text, EE is likely enforcing spam protection and/or throttling your post. Test with unique comments or adjust the settings at:

* Admin... Security and Session Preferences... Deny Duplicate Data
* Admin... Channel Administration... Channels... Comment Posting Preferences... Comment Re-submission Time Interval