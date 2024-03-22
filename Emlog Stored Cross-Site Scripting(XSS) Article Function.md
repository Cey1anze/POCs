---
title: Emlog Stored Cross-Site Scripting(XSS)-article function
date: 2024-03-22 20:35:52
categories:
- 网络安全
tags: [XSS,OWASP-TOP10]
---

# Emlog Stored Cross-Site Scripting(XSS)

## Description

The client lacks proper validation when storing user input, resulting in a stored xss vulnerability.

## Vendor Homepage

```
https://www.emlog.net/
https://github.com/emlog/emlog
```

## Proof of Concept

1. Register and log in as administrator.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222128072.png)

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222132670.png)

2. Click "发新文章" on Personal Page.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222132818.png)

3. Input payload：

```
![1](1"><script>alert('xss')</script><img src=")
```

Then click "立即发布" botton.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222129409.png)

4. All users now will trigger the attack code and a pop-up window when they enter the homepage of the website.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222130636.png)

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222135818.png)
