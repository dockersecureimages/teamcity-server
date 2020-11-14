# JetBrains TeamCity Server

JetBrains TeamCity Server, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~1.61GB)

Security scanning using Clair
```
clair-scanner secureimages/teamcity-server:2020.1.5-alpine-3.12.1
2020/11/14 16:40:22 [INFO] ▶ Start clair-scanner
2020/11/14 16:40:46 [INFO] ▶ Server listening on port 9279
2020/11/14 16:40:46 [INFO] ▶ Analyzing ff72598b05f57e6f83d56b858ba9783796e99aea2dcef391b3fa688c1e077ae5
2020/11/14 16:40:46 [INFO] ▶ Analyzing e4782f3316d3f755e0d8598ec15e75b4ac4c021dae5b1b38cee3d859738abe57
2020/11/14 16:40:47 [INFO] ▶ Analyzing f0d6bc2ccfd9360524ae0e58960f41d324da1a297b6f1567fbfa24ec8858fc93
2020/11/14 16:40:49 [INFO] ▶ Analyzing 86007982779ed4a9a767ce7a7ccd58161e24ae891c507a03aeb2fb29d6d37f56
2020/11/14 16:40:49 [INFO] ▶ Analyzing 0b46c55f4d829f6806428d4203a47eee6368735f2054128474453f3d1e2931b0
2020/11/14 16:40:49 [INFO] ▶ Image [secureimages/teamcity-server:2020.1.5-alpine-3.12.1] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.12.0 --no-progress secureimages/teamcity-server:2020.1.5-alpine-3.12.1
2020-11-14T16:40:51.819Z        INFO    Need to update DB
2020-11-14T16:40:51.819Z        INFO    Downloading DB...
2020-11-14T16:41:27.996Z        INFO    Detecting Alpine vulnerabilities...

secureimages/teamcity-server:2020.1.5-alpine-3.12.1 (alpine 3.12.1)
===================================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~2.01GB)

[https://hub.docker.com/r/jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)
```
docker pull jetbrains/teamcity-server:2020.1.5
```

Security scanning using Clair
```
clair-scanner jetbrains/teamcity-server:2020.1.5
2020/11/14 16:42:10 [INFO] ▶ Start clair-scanner
2020/11/14 16:42:51 [INFO] ▶ Server listening on port 9279
2020/11/14 16:42:51 [INFO] ▶ Analyzing 8bf067b107a6f7444876e33c6ed85652355f679ac98ebab97ab3ebad63f0dff3
2020/11/14 16:42:56 [INFO] ▶ Analyzing 468327b5cd7ce539db695bd0ef05dae8a4ff77b02870a8e823ed74dedad4bd55
2020/11/14 16:42:56 [INFO] ▶ Analyzing 6cf145843a8d3af29f9b328595994e1487c110c5adcecc8d7125505cbea1b5b7
2020/11/14 16:42:56 [INFO] ▶ Analyzing 69d572705fc23879ba50fcbc772b8327e950053a4e95d3f2f7882b28d7412eb6
2020/11/14 16:42:56 [INFO] ▶ Analyzing df8c22a7b04621b15e79f06fd54a03909d5211d46b122b0402477daedcca17b8
2020/11/14 16:42:56 [INFO] ▶ Analyzing 4acc603a8404e1f8aa9333918a6b7abb9f5bf298716bd41548cc66386dea80c3
2020/11/14 16:42:56 [INFO] ▶ Analyzing 703c9a0c1d595792a95310444538346b003139dcc58bd46c6e10c9e5e15bfe61
2020/11/14 16:42:57 [INFO] ▶ Analyzing fef1178b235ae7c8f6946f170bf3b148b54e977d4fed74ba4e44157591654691
2020/11/14 16:42:57 [INFO] ▶ Analyzing a064364aadf44c8391c4e2ac25a56b575d266c0a9fd37d403cc6ee98515d2cf6
2020/11/14 16:42:57 [INFO] ▶ Analyzing d63b4a1b12b80f461c3812cdbdba1aad263a84aaec99d2cc638ba3a4fbdb92b9
2020/11/14 16:42:57 [INFO] ▶ Analyzing e1e0ee283d5707d6dfacff6f8da9ad2ce56602b741f38d54fbee9a0c858e32e2
2020/11/14 16:42:57 [INFO] ▶ Analyzing f4c7840fe07626c7a7d362bffb6b1ac4475a376ed0fd37b44680e10c52a00c2b
2020/11/14 16:42:58 [INFO] ▶ Analyzing e45d82b50062befa3c54f471a372c74dcb6568186a1be7f5c6f39dd3414354eb
2020/11/14 16:42:58 [WARN] ▶ Image [jetbrains/teamcity-server:2020.1.5] contains 43 total vulnerabilities
2020/11/14 16:42:58 [ERRO] ▶ Image [jetbrains/teamcity-server:2020.1.5] contains 43 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.12.0 --no-progress jetbrains/teamcity-server:2020.1.5
2020-11-14T16:43:00.188Z        INFO    Need to update DB
2020-11-14T16:43:00.188Z        INFO    Downloading DB...
2020-11-14T16:43:45.196Z        INFO    Detecting Ubuntu vulnerabilities...

jetbrains/teamcity-server:2020.1.5 (ubuntu 18.04)
=================================================
Total: 105 (UNKNOWN: 0, LOW: 78, MEDIUM: 26, HIGH: 1, CRITICAL: 0)
```
