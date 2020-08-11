# JetBrains TeamCity Server

JetBrains TeamCity Server, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~1.61GB)

Security scanning using Clair
```
clair-scanner secureimages/teamcity-server:2020.1.3-alpine-3.12.0
2020/08/11 17:49:54 [INFO] ▶ Start clair-scanner
2020/08/11 17:50:19 [INFO] ▶ Server listening on port 9279
2020/08/11 17:50:19 [INFO] ▶ Analyzing 31609b718dd2bed92b93b1ab00c0ff67419a3121d0144bef0dc6ca49718820a7
2020/08/11 17:50:19 [INFO] ▶ Analyzing ae342f42201f6279a710ef28a74aa6851cf88daffaf756f5515a9f50478c3226
2020/08/11 17:50:20 [INFO] ▶ Analyzing 5aab9f28c3a926864fc4d4e2fef4b43a94f9d213d9a4ca07ff83473aba4a1e73
2020/08/11 17:50:28 [INFO] ▶ Analyzing f8cb12b79a27aabbe0c307a32b5f6ebdd364ef82a9f0bbf2d2d9b059f968b800
2020/08/11 17:50:28 [INFO] ▶ Analyzing 5a5d1a1005303ac6bb25c0aaceb9b352d1be0a555b3688c34b1d3e1ede8927dd
2020/08/11 17:50:28 [INFO] ▶ Image [secureimages/teamcity-server:2020.1.3-alpine-3.12.0] contains NO unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.2 --no-progress secureimages/teamcity-server:2020.1.3-alpine-3.12.0
2020-08-11T17:50:30.688Z        INFO    Need to update DB
2020-08-11T17:50:30.688Z        INFO    Downloading DB...
2020-08-11T17:51:18.316Z        INFO    Detecting Alpine vulnerabilities...

secureimages/teamcity-server:2020.1.3-alpine-3.12.0 (alpine 3.12.0)
===================================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~2.01GB)

[https://hub.docker.com/r/jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)
```
docker pull jetbrains/teamcity-server:2020.1.3
```

Security scanning using Clair
```
clair-scanner jetbrains/teamcity-server:2020.1.3
2020/08/11 17:51:36 [INFO] ▶ Start clair-scanner
2020/08/11 17:52:30 [INFO] ▶ Server listening on port 9279
2020/08/11 17:52:30 [INFO] ▶ Analyzing 304740117a5a0c15c8ea43b7291479207b357b9fc08cc47a5e4a357f5e9a1768
2020/08/11 17:52:30 [INFO] ▶ Analyzing e07cf37ea90b5bbca2de1ac92fdaf18b135b6698351fc016ccdf957b14da40a4
2020/08/11 17:52:30 [INFO] ▶ Analyzing 3f2b9e84725f90338cdbeb1327d0b031a9c6eea513285b4645b7a62ff2457a07
2020/08/11 17:52:30 [INFO] ▶ Analyzing 58a62b8d255ff4ec9d9f893d106cf3927326ce75c0a97fc29e78b05f41707b51
2020/08/11 17:52:30 [INFO] ▶ Analyzing 7f3a7bb22ad918d22c2aed7b1134eb898e684b01225849347339bfbb12820be8
2020/08/11 17:52:30 [INFO] ▶ Analyzing eb91e083aa26899ab9c9b6a786dabe7b41eccd3af815e4c5ebe5db09f54950ed
2020/08/11 17:52:30 [INFO] ▶ Analyzing de68d322585d2ce70c81e837c580496075fa4d3101773d65f40d26cfc90ff7ed
2020/08/11 17:52:30 [INFO] ▶ Analyzing abeaf42ea6ae043cd264aa162d116a6853333b866e1b2ed73c75382c5b7209d4
2020/08/11 17:52:31 [INFO] ▶ Analyzing 6caf461576637807e8d55f2c02272744577119dc7e14ca5c08fd50d04c4cc534
2020/08/11 17:52:31 [INFO] ▶ Analyzing 5e2cdf203021689a9d82a9c5d99634861249f8fa8885b4dfc54e9961df1533ae
2020/08/11 17:52:31 [INFO] ▶ Analyzing bfe1c9ef4f1942bd3d035a97bd5823a6f2604754bce1d48207df503fcc9c7c0e
2020/08/11 17:52:31 [INFO] ▶ Analyzing ffd6f81255c2132fff825f88e662337ca7a60ae7a1653ddc1995b391575f03c6
2020/08/11 17:52:31 [INFO] ▶ Analyzing e0f55730395f84193b4b2b3ce4f7b0ac5691e9c9bf65f33446bc92c4825497ae
2020/08/11 17:52:32 [INFO] ▶ Analyzing 7efdf0b6709fb23bf16d55deb31a598bb00a74aba7d31995d06a6f8101c83883
2020/08/11 17:52:32 [WARN] ▶ Image [jetbrains/teamcity-server:2020.1.3] contains 47 total vulnerabilities
2020/08/11 17:52:32 [ERRO] ▶ Image [jetbrains/teamcity-server:2020.1.3] contains 47 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.10.2 --no-progress jetbrains/teamcity-server:2020.1.3
2020-08-11T17:52:34.036Z        INFO    Need to update DB
2020-08-11T17:52:34.036Z        INFO    Downloading DB...
2020-08-11T17:53:32.224Z        INFO    Detecting Ubuntu vulnerabilities...

jetbrains/teamcity-server:2020.1.3 (ubuntu 18.04)
=================================================
Total: 113 (UNKNOWN: 0, LOW: 95, MEDIUM: 18, HIGH: 0, CRITICAL: 0)
```
