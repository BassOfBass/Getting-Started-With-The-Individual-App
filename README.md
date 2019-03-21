# GitGuardian Getting Started

<p align="center"> 
<img src="images/02_Logo_Dev_Quadri.png" alt="Image" width="60%" height="60%">
</p>

- [1. Introduction](#1-introduction)
  - [1.1. What is GitGuardian?](#11-what-is-gitguardian)
  - [1.2. Getting Started](#12-getting-started)
- [2. Deploy GitGuardian on your repos](#2-deploy-gitguardian-on-your-repos)
  - [2.1. Where to sign up?](#21-where-to-sign-up)
  - [2.2. What permissions does GitGuardian need?](#22-what-permissions-does-gitguardian-need)
  - [2.3. What's happening under the hood?](#23-whats-happening-under-the-hood)
- [3. Evaluate the risk](#3-evaluate-the-risk)
  - [3.1. Risk exposure](#31-risk-exposure)
  - [3.2. What should you do in case of a leak?](#32-what-should-you-do-in-case-of-a-leak)
  - [3.3. What should you do to reduce the risks of leaking a secret?](#33-what-should-you-do-to-reduce-the-risks-of-leaking-a-secret)
  - [3.4. Protect against most critical threats](#34-protect-against-most-critical-threats)
- [4. How does GitGuardian work?](#4-how-does-gitguardian-work)
  - [4.1. Monitoring](#41-monitoring)
    - [4.1.1. Dashboard](#411-dashboard)
    - [4.1.2. Owned repos](#412-owned-repos)
    - [4.1.3. Collaborating repos](#413-collaborating-repos)
  - [4.2. Detection](#42-detection)
  - [4.3. Alerting](#43-alerting)
- [5. Test it live!](#5-test-it-live)
- [6. About GitGuardian](#6-about-gitguardian)

# 1. Introduction

## 1.1. What is GitGuardian?

- GitGuardian, or GG, is a **developers-first cybersecurity company** that detects highly sensitive secrets in source code, public and private!
- As an individual developer, you can deploy our web app to **start monitoring in real-time your public commits for API keys, database credentials, certificates, ...**
- It takes just a **few minutes** to integrate and get started!

<p align="center"> 
<img src="images/WebApp.png" alt="Image" width="70%" height="70%">
</p>
       
## 1.2. Getting Started

This guided tour walks you through what GitGuardian can do once linked to your GitHub account:

- **Protect your credentials from being stolen** by detecting API keys, database connection strings, certificates, etc. leaked in source code.
- **Proactively prevent hackers from penetrating your systems** by alerting you in real-time. Our 4-second reaction time makes us a proactive solution rather than a reactive one!
- **Give you peace of mind** by monitoring your repositories. Because if you can be sure that nothing bad happened today on your GitHub, that really means something!

# 2. Deploy GitGuardian on your repos

## 2.1. Where to sign up?

Sign up [there](https://www.gitguardian.com/developer), this is free for individual developers! We'll be up and running in a minute.

## 2.2. What permissions does GitGuardian need?

<p align="center"> 
<img src="images/SignUp.png" alt="Image" width="30%" height="30%">
</p>
     
GitGuardian needs some permissions to be fully functional:

| Name of the permission          | GitHub associated [scope](https://developer.github.com/apps/building-oauth-apps/understanding-scopes-for-oauth-apps/) | Why GitGuardian needs it                                                                                                                                              |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Email addresses (read only)** | 'user:email'                                                                                                          | We synchronize your email addresses so we can email you our alerts. You can later configure your email addresses in our app if you'd like to override that.           |
| **Public repositories**         | 'public_repo'                                                                                                         | Grants read and write access to code for public repositories. We need this level of access because GitHub does not provide a read only scope for public repositories. |

<p align="center"> 
<img src="images/Permissions.png" alt="Image" width="70%" height="70%">
</p>

## 2.3. What's happening under the hood?

GitGuardian is installing [webhooks](https://developer.github.com/webhooks/) for us to be notified in real-time when you push code on GitHub.

# 3. Evaluate the risk

## 3.1. Risk exposure

- **We’ve all been there already: committing a key in source code** to run a few tests, then deleting the key so that the actual version of the source code looks clean, and pushing everything to GitHub later on forgetting about the old key. Or simply open sourcing files that shouldn’t be due to a misconfigured .gitignore or an audacious ‘git add .’ command.
- **It’s OK to make mistakes, and it’s a sound attitude not to feel invulnerable.** Recognizing that mistakes happen is the best way to show how much you care!
- Bots often scan GitHub in search of secret keys that can be abused for malicious attacks using [**GitHub Dorks**](https://github.com/techgaun/github-dorks) to find their targets.
- **GitGuardian is there to raise awareness among developers and get everyone covered!**

## 3.2. What should you do in case of a leak?

GitGuardian provides you with general advice as well as actionable items to walk you through the remediation procedure on our dedicated repository: [APISecurityBestPractices](https://github.com/GitGuardian/APISecurityBestPractices/blob/master/Leak%20Mitigation%20Checklist.md).

## 3.3. What should you do to reduce the risks of leaking a secret?

GitGuardian provides you with [good development practices](https://github.com/GitGuardian/APISecurityBestPractices/blob/master/Good%20development%20practices.md).

## 3.4. Protect against most critical threats

GitGuardian is focused on detecting vulnerabilities that could be highly detrimental to you, your career or your organization.

# 4. How does GitGuardian work?

The web application works in 3 steps:

<p align="center"> 
<img src="images/GG-steps.png" alt="Image" width="60%" height="60%">
</p>
           
## 4.1. Monitoring

### 4.1.1. Dashboard

**Quick view on your history with aggregated stats and timeline**

<p align="center"> 
<img src="images/feature1.png" alt="Image" width="60%" height="60%">
</p>
       
**Keep an eye on your security warnings**
  * Security warnings allow you to access your leaks and to get detailed information.
  * This section helps you to understand why a leak has happened and what you should do to remediate.  
 
 All keys are fake of course (take care!) :)
 
<p align="center"> 
<img src="images/feature3.png" alt="Image" width="60%" height="60%">
</p>
       
**But also on all your reported events**
  * This is where we log all the events that are related to your account. For example, you can push code on GitHub and check there that we properly scanned the associated commits, even if your commits don't contain any credential. Because the fact that GitGuardian did not detect any commit really does mean something for your security!
  * Every commit is scanned. Keep in mind that even if the actual version of your source code looks clean, a leak can still be in the git!
  * Be redirected to your commit by clicking on your commit SHA.
       
<p align="center"> 
<img src="images/feature4.png" alt="Image" width="60%" height="60%">
</p>
       
### 4.1.2. Owned repos

- Make sure that GG's [webhooks](https://developer.github.com/webhooks/) were properly installed on your repos thanks to the "real time protection activated" status. Webhooks allow us to be notified instantly the moment you push public code on GitHub.
- New commits will be automatically scanned when they are pushed.
- You can click on the "Scan" button to check your commits history (before our app was installed) for secrets.

<p align="center"> 
<img src="images/owned%20repos.png" alt="Image" width="70%" height="70%">
</p>
       
### 4.1.3. Collaborating repos

If you are collaborating on a repository, you can use the "Scan" button to check the commits history for secrets. However, real-time protection can only be enabled by the repository's owner. Invite the owner to subscribe to GG!

<p align="center"> 
<img src="images/Collaborating%20repos.png" alt="Image" width="70%" height="70%">
</p>
       
## 4.2. Detection

GitGuardian detectors use:

- **Entropy statistics** to find good candidates for credentials. Every API key is a high-entropy string, but the majority of high-entropy strings on GitHub aren't keys! With that many false positives, using entropy alone is definitely not doable!
- **Pattern matching** to find prefixed credentials.
- More sophisticated algorithms including **Machine Learning** techniques for others!

Here are two different types of keys to illustrate this: Amazon API keys all start with “AKIA” whereas the Digital Ocean tokens don’t show any patterns.

**Amazon examples**

```
(first id, secret pair)
AKIAEXAMPLE********A
cR6+LDX9q***************************

(second id, secret pair)
AKIAEXAMPLE2******A
q+Ar81dCb***************************
```

**Digital Ocean examples**

```
(first id, secret pair)
NLARY***************
MGYDzr******************************

(second id, secret pair)
4IWAU***************
UQDzr5******************************
```

## 4.3. Alerting

- Each public commit pushed to the platform will be scanned. The pusher is alerted in real-time by email of any leak.
- Emails can be configured in the settings page. We strongly advise to use multiple alerting emails. Email still is one of the best ways to deliver quickly human-readable content, but it is almost impossible to guarantee a 100% delivery rate. Using multiple alerting emails helps.

<p align="center"> 
<img src="images/SettingPanel.png" alt="Image" width="70%" height="70%">
</p>

# 5. Test it live!

1. **Commit a fake API Key**

You can use this fake SendGrid token and **change at least one character (without touching the 'SG.' prefix that characterizes SendGrid tokens)**:

```
fake_secret_sendgrid=SG.af7c6bMLRxSagExMsW8Hng.vaa_FWbgCcVdkXhDXXg23SWS4cT5RcRtClTcdIb2d3b
```

**If you don't change at least one character, this won't work!** Indeed, using this key as-is will not work because we implemented a caching system by key to make sure we don't alert multiple times when we detect the same secrets. The reason behind it is that when the same secret is found in multiple places on GitHub, it’s generally because it’s an example secret.

2. **GitGuardian to the rescue: check your email box**

Receive GG's email in your box a few seconds after you pushed!

3. **Check your dashboard**

Refresh your dashboard and verify the commit was scanned and the leak was reported there.

# 6. About GitGuardian

**Why has GitGuardian been founded?**  
First of all, GitGuardian is a product created by developers, for developers, with one mission, which is to **prevent secret sprawl**.

**Why the individual developers' app?**

There are three main priorities of the individual application:

- **Peace of mind**: Protecting developers and ensuring their career success. GG covers your back.
- **Time saving**: Recovering from data breaches is a tough process requiring a lot of time. Reduce the impact of data breaches and the number of critical incidents.
- **Awareness**: Raising awareness in the developers community about leaks and empowering developers with the right products and knowledge!

**Who's developing GitGuardian?**

A team of talented French :fr: engineers with a strong technical background. By the way, GitGuardian is also offering an enterprise version of public monitoring as well as private monitoring.

**More infos: https://gitguardian.com**
