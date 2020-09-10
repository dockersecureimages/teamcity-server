# JetBrains TeamCity Server

JetBrains TeamCity Server, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~1.61GB)

Security scanning using Clair
```
clair-scanner secureimages/teamcity-server:2020.1.4-alpine-3.12.0
2020/09/10 18:05:41 [INFO] ▶ Start clair-scanner
2020/09/10 18:06:07 [INFO] ▶ Server listening on port 9279
2020/09/10 18:06:07 [INFO] ▶ Analyzing 31609b718dd2bed92b93b1ab00c0ff67419a3121d0144bef0dc6ca49718820a7
2020/09/10 18:06:10 [INFO] ▶ Analyzing 7983ae30d1f514ecdc487001403bf0e13c003d8093f295361d1f6be55cfb461f
2020/09/10 18:06:12 [INFO] ▶ Analyzing 61f268f80c284d772cbab039768d489bd4995fda6ebcb19b669246e5614c06b1
2020/09/10 18:06:18 [INFO] ▶ Analyzing c004d793274935b861ef87ac72e4f4112100e0a3581b0c0302318ba30c622ea4
2020/09/10 18:06:18 [INFO] ▶ Analyzing 67a7664aa97c9f18c1d6ca05ff727b7749f746b87407543809d89bf87d04ce1b
2020/09/10 18:06:18 [INFO] ▶ Image [secureimages/teamcity-server:2020.1.4-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress secureimages/teamcity-server:2020.1.4-alpine-3.12.0
2020-09-10T18:07:07.441Z        INFO    Need to update DB
2020-09-10T18:07:07.441Z        INFO    Downloading DB...
2020-09-10T18:07:51.485Z        INFO    Detecting Alpine vulnerabilities...

secureimages/teamcity-server:2020.1.4-alpine-3.12.0 (alpine 3.12.0)
===================================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~2.01GB)

[https://hub.docker.com/r/jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)
```
docker pull jetbrains/teamcity-server:2020.1.4
```

Security scanning using Clair
```
clair-scanner jetbrains/teamcity-server:2020.1.4
2020/09/10 18:08:00 [INFO] ▶ Start clair-scanner
2020/09/10 18:08:44 [INFO] ▶ Server listening on port 9279
2020/09/10 18:08:44 [INFO] ▶ Analyzing c46312971b989857795a66c3a16a6c5ad3faf70f68a86374d05fc98271302d31
2020/09/10 18:08:48 [INFO] ▶ Analyzing d5daf2b531bb4b815a1be1530978615e27bbc862258d1fd287df43a3b662181a
2020/09/10 18:08:48 [INFO] ▶ Analyzing 989dbccc76e96e34b561b0eef7753f3134b58ab454b5b222a965ff87e25cf9fb
2020/09/10 18:08:48 [INFO] ▶ Analyzing 16191067d3bf92aa3d59d244f8b1e91d2c656cbe68304eaade0f4a7d0204648c
2020/09/10 18:08:48 [INFO] ▶ Analyzing 6ab9a7073395a341b616dc65d7564abde9302145fd7a81cb752dff90185bff64
2020/09/10 18:08:49 [INFO] ▶ Analyzing 19755023c12b4024276972d660da4b659031e54da7342d51ae95641b210a8cb6
2020/09/10 18:08:50 [INFO] ▶ Analyzing 186143fbdddcfc0404f128b63523afac0ab393024838c552616c4867a0048a0c
2020/09/10 18:08:50 [INFO] ▶ Analyzing 8c67475d48909e5b668782d7b79274fe58705eccce509a3d56075a58ea664fef
2020/09/10 18:08:50 [INFO] ▶ Analyzing 2721be29d0a99b93ea886cb92eb89e1f0ec525f2fef36d3fda18cc7e3e21f27f
2020/09/10 18:08:50 [INFO] ▶ Analyzing 6f5631dae7a47ecb68505e6e4b88482a9ff4b5cb4c07839f63caa87af6000491
2020/09/10 18:08:50 [INFO] ▶ Analyzing 0de7ebd0a9ea92aa3c2c2a7b632376a8904c33ff16df2781a2a8f8e1de8366c7
2020/09/10 18:08:50 [INFO] ▶ Analyzing f94a5aeb977855b00cf59f01f455e0d92d4289bc3c317649e72e52f77091cb2f
2020/09/10 18:08:50 [INFO] ▶ Analyzing ce35558dde7633dec0ae9ee4d5297918852b83287184d82f8b382d96a9dfa5b9
2020/09/10 18:08:51 [INFO] ▶ Analyzing f02d59f2f52a886c1f62e6cf57453e0f5f8812cc9eb6ee358561e06c6cc1490e
2020/09/10 18:08:51 [WARN] ▶ Image [jetbrains/teamcity-server:2020.1.4] contains 46 total vulnerabilities
2020/09/10 18:08:51 [ERRO] ▶ Image [jetbrains/teamcity-server:2020.1.4] contains 46 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.11.0 --no-progress jetbrains/teamcity-server:2020.1.4
2020-09-10T18:10:45.588Z        INFO    Need to update DB
2020-09-10T18:10:45.589Z        INFO    Downloading DB...
2020-09-10T18:11:29.952Z        INFO    Detecting Ubuntu vulnerabilities...

jetbrains/teamcity-server:2020.1.4 (ubuntu 18.04)
=================================================
Total: 111 (UNKNOWN: 0, LOW: 95, MEDIUM: 16, HIGH: 0, CRITICAL: 0)
```
