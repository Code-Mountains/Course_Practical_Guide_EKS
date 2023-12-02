# A Practical Guide to EKS

In this repository you will find all the assets required for the course `A Practical Guide to Amazon EKS`, by A Cloud Guru.


## Bookstore application

This solution has been built for for explaining all the concepts in this course. It is complete enough for covering a real case of microservices running on EKS and integrating with other AWS Services.

> You can find in [here](_docs/api.md) the documentation of the APIs.



# Build each image first
```
$ cd renting-api/api/ 

$ docker build -t renting-api-image .
```

## OUTPUT 
$ docker build -t renting-api-image .
```
[+] Building 148.0s (11/11) FINISHED
 => [internal] load build definition from Dockerfile                                                                          0.0s
 => => transferring dockerfile: 283B                                                                                          0.0s
 => [internal] load .dockerignore                                                                                             0.0s
 => => transferring context: 2B                                                                                               0.0s
 => [internal] load metadata for docker.io/library/ruby:2.6.3                                                                 0.7s
 => [auth] library/ruby:pull token for registry-1.docker.io                                                                   0.0s
 => [1/5] FROM docker.io/library/ruby:2.6.3@sha256:358f16e92d0f66599103318f7a8528d449b0973fd89e46a1a5c47cec7479f09b           0.0s
 => [internal] load build context                                                                                             0.0s
 => => transferring context: 3.65kB                                                                                           0.0s
 => CACHED [2/5] WORKDIR /usr/src/app                                                                                         0.0s
 => CACHED [3/5] COPY Gemfile Gemfile.lock ./                                                                                 0.0s
 => [4/5] RUN bundle install                                                                                                145.4s
 => [5/5] COPY . .                                                                                                            0.1s
 => exporting to image                                                                                                        1.7s
 => => exporting layers                                                                                                       1.7s
 => => writing image sha256:9359280ad31cd84280a1b4c74e073e918ebe9e5d0b92d78368fa336c3c0c8d24                                  0.0s
 => => naming to docker.io/library/renting-api-image                                                                          0.0s
```

$ docker build -t inventory-api-image .
```
[+] Building 41.0s (11/11) FINISHED
 => [internal] load .dockerignore                                                                                             0.0s
 => => transferring context: 2B                                                                                               0.0s
 => [internal] load build definition from Dockerfile                                                                          0.0s
 => => transferring dockerfile: 153B                                                                                          0.0s
 => [internal] load metadata for docker.io/library/node:16-alpine                                                             0.8s
 => [auth] library/node:pull token for registry-1.docker.io                                                                   0.0s
 => [1/5] FROM docker.io/library/node:16-alpine@sha256:a1f9d027912b58a7c75be7716c97cfbc6d3099f3a97ed84aa490be9dee20e787      24.6s
 => => resolve docker.io/library/node:16-alpine@sha256:a1f9d027912b58a7c75be7716c97cfbc6d3099f3a97ed84aa490be9dee20e787       0.0s
 => => sha256:93b3025fe10392717d06ec0d012a9ffa2039d766a322aac899c6831dd93382c2 2.34MB / 2.34MB                                4.3s
 => => sha256:a1f9d027912b58a7c75be7716c97cfbc6d3099f3a97ed84aa490be9dee20e787 1.43kB / 1.43kB                                0.0s
 => => sha256:72e89a86be58c922ed7b1475e5e6f151537676470695dd106521738b060e139d 1.16kB / 1.16kB                                0.0s
 => => sha256:2573171e0124bb95d14d128728a52a97bb917ef45d7c4fa8cfe76bc44aa78b73 6.73kB / 6.73kB                                0.0s
 => => sha256:7264a8db6415046d36d16ba98b79778e18accee6ffa71850405994cffa9be7de 3.40MB / 3.40MB                                4.2s
 => => sha256:eee371b9ce3ffdbb8aa703b9a14d318801ddc3468f096bb6cfeabbeb715147f9 36.63MB / 36.63MB                             22.2s
 => => extracting sha256:7264a8db6415046d36d16ba98b79778e18accee6ffa71850405994cffa9be7de                                     0.1s
 => => sha256:d9059661ce70092af66d2773666584fc8addcb78a2be63f720022f4875577ea9 452B / 452B                                    4.4s
 => => extracting sha256:eee371b9ce3ffdbb8aa703b9a14d318801ddc3468f096bb6cfeabbeb715147f9                                     2.0s
 => => extracting sha256:93b3025fe10392717d06ec0d012a9ffa2039d766a322aac899c6831dd93382c2                                     0.1s
 => => extracting sha256:d9059661ce70092af66d2773666584fc8addcb78a2be63f720022f4875577ea9                                     0.0s
 => [internal] load build context                                                                                             0.0s
 => => transferring context: 187B                                                                                             0.0s
 => [2/5] WORKDIR /usr/src/app                                                                                                0.3s
 => [3/5] COPY package*.json ./                                                                                               0.0s
 => [4/5] RUN npm install                                                                                                    14.5s
 => [5/5] COPY . .                                                                                                            0.0s
 => exporting to image                                                                                                        0.7s
 => => exporting layers                                                                                                       0.7s
 => => writing image sha256:511ef81f3d085ab7ec01f7e071154a402548c6e32aef7d297d93ff441da5702a                                  0.0s
 => => naming to docker.io/library/inventory-api-image                                                                        0.0s
```

$ docker build -t clients-api-image .
```
[+] Building 0.6s (15/15) FINISHED
 => [internal] load build definition from Dockerfile                                                                          0.0s
 => => transferring dockerfile: 531B                                                                                          0.0s
 => [internal] load .dockerignore                                                                                             0.0s
 => => transferring context: 47B                                                                                              0.0s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/aspnet:3.1                                                     0.5s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/sdk:3.1                                                        0.5s
 => [build-env 1/6] FROM mcr.microsoft.com/dotnet/core/sdk:3.1@sha256:150d074697d1cda38a0c2185fe43895d84b5745841e9d15c5adba2  0.0s
 => [stage-1 1/3] FROM mcr.microsoft.com/dotnet/core/aspnet:3.1@sha256:e3b773f30a0a6e88d71ce52429f6847627fc9353e491346902ca3  0.0s
 => [internal] load build context                                                                                             0.0s
 => => transferring context: 20.50kB                                                                                          0.0s
 => CACHED [stage-1 2/3] WORKDIR /app                                                                                         0.0s
 => CACHED [build-env 2/6] RUN apt-get update && apt-get install -y ca-certificates                                           0.0s
 => CACHED [build-env 3/6] COPY . /app                                                                                        0.0s
 => CACHED [build-env 4/6] WORKDIR /app                                                                                       0.0s
 => CACHED [build-env 5/6] RUN dotnet restore --verbosity detailed                                                            0.0s
 => CACHED [build-env 6/6] RUN dotnet publish -c Release -o publish                                                           0.0s
 => CACHED [stage-1 3/3] COPY --from=build-env /app/publish .                                                                 0.0s
 => exporting to image                                                                                                        0.0s
 => => exporting layers                                                                                                       0.0s
 => => writing image sha256:155f6cc40347448fb775213a1bff0c3fb77f77d120704cf4e4ca73a3b2c9fbda                                  0.0s
 => => naming to docker.io/library/clients-api-image                                                                          0.0s
```

$ docker build -t resource-api-image .
```
[+] Building 1.4s (10/10) FINISHED
 => [internal] load .dockerignore                                                                                             0.0s
 => => transferring context: 2B                                                                                               0.0s
 => [internal] load build definition from Dockerfile                                                                          0.0s
 => => transferring dockerfile: 223B                                                                                          0.0s
 => [internal] load metadata for docker.io/library/python:3                                                                   1.3s
 => [auth] library/python:pull token for registry-1.docker.io                                                                 0.0s
 => [1/4] FROM docker.io/library/python:3@sha256:31ceea009f42df76371a8fb94fa191f988a25847a228dbeac35b6f8d2518a6ef             0.0s
 => [internal] load build contcd ext                                                                                             0.0s
 => => transferring context: 10.93kB                                                                                          0.0s
 => CACHED [2/4] ADD requirements.txt requirements.txt                                                                        0.0s
 => CACHED [3/4] RUN pip install -r requirements.txt                                                                          0.0s
 => CACHED [4/4] ADD . /                                                                                                      0.0s
 => exporting to image                                                                                                        0.0s
 => => exporting layers                                                                                                       0.0s
 => => writing image sha256:941df58b088e97f2aeff449334dd7551c3a7a09a47cd462f35faf38367e1fc52                                  0.0s
 => => naming to docker.io/library/resource-api-image                                                                         0.0s
 
```

# Build & Run:
```
$ docker-compose --verbose up --build

# OUTPUT:
$ docker-compose --verbose up --build
compose.config.config.find: Using configuration files: ./docker-compose.yaml
compose.cli.docker_client.get_client: docker-compose version 1.29.2, build unknown
docker-py version: 5.0.3
CPython version: 3.10.12
OpenSSL version: OpenSSL 3.0.2 15 Mar 2022
compose.cli.docker_client.get_client: Docker base_url: http+docker://localhost
compose.cli.docker_client.get_client: Docker version: Platform={'Name': 'Docker Engine - Community'}, Components=[{'Name': 'Engine', 'Version': '24.0.7', 'Details': {'ApiVersion': '1.43', 'Arch': 'amd64', 'BuildTime': '2023-10-26T09:07:41.000000000+00:00', 'Experimental': 'false', 'GitCommit': '311b9ff', 'GoVersion': 'go1.20.10', 'KernelVersion': '6.2.0-37-generic', 'MinAPIVersion': '1.12', 'Os': 'linux'}}, {'Name': 'containerd', 'Version': '1.6.25', 'Details': {'GitCommit': 'd8f198a4ed8892c764191ef7b3b06d8a2eeb5c7f'}}, {'Name': 'runc', 'Version': '1.1.10', 'Details': {'GitCommit': 'v1.1.10-0-g18a0cb0'}}, {'Name': 'docker-init', 'Version': '0.19.0', 'Details': {'GitCommit': 'de40ad0'}}], Version=24.0.7, ApiVersion=1.43, MinAPIVersion=1.12, GitCommit=311b9ff, GoVersion=go1.20.10, Os=linux, Arch=amd64, KernelVersion=6.2.0-37-generic, BuildTime=2023-10-26T09:07:41.000000000+00:00
compose.cli.verbose_proxy.proxy_callable: docker inspect_network <- ('coursepracticalguideeks_default')
compose.cli.verbose_proxy.proxy_callable: docker info <- ()
compose.cli.verbose_proxy.proxy_callable: docker info -> {'Architecture': 'x86_64',
 'BridgeNfIp6tables': True,
 'BridgeNfIptables': True,
 'CPUSet': True,
 'CPUShares': True,
 'CgroupDriver': 'systemd',
 'CgroupVersion': '2',
 'ContainerdCommit': {'Expected': 'd8f198a4ed8892c764191ef7b3b06d8a2eeb5c7f',
                      'ID': 'd8f198a4ed8892c764191ef7b3b06d8a2eeb5c7f'},
 'Containers': 1,
...
compose.cli.verbose_proxy.proxy_callable: docker inspect_network <- ('course_practical_guide_eks_default')
compose.network.ensure: Creating network "course_practical_guide_eks_default" with the default driver
compose.cli.verbose_proxy.proxy_callable: docker create_network <- (name='course_practical_guide_eks_default', driver=None, options=None, ipam=None, internal=False, enable_ipv6=False, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.network': 'default', 'com.docker.compose.version': '1.29.2'}, attachable=True, check_duplicate=True)
compose.cli.verbose_proxy.proxy_callable: docker create_network -> {'Id': '6b871ea986b1414123f830741eca651d35da5fc620ee5f3d92e86f2f43e20db9',
 'Warning': ''}
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.service.build: Building resources-api
[+] Building 26.5s (9/9) FINISHED                                                                                                                                                            
 => [internal] load build definition from Dockerfile                                                                                                                                    0.0s
 => => transferring dockerfile: 223B                                                                                                                                                    0.0s
 => [internal] load .dockerignore                                                                                                                                                       0.0s
 => => transferring context: 2B                                                                                                                                                         0.0s
 => [internal] load metadata for docker.io/library/python:3                                                                                                                             0.3s
 => CACHED [1/4] FROM docker.io/library/python:3@sha256:1987c4ae3b5afaa3a7c5e247e9eaab7348082ba167986ca90d4d6a197fb364e8                                                                0.0s
 => [internal] load build context                                                                                                                                                       0.0s
 => => transferring context: 10.94kB                                                                                                                                                    0.0s
 => [2/4] ADD requirements.txt requirements.txt                                                                                                                                         0.0s
 => [3/4] RUN pip install -r requirements.txt                                                                                                                                          25.3s
 => [4/4] ADD . /                                                                                                                                                                       0.0s
 => exporting to image                                                                                                                                                                  0.8s 
 => => exporting layers                                                                                                                                                                 0.8s 
 => => writing image sha256:6fe360a3f156e750280d7f9819618ca0e8a4895fd66ae8ccfb830aa4be8620e8                                                                                            0.0s 
 => => naming to docker.io/library/course_practical_guide_eks_resources-api                                                                                                             0.0s 
compose.service.build: Building inventory-api                                                                                                                                                
[+] Building 0.4s (10/10) FINISHED                                                                                                                                                           
 => [internal] load build definition from Dockerfile                                                                                                                                    0.0s
 => => transferring dockerfile: 146B                                                                                                                                                    0.0s
 => [internal] load .dockerignore                                                                                                                                                       0.0s
 => => transferring context: 2B                                                                                                                                                         0.0s
 => [internal] load metadata for docker.io/library/node:10                                                                                                                              0.3s
 => [1/5] FROM docker.io/library/node:10@sha256:59531d2835edd5161c8f9512f9e095b1836f7a1fcb0ab73e005ec46047384911                                                                        0.0s
 => [internal] load build context                                                                                                                                                       0.0s
 => => transferring context: 46.24kB                                                                                                                                                    0.0s
 => CACHED [2/5] WORKDIR /usr/src/app                                                                                                                                                   0.0s
 => CACHED [3/5] COPY package*.json ./                                                                                                                                                  0.0s
 => CACHED [4/5] RUN npm install                                                                                                                                                        0.0s
 => CACHED [5/5] COPY . .                                                                                                                                                               0.0s
 => exporting to image                                                                                                                                                                  0.0s
 => => exporting layers                                                                                                                                                                 0.0s
 => => writing image sha256:be5c4af3a075a79f5aa3e27139592442b0ef4eacdf02e5a64c07463ba86a176d                                                                                            0.0s
 => => naming to docker.io/library/course_practical_guide_eks_inventory-api                                                                                                             0.0s
compose.service.build: Building clients-api
[+] Building 0.6s (14/14) FINISHED                                                                                                                                                           
 => [internal] load build definition from Dockerfile                                                                                                                                    0.0s
 => => transferring dockerfile: 370B                                                                                                                                                    0.0s
 => [internal] load .dockerignore                                                                                                                                                       0.0s
 => => transferring context: 47B                                                                                                                                                        0.0s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/aspnet:3.1                                                                                                               0.6s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/sdk:3.1                                                                                                                  0.6s
 => [internal] load build context                                                                                                                                                       0.0s
 => => transferring context: 20.32kB                                                                                                                                                    0.0s
 => [build-env 1/5] FROM mcr.microsoft.com/dotnet/core/sdk:3.1@sha256:150d074697d1cda38a0c2185fe43895d84b5745841e9d15c5adba29604a6e4cb                                                  0.0s
 => [stage-1 1/3] FROM mcr.microsoft.com/dotnet/core/aspnet:3.1@sha256:e3b773f30a0a6e88d71ce52429f6847627fc9353e491346902ca345760b82bdd                                                 0.0s
 => CACHED [stage-1 2/3] WORKDIR /app                                                                                                                                                   0.0s
 => CACHED [build-env 2/5] COPY . /app                                                                                                                                                  0.0s
 => CACHED [build-env 3/5] WORKDIR /app                                                                                                                                                 0.0s
 => CACHED [build-env 4/5] RUN dotnet restore                                                                                                                                           0.0s
 => CACHED [build-env 5/5] RUN dotnet publish -c Release -o publish                                                                                                                     0.0s
 => CACHED [stage-1 3/3] COPY --from=build-env /app/publish .                                                                                                                           0.0s
 => exporting to image                                                                                                                                                                  0.0s
 => => exporting layers                                                                                                                                                                 0.0s
 => => writing image sha256:ba756e91a696283bb88be87b7f1fc40964134310e7e3b197333f25e4b8fbdd53                                                                                            0.0s
 => => naming to docker.io/library/course_practical_guide_eks_clients-api                                                                                                               0.0s
compose.service.build: Building renting-api
[+] Building 0.4s (10/10) FINISHED                                                                                                                                                           
 => [internal] load .dockerignore                                                                                                                                                       0.0s
 => => transferring context: 2B                                                                                                                                                         0.0s
 => [internal] load build definition from Dockerfile                                                                                                                                    0.0s
 => => transferring dockerfile: 283B                                                                                                                                                    0.0s
 => [internal] load metadata for docker.io/library/ruby:2.6.3                                                                                                                           0.3s
 => [1/5] FROM docker.io/library/ruby:2.6.3@sha256:358f16e92d0f66599103318f7a8528d449b0973fd89e46a1a5c47cec7479f09b                                                                     0.0s
 => [internal] load build context                                                                                                                                                       0.0s
 => => transferring context: 3.65kB                                                                                                                                                     0.0s
 => CACHED [2/5] WORKDIR /usr/src/app                                                                                                                                                   0.0s
 => CACHED [3/5] COPY Gemfile Gemfile.lock ./                                                                                                                                           0.0s
 => CACHED [4/5] RUN bundle install                                                                                                                                                     0.0s
 => CACHED [5/5] COPY . .                                                                                                                                                               0.0s
 => exporting to image                                                                                                                                                                  0.0s
 => => exporting layers                                                                                                                                                                 0.0s
 => => writing image sha256:9359280ad31cd84280a1b4c74e073e918ebe9e5d0b92d78368fa336c3c0c8d24                                                                                            0.0s
 => => naming to docker.io/library/course_practical_guide_eks_renting-api                                                                                                               0.0s
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('nginx:stable-alpine')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': '',
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': ['/docker-entrypoint.sh'],
            'Env': ['PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
...
compose.service.build: Building front-end
[+] Building 0.8s (15/15) FINISHED                                                                                                                                                           
 => [internal] load build definition from Dockerfile                                                                                                                                    0.0s
 => => transferring dockerfile: 271B                                                                                                                                                    0.0s
 => [internal] load .dockerignore                                                                                                                                                       0.0s
 => => transferring context: 2B                                                                                                                                                         0.0s
 => [internal] load metadata for docker.io/library/nginx:1.15-alpine                                                                                                                    0.7s
 => [internal] load metadata for docker.io/library/node:carbon-alpine                                                                                                                   0.4s
 => [stage-0 1/6] FROM docker.io/library/node:carbon-alpine@sha256:38f7bf07ffd72ac612ec8c829cb20ad416518dbb679768d7733c93175453f4d4                                                     0.0s
 => [internal] load build context                                                                                                                                                       0.0s
 => => transferring context: 12.64kB                                                                                                                                                    0.0s
 => [stage-1 1/3] FROM docker.io/library/nginx:1.15-alpine@sha256:57a226fb6ab6823027c0704a9346a890ffb0cacde06bc19bbc234c8720673555                                                      0.0s
 => CACHED [stage-0 2/6] WORKDIR /opt/forms                                                                                                                                             0.0s
 => CACHED [stage-0 3/6] COPY package*.json ./                                                                                                                                          0.0s
 => CACHED [stage-0 4/6] RUN npm install                                                                                                                                                0.0s
 => CACHED [stage-0 5/6] COPY . ./                                                                                                                                                      0.0s
 => CACHED [stage-0 6/6] RUN npm run build                                                                                                                                              0.0s
 => CACHED [stage-1 2/3] COPY --from=0 /opt/forms/dist /usr/share/nginx/html                                                                                                            0.0s
 => CACHED [stage-1 3/3] COPY nginx.conf /etc/nginx/conf.d/default.conf                                                                                                                 0.0s
 => exporting to image                                                                                                                                                                  0.0s
 => => exporting layers                                                                                                                                                                 0.0s
 => => writing image sha256:29c6ca07acc94df7668c8e8571b9ea7cbd67d2acd1093346dcb2c70bc606ad9c                                                                                            0.0s
 => => naming to docker.io/library/course_practical_guide_eks_front-end                                                                                                                 0.0s
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.project._get_convergence_plans: inventory-api has upstream changes (resources-api)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'status': ['created', 'exited'], 'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'status': ['created', 'exited'], 'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.project._get_convergence_plans: proxy has upstream changes (resources-api, inventory-api, renting-api, clients-api)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'status': ['created', 'exited'], 'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'status': ['created', 'exited'], 'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.parallel.feed_queue: Pending: {<Service: clients-api>, <Service: resources-api>, <Service: proxy>, <Service: renting-api>, <Service: inventory-api>, <Service: front-end>}
compose.parallel.feed_queue: Starting producer thread for <Service: clients-api>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for <Service: resources-api>
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for <Service: renting-api>
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_clients-api_1 ... 
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='clients-api', number=1)}
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='clients-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_clients-api')
compose.parallel.feed_queue: Starting producer thread for <Service: front-end>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_resources-api_1 ... 
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='resources-api', number=1)}
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh',
                    '-c',
                    'dotnet ACG.EKS.Bookstore.Clients-API.dll'],
...
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='resources-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_clients-api')
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_resources-api')
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_renting-api_1   ... 
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh',
                    '-c',
                    'dotnet ACG.EKS.Bookstore.Clients-API.dll'],
...
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_front-end_1     ... 
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='renting-api', number=1)}
compose.service.build_container_labels: Added config hash: c1c2e984d68b373819dbf19cc5725e33a0fa4f0e45c599369b9cfcda82e419d9
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='front-end', number=1)}
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='renting-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_renting-api')
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'5003/tcp': ['5003']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='front-end', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['gunicorn',
                    '--worker-tmp-dir',
                    '/dev/shm',
...
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'5003/tcp': [{'HostIp': '', 'HostPort': '5003'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_resources-api')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_front-end')
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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'], ports=[('5003', 'tcp')], volumes={}, name='course_practical_guide_eks_clients-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'clients-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'c1c2e984d68b373819dbf19cc5725e33a0fa4f0e45c599369b9cfcda82e419d9'}, image='course_practical_guide_eks_clients-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'5003/tcp': [{'HostIp': '', 'HostPort': '5003'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['clients-api'], 'IPAMConfig': {}}}})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['bundle',
                    'exec',
                    'rails',
...
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_renting-api')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['gunicorn',
                    '--worker-tmp-dir',
                    '/dev/shm',
...
compose.service.build_container_labels: Added config hash: c62bbf0704a936c0681c20e239fd30cf9fb9773594e384d02a771419a5bc7fdb
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'5000/tcp': ['5000']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'5000/tcp': [{'HostIp': '', 'HostPort': '5000'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['DYNAMODB_TABLE=development-resources', 'AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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', 'AWS_XRAY_SDK_ENABLED=false'], ports=[('5000', 'tcp')], volumes={}, name='course_practical_guide_eks_resources-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'resources-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'c62bbf0704a936c0681c20e239fd30cf9fb9773594e384d02a771419a5bc7fdb'}, image='course_practical_guide_eks_resources-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'5000/tcp': [{'HostIp': '', 'HostPort': '5000'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['resources-api'], 'IPAMConfig': {}}}})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['bundle',
                    'exec',
                    'rails',
...
compose.service.build_container_labels: Added config hash: 1271d8da681797bf3af1dfc2b6a8818b8d9af8df9a2a9b5289a5dd2287c2e850
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'3000/tcp': ['5004']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'3000/tcp': [{'HostIp': '', 'HostPort': '5004'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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', 'DYNAMODB_TABLE=development-renting', 'INVENTORY_API_ENDPOINT=http://inventory-api:5001', 'CLIENTS_API_ENDPOINT=http://clients-api:5003', 'RESOURCES_API_ENDPOINT=http://resources-api:5000'], ports=[('3000', 'tcp')], volumes={}, name='course_practical_guide_eks_renting-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'renting-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': '1271d8da681797bf3af1dfc2b6a8818b8d9af8df9a2a9b5289a5dd2287c2e850'}, image='course_practical_guide_eks_renting-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'3000/tcp': [{'HostIp': '', 'HostPort': '5004'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['renting-api'], 'IPAMConfig': {}}}})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': None,
...
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_front-end')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': None,
...
compose.service.build_container_labels: Added config hash: f273140484adcfea4db2886a8d55a0c60c5faaf5d12b0596c59dd4efd8a6d857
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'80/tcp': ['5002']}, binds=['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '5002'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (ports=[('80', 'tcp')], volumes={'/usr/share/nginx/html/assets/json/config.json': {}}, name='course_practical_guide_eks_front-end_1', detach=True, environment=[], labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'front-end', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'f273140484adcfea4db2886a8d55a0c60c5faaf5d12b0596c59dd4efd8a6d857'}, image='course_practical_guide_eks_front-end', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'], 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '5002'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['front-end'], 'IPAMConfig': {}}}})
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': 'bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb')
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['-c', 'dotnet ACG.EKS.Bookstore.Clients-API.dll'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh',
                    '-c',
                    'dotnet ACG.EKS.Bookstore.Clients-API.dll'],
            'Domainname': '',
            'Entrypoint': None,
...
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb', stdout=True, stderr=True, stream=True)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68')
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': 'f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47')
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd')
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d6211d240>
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['exec', 'rails', 'server', '-p', '5004', '-b', '0.0.0.0'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['bundle',
                    'exec',
                    'rails',
                    'server',
                    '-p',
...
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47', stdout=True, stderr=True, stream=True)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['--worker-tmp-dir', '/dev/shm', '--bind', '0.0.0.0:5000', 'wsgi:app'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['gunicorn',
                    '--worker-tmp-dir',
                    '/dev/shm',
                    '--bind',
                    '0.0.0.0:5000',
...
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68', stdout=True, stderr=True, stream=True)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['-g', 'daemon off;'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': None,
            'Env': ['PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
                    'NGINX_VERSION=1.15.12'],
...
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd', stdout=True, stderr=True, stream=True)
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d622dfaf0>
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb', 'course_practical_guide_eks_default', aliases=['bb56a82c7891', 'clients-api'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d6211d120>
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68', 'course_practical_guide_eks_default')
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d622de7a0>
compose.cli.verbose_proxy.proxy_callable: docker start <- ('bb56a82c7891784c8d6658d63a445a4d5e52e9a93c40225b21db8478efd97eeb')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd', 'course_practical_guide_eks_default')
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47', 'course_practical_guide_eks_default', aliases=['renting-api', 'f8a236fb09fb'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68', 'course_practical_guide_eks_default', aliases=['4cce4646849d', 'resources-api'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd', 'course_practical_guide_eks_default', aliases=['5e4589dc1b22', 'front-end'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('f8a236fb09fb2d25859e0984c4e3aa696c91ef82d29acad51b4a6714febe0b47')
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68')
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('5e4589dc1b22b997b25795f6164dba3f0425a4841e5064450b10bad0402be2bd')
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
Creating course_practical_guide_eks_clients-api_1   ... done
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker start -> None
compose.parallel.parallel_execute_iter: Finished processing: ServiceName(project='course_practical_guide_eks', service='clients-api', number=1)
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: clients-api>
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
Creating course_practical_guide_eks_resources-api_1 ... done
compose.cli.verbose_proxy.proxy_callable: docker start -> None
compose.parallel.parallel_execute_iter: Finished processing: ServiceName(project='course_practical_guide_eks', service='resources-api', number=1)
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: resources-api>
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Starting producer thread for <Service: inventory-api>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=inventory-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_inventory-api_1 ... 
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='inventory-api', number=1)}
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='inventory-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_inventory-api')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh', '-c', 'node app.js'],
            'Domainname': '',
            'Entrypoint': ['docker-entrypoint.sh'],
...
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_inventory-api')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': 'buildkit.dockerfile.v0',
 'Config': {'ArgsEscaped': True,
            'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh', '-c', 'node app.js'],
            'Domainname': '',
            'Entrypoint': ['docker-entrypoint.sh'],
...
compose.service.build_container_labels: Added config hash: dbbb582180a12234adadb971bbe26b6bdb24fdb11faa78caf478c6de3d6b1aa7
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 1 items)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68')
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': 'docker-default',
 'Args': ['--worker-tmp-dir', '/dev/shm', '--bind', '0.0.0.0:5000', 'wsgi:app'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['gunicorn',
                    '--worker-tmp-dir',
                    '/dev/shm',
                    '--bind',
                    '0.0.0.0:5000',
...
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[('course_practical_guide_eks_resources-api_1', 'resources-api'), ('course_practical_guide_eks_resources-api_1', 'course_practical_guide_eks_resources-api_1'), ('course_practical_guide_eks_resources-api_1', 'resources-api_1')], port_bindings={'5001/tcp': ['5001']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': ['course_practical_guide_eks_resources-api_1:course_practical_guide_eks_resources-api_1',
           'course_practical_guide_eks_resources-api_1:resources-api',
           'course_practical_guide_eks_resources-api_1:resources-api_1'],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'5001/tcp': [{'HostIp': '', 'HostPort': '5001'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['DYNAMODB_TABLE=development-inventory', 'RESOURCE_API_ENDPOINT=http://resources-api:5000', 'AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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'], ports=[('5001', 'tcp')], volumes={}, name='course_practical_guide_eks_inventory-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'inventory-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'dbbb582180a12234adadb971bbe26b6bdb24fdb11faa78caf478c6de3d6b1aa7'}, image='course_practical_guide_eks_inventory-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'5001/tcp': [{'HostIp': '', 'HostPort': '5001'}]}, 'Links': ['course_practical_guide_eks_resources-api_1:course_practical_guide_eks_resources-api_1', 'course_practical_guide_eks_resources-api_1:resources-api', 'course_practical_guide_eks_resources-api_1:resources-api_1'], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['inventory-api'], 'IPAMConfig': {}}}})
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
Creating course_practical_guide_eks_renting-api_1   ... done
compose.cli.verbose_proxy.proxy_callable: docker start -> None
compose.parallel.parallel_execute_iter: Finished processing: ServiceName(project='course_practical_guide_eks', service='renting-api', number=1)
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: renting-api>
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a')
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['/bin/sh', '-c', 'node app.js'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['/bin/sh', '-c', 'node app.js'],
            'Domainname': '',
            'Entrypoint': ['docker-entrypoint.sh'],
            'Env': ['DYNAMODB_TABLE=development-inventory',
                    'RESOURCE_API_ENDPOINT=http://resources-api:5000',
...
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a', stdout=True, stderr=True, stream=True)
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d620362c0>
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a', 'course_practical_guide_eks_default')
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 1 items)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('4cce4646849d571cbb8204eba80fe67ebf9558fab88aaa251c84a1f0f0ac6e68')
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': 'docker-default',
 'Args': ['--worker-tmp-dir', '/dev/shm', '--bind', '0.0.0.0:5000', 'wsgi:app'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['gunicorn',
                    '--worker-tmp-dir',
                    '/dev/shm',
                    '--bind',
                    '0.0.0.0:5000',
...
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a', 'course_practical_guide_eks_default', aliases=['inventory-api', '8cd56ae1c3eb'], ipv4_address=None, ipv6_address=None, links=[('course_practical_guide_eks_resources-api_1', 'resources-api'), ('course_practical_guide_eks_resources-api_1', 'course_practical_guide_eks_resources-api_1'), ('course_practical_guide_eks_resources-api_1', 'resources-api_1')], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('8cd56ae1c3eb16289db229c110c2ab41c8751156bc19f596fda16c521d0fb71a')
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
Creating course_practical_guide_eks_front-end_1     ... done
compose.parallel.parallel_execute_iter: Finished processing: ServiceName(project='course_practical_guide_eks', service='front-end', number=1)
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: front-end>
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker start -> None
Creating course_practical_guide_eks_inventory-api_1 ... done
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: inventory-api>
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Starting producer thread for <Service: proxy>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=proxy', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_proxy_1         ... 
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='proxy', number=1)}
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='proxy', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('nginx:stable-alpine')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': '',
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': ['/docker-entrypoint.sh'],
            'Env': ['PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
...
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('nginx:stable-alpine')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image -> {'Architecture': 'amd64',
 'Author': '',
 'Comment': '',
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': ['/docker-entrypoint.sh'],
            'Env': ['PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
...
compose.service.build_container_labels: Added config hash: ebde1b14f22feb2b2c7ef526cef2c80a15d66f3b2f615afb14ef3cd3c60c4b36
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'80/tcp': ['80']}, binds=['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '80'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (image='nginx:stable-alpine', ports=[('80', 'tcp')], volumes={'/etc/nginx/conf.d/default.conf': {}}, name='course_practical_guide_eks_proxy_1', detach=True, environment=[], labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'proxy', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'ebde1b14f22feb2b2c7ef526cef2c80a15d66f3b2f615afb14ef3cd3c60c4b36'}, host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'], 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '80'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['proxy'], 'IPAMConfig': {}}}})
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673')
compose.cli.verbose_proxy.proxy_callable: docker inspect_container -> {'AppArmorProfile': '',
 'Args': ['nginx', '-g', 'daemon off;'],
 'Config': {'AttachStderr': False,
            'AttachStdin': False,
            'AttachStdout': False,
            'Cmd': ['nginx', '-g', 'daemon off;'],
            'Domainname': '',
            'Entrypoint': ['/docker-entrypoint.sh'],
            'Env': ['PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin',
                    'NGINX_VERSION=1.24.0',
...
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker attach <- ('76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673', stdout=True, stderr=True, stream=True)
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker attach -> <docker.types.daemon.CancellableStream object at 0x7f3d6211f400>
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673', 'course_practical_guide_eks_default', aliases=['proxy', '76ffa43269a6'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('76ffa43269a69fe27dfaa2f4bac1cb88245487c9455fddc4a6298c524c42d673')
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker start -> None
Creating course_practical_guide_eks_proxy_1         ... done
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: proxy>
compose.parallel.feed_queue: Pending: set()
Attaching to course_practical_guide_eks_clients-api_1, course_practical_guide_eks_resources-api_1, course_practical_guide_eks_renting-api_1, course_practical_guide_eks_front-end_1, course_practical_guide_eks_inventory-api_1, course_practical_guide_eks_proxy_1
clients-api_1    | info: Microsoft.Hosting.Lifetime[0]
clients-api_1    |       Now listening on: http://[::]:5003
clients-api_1    | info: Microsoft.Hosting.Lifetime[0]
clients-api_1    |       Application started. Press Ctrl+C to shut down.
clients-api_1    | info: Microsoft.Hosting.Lifetime[0]
clients-api_1    |       Hosting environment: Production
clients-api_1    | info: Microsoft.Hosting.Lifetime[0]
clients-api_1    |       Content root path: /app
inventory-api_1  | Inventory API Running...
proxy_1          | /docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
proxy_1          | /docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
proxy_1          | /docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
resources-api_1  | [2023-12-02 03:31:14 +0000] [1] [INFO] Starting gunicorn 21.2.0
resources-api_1  | [2023-12-02 03:31:14 +0000] [1] [INFO] Listening at: http://0.0.0.0:5000 (1)
resources-api_1  | [2023-12-02 03:31:14 +0000] [1] [INFO] Using worker: sync
resources-api_1  | [2023-12-02 03:31:14 +0000] [7] [INFO] Booting worker with pid: 7
compose.cli.verbose_proxy.proxy_callable: docker events <- (filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.oneoff=False']}, decode=True)
compose.cli.verbose_proxy.proxy_callable: docker events -> <docker.types.daemon.CancellableStream object at 0x7f3d622df8b0>
proxy_1          | 10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
proxy_1          | 10-listen-on-ipv6-by-default.sh: info: /etc/nginx/conf.d/default.conf differs from the packaged version
proxy_1          | /docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
proxy_1          | /docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
proxy_1          | /docker-entrypoint.sh: Configuration complete; ready for start up
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: using the "epoll" event method
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: nginx/1.24.0
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: built by gcc 12.2.1 20220924 (Alpine 12.2.1_git20220924-r4) 
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: OS: Linux 6.2.0-37-generic
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker processes
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 29
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 30
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 31
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 32
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 33
proxy_1          | 2023/12/02 03:31:17 [notice] 1#1: start worker process 34
renting-api_1    | => Booting Puma
renting-api_1    | => Rails 6.0.3.6 application starting in development 
renting-api_1    | => Run `rails server --help` for more startup options
renting-api_1    | Puma starting in single mode...
renting-api_1    | * Version 4.3.7 (ruby 2.6.3-p62), codename: Mysterious Traveller
renting-api_1    | * Min threads: 5, max threads: 5
renting-api_1    | * Environment: development
renting-api_1    | * Listening on tcp://0.0.0.0:5004
renting-api_1    | Use Ctrl-C to stop


```