# JetBrains TeamCity Server

JetBrains TeamCity Server, image is based on the Alpine base image with 0 vulnerabilities.

## Current Docker image (~1.75GB)

Security scanning using Clair
```
clair-scanner secureimages/teamcity-server:2020.2.2-alpine-3.13.2
2021/02/19 21:46:23 [INFO] ▶ Start clair-scanner
2021/02/19 21:46:50 [INFO] ▶ Server listening on port 9279
2021/02/19 21:46:50 [INFO] ▶ Analyzing b73bac2fe5a7b9d1abcbf0138798281e20b11e59b4605b104d38e914fa35b4d2
2021/02/19 21:46:57 [INFO] ▶ Analyzing e2ff1d1eeaf7ea1c2309db06d13a0b418a442e386d8bb960509bbdd64e54a71d
2021/02/19 21:46:57 [INFO] ▶ Analyzing fd901eddc73bbaea7ba55daaf51822cc146f4a5fcbce610e841e3f91f5ca6573
2021/02/19 21:46:58 [INFO] ▶ Analyzing 411a88dbba7d6775f5229a5a0e7d0537d9d177d6f01704dcf6bd297f4d6d94c6
2021/02/19 21:46:58 [INFO] ▶ Analyzing 9c12c8a9a5fb211e5780037daeefe754bf1d0291d4727038888ec5bc5d787378
2021/02/19 21:46:58 [WARN] ▶ Image [secureimages/teamcity-server:2020.2.2-alpine-3.13.2] contains 1 total vulnerabilities
2021/02/19 21:46:58 [ERRO] ▶ Image [secureimages/teamcity-server:2020.2.2-alpine-3.13.2] contains 1 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress secureimages/teamcity-server:2020.2.2-alpine-3.13.2
2021-02-19T21:48:02.320Z        INFO    Need to update DB
2021-02-19T21:48:02.321Z        INFO    Downloading DB...
2021-02-19T21:48:35.779Z        INFO    Detecting Alpine vulnerabilities...
2021-02-19T21:48:36.315Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

secureimages/teamcity-server:2020.2.2-alpine-3.13.2 (alpine 3.13.2)
===================================================================
Total: 0 (UNKNOWN: 0, LOW: 0, MEDIUM: 0, HIGH: 0, CRITICAL: 0)
```

## Official Docker image (~2.11GB)

[https://hub.docker.com/r/jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)
```
docker pull jetbrains/teamcity-server:2020.2.2
```

Security scanning using Clair
```
clair-scanner jetbrains/teamcity-server:2020.2.2
2021/02/19 21:48:56 [INFO] ▶ Start clair-scanner
2021/02/19 21:49:52 [INFO] ▶ Server listening on port 9279
2021/02/19 21:49:52 [INFO] ▶ Analyzing 2aade13603488c2c20ed3b6d742867cc8ce6b6dfa6f2eaff27799f1b6596835d
2021/02/19 21:49:53 [INFO] ▶ Analyzing cdec4b02a479c3dae4af73d15dfb2afff354cfeb3b9017f69d567920c629ee29
2021/02/19 21:49:53 [INFO] ▶ Analyzing 138ea95583e2a6c484dbf3d9d6994c096efca7f9bd07176dccae887494b857bb
2021/02/19 21:49:53 [INFO] ▶ Analyzing 45058af4b1894709a987bcf64c6fa147ee68300a4b8af468d32385d54061c4cf
2021/02/19 21:49:53 [INFO] ▶ Analyzing ce4659abd634fe537f8a5ae186ca31a77d47e2af738e7b3fecfb0b5b0ffcc9fc
2021/02/19 21:49:53 [INFO] ▶ Analyzing 162e72086849caa714181dcb385ae80ca744a23c8401dcd321df24657ca8de74
2021/02/19 21:49:53 [INFO] ▶ Analyzing d3cacba9f2d4b35e219e4d6d83bf271b318231c4f3267edc82911887cd99547c
2021/02/19 21:49:53 [INFO] ▶ Analyzing 1f01f6cc58a0ee9941ace124199171d688cb91847f93bc308702b08416babd6d
2021/02/19 21:49:53 [INFO] ▶ Analyzing 0154235c9c9725adf8492bd55e637bf8ce51130866d5535d68f05bd6648587c7
2021/02/19 21:49:53 [INFO] ▶ Analyzing e75673c4d57a7f03bb9ac567907ab44dcc3f4e054c47f48776e1f4847b6806b9
2021/02/19 21:49:53 [INFO] ▶ Analyzing e97158806c3882e1b2c0f168b200fe90c366a4d57b395bf85d7c4a8b1087e4e5
2021/02/19 21:49:53 [INFO] ▶ Analyzing fff024a5926288d471e2de288b2a50eb390050d327073ce10cf5623f2c8073a3
2021/02/19 21:49:53 [INFO] ▶ Analyzing 003538d001bf226d9bf7b8ff71940fb400973fbdc07e1a28f1b34b09cbb488dd
2021/02/19 21:49:55 [INFO] ▶ Analyzing 5e487bf9ff1fd70603da038f8015e2f4a19a9d30eeb4500e473ddd1518654e28
2021/02/19 21:49:55 [WARN] ▶ Image [jetbrains/teamcity-server:2020.2.2] contains 42 total vulnerabilities
2021/02/19 21:49:55 [ERRO] ▶ Image [jetbrains/teamcity-server:2020.2.2] contains 42 unapproved vulnerabilities
```

Security scanning using Trivy
```
docker run --rm -v /var/run/docker.sock:/var/run/docker.sock:ro aquasec/trivy:0.16.0 --no-progress jetbrains/teamcity-server:2020.2.2
2021-02-19T21:49:57.715Z        INFO    Need to update DB
2021-02-19T21:49:57.715Z        INFO    Downloading DB...
2021-02-19T21:50:56.194Z        INFO    Detecting Ubuntu vulnerabilities...
2021-02-19T21:50:56.201Z        INFO    Trivy skips scanning programming language libraries because no supported file was detected

jetbrains/teamcity-server:2020.2.2 (ubuntu 20.04)
=================================================
Total: 70 (UNKNOWN: 0, LOW: 43, MEDIUM: 27, HIGH: 0, CRITICAL: 0)
```
