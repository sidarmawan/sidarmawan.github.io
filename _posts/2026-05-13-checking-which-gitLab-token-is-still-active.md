---
layout: post
title: "Learning Note: Checking Which GitLab Token Is Still Active"
author: "Sidar"
categories:
    - Blog
tags:
    - GitLab
    - Linux
---
<p>While learning GitLab API testing, I ended up creating multiple personal access tokens for experiments and practice.</p>

<p>After a while, I forgot which token was still active and which one was no longer being used 😅</p>

<p>The confusing part is that GitLab only shows the token list from the dashboard, but it does not show the actual token value again after it is created. So when I wanted to test the API again, I had several old tokens saved in terminal history and notes, but no idea which one still worked.</p>

<p>Finally, I found a simple way to check whether a GitLab token is still valid or not.</p>

## Check GitLab Token Using curl

Command:

```bash
curl -s --header "PRIVATE-TOKEN: glpat-xxxxxxxxxxxxxxxx" \
https://gitlab.example.local/api/v4/user
```

> The URL and token are masked for security reasons.

If the token is still active, GitLab will return the user information in JSON format.

Example output:

```json
{
  "id": 104,
  "username": "automation_user",
  "name": "Automation User",
  "state": "active",
  "web_url": "https://gitlab.example.local/automation_user",
  "last_activity_on": "2026-05-13",
  "is_admin": true
}
```

If the token is invalid or expired, the response will usually look like this:

```json
{
  "message": "401 Unauthorized"
}
```

## What I Learned

From this small case, I realized that creating too many tokens without proper notes can become confusing later.

Now I try to:

- give tokens clear names
- remove unused tokens
- keep simple notes about where tokens are used

Even though this is a simple trick, using the `/api/v4/user` endpoint is very helpful for quickly checking whether a GitLab token is still active.

---

This is just my personal learning note so I do not forget how to verify GitLab tokens when I have too many tokens in the future.

