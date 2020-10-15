# JetBrains TeamCity Server

JetBrains TeamCity Server, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~1.61GB)

Security scanning using Clair
```
clair-scanner secureimages/teamcity-server:2020.1.5-alpine-3.12.0
2020/10/15 18:49:19 [INFO] ▶ Start clair-scanner
2020/10/15 18:50:16 [INFO] ▶ Server listening on port 9279
2020/10/15 18:50:16 [INFO] ▶ Analyzing 31609b718dd2bed92b93b1ab00c0ff67419a3121d0144bef0dc6ca49718820a7
2020/10/15 18:50:16 [INFO] ▶ Analyzing 5ffa0dfc1cac3c7a7e8f8b8d715b48c0aa2465afec52accc4de6a412f259e212
2020/10/15 18:50:17 [INFO] ▶ Analyzing 041b36762ed34236b5f21d7ce5a7cd818b006ab6de0fd1b66c90fd50b8aba4cf
2020/10/15 18:50:19 [INFO] ▶ Analyzing a4aea05ee5dc196d3cc3b10143d69b1f18420340202fb5b13c768e289729fb81
2020/10/15 18:50:19 [INFO] ▶ Analyzing 283df1c0f8bd36d59408cdafb823888d4b2f45eb24c17568f11c19b22e766491
2020/10/15 18:50:19 [INFO] ▶ Image [secureimages/teamcity-server:2020.1.5-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.12.0 --no-progress secureimages/teamcity-server:2020.1.5-alpine-3.12.0
2020-10-15T18:47:53.799Z        INFO    Need to update DB
2020-10-15T18:47:53.799Z        INFO    Downloading DB...
2020-10-15T18:50:20.457Z        INFO    Detecting Alpine vulnerabilities...

secureimages/teamcity-server:2020.1.5-alpine-3.12.0 (alpine 3.12.0)
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
2020/10/15 18:51:00 [INFO] ▶ Start clair-scanner
2020/10/15 18:51:39 [INFO] ▶ Server listening on port 9279
2020/10/15 18:51:39 [INFO] ▶ Analyzing 8bf067b107a6f7444876e33c6ed85652355f679ac98ebab97ab3ebad63f0dff3
2020/10/15 18:51:43 [INFO] ▶ Analyzing 468327b5cd7ce539db695bd0ef05dae8a4ff77b02870a8e823ed74dedad4bd55
2020/10/15 18:51:43 [INFO] ▶ Analyzing 6cf145843a8d3af29f9b328595994e1487c110c5adcecc8d7125505cbea1b5b7
2020/10/15 18:51:43 [INFO] ▶ Analyzing 69d572705fc23879ba50fcbc772b8327e950053a4e95d3f2f7882b28d7412eb6
2020/10/15 18:51:44 [INFO] ▶ Analyzing df8c22a7b04621b15e79f06fd54a03909d5211d46b122b0402477daedcca17b8
2020/10/15 18:51:44 [INFO] ▶ Analyzing 4acc603a8404e1f8aa9333918a6b7abb9f5bf298716bd41548cc66386dea80c3
2020/10/15 18:51:44 [INFO] ▶ Analyzing 703c9a0c1d595792a95310444538346b003139dcc58bd46c6e10c9e5e15bfe61
2020/10/15 18:51:44 [INFO] ▶ Analyzing fef1178b235ae7c8f6946f170bf3b148b54e977d4fed74ba4e44157591654691
2020/10/15 18:51:44 [INFO] ▶ Analyzing a064364aadf44c8391c4e2ac25a56b575d266c0a9fd37d403cc6ee98515d2cf6
2020/10/15 18:51:44 [INFO] ▶ Analyzing d63b4a1b12b80f461c3812cdbdba1aad263a84aaec99d2cc638ba3a4fbdb92b9
2020/10/15 18:51:44 [INFO] ▶ Analyzing e1e0ee283d5707d6dfacff6f8da9ad2ce56602b741f38d54fbee9a0c858e32e2
2020/10/15 18:51:44 [INFO] ▶ Analyzing f4c7840fe07626c7a7d362bffb6b1ac4475a376ed0fd37b44680e10c52a00c2b
2020/10/15 18:51:45 [INFO] ▶ Analyzing e45d82b50062befa3c54f471a372c74dcb6568186a1be7f5c6f39dd3414354eb
2020/10/15 18:51:45 [WARN] ▶ Image [jetbrains/teamcity-server:2020.1.5] contains 43 total vulnerabilities
2020/10/15 18:51:45 [ERRO] ▶ Image [jetbrains/teamcity-server:2020.1.5] contains 43 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.12.0 --no-progress jetbrains/teamcity-server:2020.1.5
2020-10-15T18:51:47.652Z        INFO    Need to update DB
2020-10-15T18:51:47.652Z        INFO    Downloading DB...
2020-10-15T18:53:25.632Z        INFO    Detecting Ubuntu vulnerabilities...

jetbrains/teamcity-server:2020.1.5 (ubuntu 18.04)
=================================================
Total: 99 (UNKNOWN: 0, LOW: 83, MEDIUM: 16, HIGH: 0, CRITICAL: 0)
```
