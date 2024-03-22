# Emlog Stored Cross-Site Scripting(XSS)

## Description

The client lacks proper validation when storing user input, resulting in a stored xss vulnerability.

## Vendor Homepage

```
https://www.emlog.net/
https://github.com/emlog/emlog
```

## Proof of Concept

1. Install emlog and log in as administrator.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222017415.png)

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222019172.png)

2. In the left navigation bar, enter the "微语" function and enter the payload:

```
<script>alert(document.cookie)</script>
```

Then click “发布” botton.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222021590.png)

3. Add "微语" at "外观"-"边栏".

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222028608.png)

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222029901.png)

4. All users now will trigger the attack code and a pop-up window when they enter the homepage of the website.

![](https://cdn.jsdelivr.net/gh/Cey1anze/Blog_Images@main/pic/202403222031771.png)
