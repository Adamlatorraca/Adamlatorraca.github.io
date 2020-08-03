---
layout: post
title:      "Protecting Your Apps"
date:       2020-08-03 00:32:27 +0000
permalink:  protecting_your_apps
---

## What is a CSRF Attack?

Put simply, a CSRF (or Cross-Site Request Forgery) attack allows a malicious actor to perform unwanted actions on a user who is authorized on an application. This could mean forcing a user to change the email their account is associated with, make posts that they didn't author, or even change the password associated with the account. That sounds pretty inconvienient, I mean think of the emails you'll need to send back and forth to support to get your account back! But what if your banking website is vulnerable to such an attack? If an attacker can author posts under your blog account, what is stopping them from being able to make transactions under your banking account? There is indeed an answer, but first, let's dive deeper on how a CSRF attack takes place.

### The Anatomy of a CSRF Attack

A web app that is vulnerable to a CSRF attack has 3 components: a relevent action, limited authorization, and predictable parameters. A relevent action is any action that an attacker can modify for their own benefit, such as an edit user action where a user can change their password or other log in information. Without a relevent action, an attacker doesn't really have anything to modify thus rendering the attack pointless. Limited authorization can come in many forms, but for a CSRF attack anything that is authorized only by session cookies can be vulnerable. If an app has further forms of authorization, the attacker would be stopped in their tracks. However, if session cookies are the only form of authorization, then once an attacker has established a forged session they can attack until the session closes or they close it themselves. Lastly, predictable parameters make forging HTML forms that much easier for an attacker. If an attacker knows what parameters they need to pass in to a form, then they can feed in exactly what is needed for the app to accept the malicious data.

### Playing Defense

Now that we know what a CSRF attack is and what makes for a vulnerable website, we're ready to defend against them. First, Ruby on Rails comes with forgery protection built in and can be enabled by adding the line 'protect_against_forgery' to the top of your application controller.

![](https://i.imgur.com/ILz1VQb.png)

This feature will automatically include CSRF authenticity tokens in the header of relevent actions to provide an unpredictable parameter that would be unobtainable by an attacker.

![](https://i.imgur.com/pM7HSrs.png)

Now an attacker is unable to forge an HTML form that can pass in an acceptable value for that parameter.

That was pretty easy, right? The Rails magic is here once again to save us! This leaves us one small issue though: what about third-party authentication? Don't worry, the rails community still has you covered.

### CSRF and Omniauth

Omniauth is a great tool for allowing users to sign in through third-party sites. It's fast, convenient, and secure. Well, pretty secure at least. One way to further ensure that users are safe from CSRF attacks is using the '[omniauth-rails_csrf_protection](https://github.com/cookpad/omniauth-rails_csrf_protection)' gem. As per the read-me, this little guy will mitigate the risk of a CSRF attack by: 1) Disabling access to the OAuth request phase using HTTP GET method, and 2) Insert a Rails CSRF token verifier at the before request phase.

Pretty sweet, right? Protecting users should be at the forefront of any web developer's mind and these tools should make the process that much easier!
