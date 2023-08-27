- Exercise 1:
```
$> curl https://api.github.com/users/TammyTrinh1511
{
  "login": "TammyTrinh1511",
  "id": 68692769,
  "node_id": "MDQ6VXNlcjY4NjkyNzY5",
  "avatar_url": "https://avatars.githubusercontent.com/u/68692769?v=4",
  "gravatar_id": "",
  "url": "https://api.github.com/users/TammyTrinh1511",
  "html_url": "https://github.com/TammyTrinh1511",
  "followers_url": "https://api.github.com/users/TammyTrinh1511/followers",
  "following_url": "https://api.github.com/users/TammyTrinh1511/following{/other_user}",
  "gists_url": "https://api.github.com/users/TammyTrinh1511/gists{/gist_id}",
  "starred_url": "https://api.github.com/users/TammyTrinh1511/starred{/owner}{/repo}",
  "subscriptions_url": "https://api.github.com/users/TammyTrinh1511/subscriptions",
  "organizations_url": "https://api.github.com/users/TammyTrinh1511/orgs",
  "repos_url": "https://api.github.com/users/TammyTrinh1511/repos",
  "events_url": "https://api.github.com/users/TammyTrinh1511/events{/privacy}",
  "received_events_url": "https://api.github.com/users/TammyTrinh1511/received_events",
  "type": "User",
  "site_admin": false,
  "name": "Tammy Trinh",
  "company": null,
  "blog": "",
  "location": null,
  "email": null,
  "hireable": null,
  "bio": null,
  "twitter_username": null,
  "public_repos": 6,
  "public_gists": 0,
  "followers": 0,
  "following": 0,
  "created_at": "2020-07-23T11:52:19Z",
  "updated_at": "2023-08-26T10:48:49Z"
}

# I don't follow anyone
```
- Exercise 2: 
```
$> curl -s "https://api.github.com/search/repositories?q=user:TammyTrinh1511&sort=stars&per_page=1" | grep "stargazers_count"
      "stargazers_count": 0,
```
- Exercise 3
```
$> curl "https://api.github.com/repos/nodejs/node/languages"
{
  "JavaScript": 13282342,
  "C++": 4766766,
  "Python": 2355907,
  "C": 613336,
  "HTML": 163390,
  "Shell": 99227,
  "Makefile": 53723,
  "Batchfile": 41870,
  "Emacs Lisp": 14363,
  "Perl": 11715,
  "R": 8037,
  "TypeScript": 702,
  "Assembly": 157,
  "Dockerfile": 33
}

```
- Bonus Exercise 1: 
```
$> curl -i -H 'Authorization: token <ghp_hehe >' https://api.github.com/TammyTrinh1511
HTTP/2 401 
server: GitHub.com
date: Sun, 27 Aug 2023 16:06:35 GMT
content-type: application/json; charset=utf-8
content-length: 90
x-github-media-type: github.v3; format=json
x-ratelimit-limit: 60
x-ratelimit-remaining: 59
x-ratelimit-reset: 1693155995
x-ratelimit-used: 1
x-ratelimit-resource: core
access-control-expose-headers: ETag, Link, Location, Retry-After, X-GitHub-OTP, X-RateLimit-Limit, X-RateLimit-Remaining, X-RateLimit-Used, X-RateLimit-Resource, X-RateLimit-Reset, X-OAuth-Scopes, X-Accepted-OAuth-Scopes, X-Poll-Interval, X-GitHub-Media-Type, X-GitHub-SSO, X-GitHub-Request-Id, Deprecation, Sunset
access-control-allow-origin: *
strict-transport-security: max-age=31536000; includeSubdomains; preload
x-frame-options: deny
x-content-type-options: nosniff
x-xss-protection: 0
referrer-policy: origin-when-cross-origin, strict-origin-when-cross-origin
content-security-policy: default-src 'none'
vary: Accept-Encoding, Accept, X-Requested-With
x-github-request-id: 83CC:0AF1:1991F1:1AA50C:64EB748B

{
  "message": "Bad credentials",
  "documentation_url": "https://docs.github.com/rest"
}
```