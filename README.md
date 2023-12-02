# A Practical Guide to EKS

In this repository you will find all the assets required for the course `A Practical Guide to Amazon EKS`, by A Cloud Guru.


## Bookstore application

This solution has been built for for explaining all the concepts in this course. It is complete enough for covering a real case of microservices running on EKS and integrating with other AWS Services.

> You can find in [here](_docs/api.md) the documentation of the APIs.


# Build & Run:
```
$ docker-compose --verbose up -d 

...


=> => sha256:ebfe61739a0e0c937dfe998a9838dcf5aa2a27700d63d2387dae896d1c5005c4 2.01kB / 2.01kB                                   0.0s
 => => sha256:48b2d58a56e99520540b5ecafb202ae036a53b5a982845434722691ccba6499a 6.16MB / 6.16MB                                   5.4s
 => => sha256:67ddeb5b15df31094e9a670c0f869c9cce23b057f052a5d6f3c5582643d19477 232B / 232B                                       0.5s
 => => sha256:7da1b82bcb720a01ec8dee4e9846f8ff3401db3248c40d314a7456b8b44b732c 2.68MB / 2.68MB                                   3.8s
 => => extracting sha256:48b2d58a56e99520540b5ecafb202ae036a53b5a982845434722691ccba6499a                                        0.5s
 => => extracting sha256:b61fb8c5b70291ec75085cef06fc9e72445483294dbe4edfff8006fc66574fa8                                        1.2s
 => => extracting sha256:67ddeb5b15df31094e9a670c0f869c9cce23b057f052a5d6f3c5582643d19477                                        0.0s
 => => extracting sha256:7da1b82bcb720a01ec8dee4e9846f8ff3401db3248c40d314a7456b8b44b732c                                        0.5s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 251B                                                                                                0.0s
 => [2/4] ADD requirements.txt requirements.txt                                                                                  0.2s
 => [3/4] RUN pip install -r requirements.txt                                                                                   20.1s
 => [4/4] ADD . /                                                                                                                0.0s
 => exporting to image                                                                                                           0.8s
 => => exporting layers                                                                                                          0.8s
 => => writing image sha256:12f3fc89b8363b2a0108527472c71a41d1574377346031a46732e700a37331b3                                     0.0s
 => => naming to docker.io/library/course_practical_guide_eks_resources-api                                                      0.0s
WARNING: compose.service.ensure_image_exists: Image for service resources-api was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_inventory-api')
compose.service.build: Building inventory-api
[+] Building 497.5s (10/10) FINISHED                                                                                                  
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 146B                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/node:10                                                                       1.3s
 => [1/5] FROM docker.io/library/node:10@sha256:59531d2835edd5161c8f9512f9e095b1836f7a1fcb0ab73e005ec46047384911               488.2s
 => => resolve docker.io/library/node:10@sha256:59531d2835edd5161c8f9512f9e095b1836f7a1fcb0ab73e005ec46047384911                 0.0s
 => => sha256:76b8ef87096fa726adbe8f073ef69bb5664bac19474c5cce4dd69e08a234903b 45.38MB / 45.38MB                                50.4s
 => => sha256:59531d2835edd5161c8f9512f9e095b1836f7a1fcb0ab73e005ec46047384911 776B / 776B                                       0.0s
 => => sha256:686e0e859358f28bfe1641e1627549b9cd0ad74f222b953d74209213488c6858 2.21kB / 2.21kB                                   0.0s
 => => sha256:28dca6642db82aaecbed18101d9966f001e8de6691e1a1718c2927c124d81262 7.83kB / 7.83kB                                   0.0s
 => => sha256:2e2bafe8a0f40509cc10249087268e66a662e437f10e9598a09abb5687038a57 11.29MB / 11.29MB                                27.7s
 => => sha256:b53ce1fd2746e8d2037f1b0b91ddea0cc7411eb3e5949fe10c0320aca8f7392b 4.34MB / 4.34MB                                   4.5s
 => => sha256:84a8c1bd5887cc4a89e1f286fed9ee31ce12dba9f6813cf14082ada3e9ab6f63 49.79MB / 49.79MB                                45.9s
 => => sha256:7a803dc0b40fcd10faee3fb3ebb2d7aaa88500520e6295295f5163c4bb48548b 214.35MB / 214.35MB                             466.2s
 => => sha256:b800e94e7303e276b8fb4911a40bfe28f46180d997022c69bf1ee02fb7b86721 4.19kB / 4.19kB                                  46.2s
 => => sha256:0da9fbf60d485c74d153bfc7562f34533550e3dd8aa78f5e8c2476ed500e0e73 21.42MB / 21.42MB                                74.0s
 => => extracting sha256:76b8ef87096fa726adbe8f073ef69bb5664bac19474c5cce4dd69e08a234903b                                        5.1s
 => => sha256:04dccde934cf0d6ab9d303fe73b36bc4ed84329d9d562049a69a5d38afb83f14 2.48MB / 2.48MB                                  56.6s
 => => extracting sha256:2e2bafe8a0f40509cc10249087268e66a662e437f10e9598a09abb5687038a57                                        0.9s
 => => extracting sha256:b53ce1fd2746e8d2037f1b0b91ddea0cc7411eb3e5949fe10c0320aca8f7392b                                        0.2s
 => => sha256:73269890f6fdf96184d0fdb0afe3cf697b0c8dbe1e7a077f0fab445d74372c78 294B / 294B                                      56.9s
 => => extracting sha256:84a8c1bd5887cc4a89e1f286fed9ee31ce12dba9f6813cf14082ada3e9ab6f63                                        5.7s
 => => extracting sha256:7a803dc0b40fcd10faee3fb3ebb2d7aaa88500520e6295295f5163c4bb48548b                                       17.0s
 => => extracting sha256:b800e94e7303e276b8fb4911a40bfe28f46180d997022c69bf1ee02fb7b86721                                        0.0s
 => => extracting sha256:0da9fbf60d485c74d153bfc7562f34533550e3dd8aa78f5e8c2476ed500e0e73                                        3.4s
 => => extracting sha256:04dccde934cf0d6ab9d303fe73b36bc4ed84329d9d562049a69a5d38afb83f14                                        0.3s
 => => extracting sha256:73269890f6fdf96184d0fdb0afe3cf697b0c8dbe1e7a077f0fab445d74372c78                                        0.0s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 46.24kB                                                                                             0.0s
 => [2/5] WORKDIR /usr/src/app                                                                                                   0.4s
 => [3/5] COPY package*.json ./                                                                                                  0.0s
 => [4/5] RUN npm install                                                                                                        6.8s
 => [5/5] COPY . .                                                                                                               0.0s
 => exporting to image                                                                                                           0.7s
 => => exporting layers                                                                                                          0.7s
 => => writing image sha256:be5c4af3a075a79f5aa3e27139592442b0ef4eacdf02e5a64c07463ba86a176d                                     0.0s
 => => naming to docker.io/library/course_practical_guide_eks_inventory-api                                                      0.0s
WARNING: compose.service.ensure_image_exists: Image for service inventory-api was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_clients-api')
compose.service.build: Building clients-api
[+] Building 42.6s (14/14) FINISHED                                                                                                   
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 370B                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 47B                                                                                                 0.0s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/aspnet:3.1                                                        0.5s
 => [internal] load metadata for mcr.microsoft.com/dotnet/core/sdk:3.1                                                           0.5s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 20.32kB                                                                                             0.0s
 => [stage-1 1/3] FROM mcr.microsoft.com/dotnet/core/aspnet:3.1@sha256:e3b773f30a0a6e88d71ce52429f6847627fc9353e491346902ca3457  0.0s
 => CACHED [build-env 1/5] FROM mcr.microsoft.com/dotnet/core/sdk:3.1@sha256:150d074697d1cda38a0c2185fe43895d84b5745841e9d15c5a  0.0s
 => [build-env 2/5] COPY . /app                                                                                                  0.0s
 => [build-env 3/5] WORKDIR /app                                                                                                 0.0s
 => [build-env 4/5] RUN dotnet restore                                                                                          36.5s
 => [build-env 5/5] RUN dotnet publish -c Release -o publish                                                                     5.3s 
 => CACHED [stage-1 2/3] WORKDIR /app                                                                                            0.0s 
 => [stage-1 3/3] COPY --from=build-env /app/publish .                                                                           0.1s 
 => exporting to image                                                                                                           0.1s 
 => => exporting layers                                                                                                          0.1s 
 => => writing image sha256:ba756e91a696283bb88be87b7f1fc40964134310e7e3b197333f25e4b8fbdd53                                     0.0s 
 => => naming to docker.io/library/course_practical_guide_eks_clients-api                                                        0.0s
WARNING: compose.service.ensure_image_exists: Image for service clients-api was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_renting-api')
compose.service.build: Building renting-api
[+] Building 1.3s (10/10) FINISHED                                                                                                    
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 283B                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/ruby:2.6.3                                                                    1.2s
 => [1/5] FROM docker.io/library/ruby:2.6.3@sha256:358f16e92d0f66599103318f7a8528d449b0973fd89e46a1a5c47cec7479f09b              0.0s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 3.65kB                                                                                              0.0s
 => CACHED [2/5] WORKDIR /usr/src/app                                                                                            0.0s
 => CACHED [3/5] COPY Gemfile Gemfile.lock ./                                                                                    0.0s
 => CACHED [4/5] RUN bundle install                                                                                              0.0s
 => CACHED [5/5] COPY . .                                                                                                        0.0s
 => exporting to image                                                                                                           0.0s
 => => exporting layers                                                                                                          0.0s
 => => writing image sha256:9359280ad31cd84280a1b4c74e073e918ebe9e5d0b92d78368fa336c3c0c8d24                                     0.0s
 => => naming to docker.io/library/course_practical_guide_eks_renting-api                                                        0.0s
WARNING: compose.service.ensure_image_exists: Image for service renting-api was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_front-end')
compose.service.build: Building front-end
[+] Building 1.1s (15/15) FINISHED                                                                                                    
 => [internal] load build definition from Dockerfile                                                                             0.0s
 => => transferring dockerfile: 271B                                                                                             0.0s
 => [internal] load .dockerignore                                                                                                0.0s
 => => transferring context: 2B                                                                                                  0.0s
 => [internal] load metadata for docker.io/library/nginx:1.15-alpine                                                             0.9s
 => [internal] load metadata for docker.io/library/node:carbon-alpine                                                            1.0s
 => [stage-0 1/6] FROM docker.io/library/node:carbon-alpine@sha256:38f7bf07ffd72ac612ec8c829cb20ad416518dbb679768d7733c93175453  0.0s
 => [internal] load build context                                                                                                0.0s
 => => transferring context: 12.64kB                                                                                             0.0s
 => [stage-1 1/3] FROM docker.io/library/nginx:1.15-alpine@sha256:57a226fb6ab6823027c0704a9346a890ffb0cacde06bc19bbc234c8720673  0.0s
 => CACHED [stage-0 2/6] WORKDIR /opt/forms                                                                                      0.0s
 => CACHED [stage-0 3/6] COPY package*.json ./                                                                                   0.0s
 => CACHED [stage-0 4/6] RUN npm install                                                                                         0.0s
 => CACHED [stage-0 5/6] COPY . ./                                                                                               0.0s
 => CACHED [stage-0 6/6] RUN npm run build                                                                                       0.0s
 => CACHED [stage-1 2/3] COPY --from=0 /opt/forms/dist /usr/share/nginx/html                                                     0.0s
 => CACHED [stage-1 3/3] COPY nginx.conf /etc/nginx/conf.d/default.conf                                                          0.0s
 => exporting to image                                                                                                           0.0s
 => => exporting layers                                                                                                          0.0s
 => => writing image sha256:29c6ca07acc94df7668c8e8571b9ea7cbd67d2acd1093346dcb2c70bc606ad9c                                     0.0s
 => => naming to docker.io/library/course_practical_guide_eks_front-end                                                          0.0s
WARNING: compose.service.ensure_image_exists: Image for service front-end was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
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
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.project._get_convergence_plans: proxy has upstream changes (resources-api, inventory-api, front-end)
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
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>, <Service: resources-api>, <Service: renting-api>, <Service: front-end>, <Service: clients-api>}
compose.parallel.feed_queue: Starting producer thread for <Service: resources-api>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for <Service: renting-api>
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for <Service: front-end>
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for <Service: clients-api>
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=renting-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_resources-api_1 ... 
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='resources-api', number=1)}
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='resources-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_renting-api_1   ... 
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=front-end', 'com.docker.compose.oneoff=False']})
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='renting-api', number=1)}
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='renting-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_front-end_1     ... 
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_resources-api')
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=True, filters={'label': ['com.docker.compose.project=coursepracticalguideeks', 'com.docker.compose.service=clients-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_renting-api')
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='front-end', number=1)}
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='front-end', number=1)
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 0 items)
Creating course_practical_guide_eks_clients-api_1   ... 
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
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_front-end')
compose.parallel.feed_queue: Pending: {ServiceName(project='course_practical_guide_eks', service='clients-api', number=1)}
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_resources-api')
compose.parallel.feed_queue: Starting producer thread for ServiceName(project='course_practical_guide_eks', service='clients-api', number=1)
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_clients-api')
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
compose.service.build_container_labels: Added config hash: 1912f7967cf58f808f7b5c741493a22c54b821d33ee4443b5010b39f8b24c288
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'5000/tcp': ['5000']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'5000/tcp': [{'HostIp': '', 'HostPort': '5000'}]},
 'VolumesFrom': []}
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
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['DYNAMODB_TABLE=development-resources', 'AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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', 'AWS_XRAY_SDK_ENABLED=false'], ports=[('5000', 'tcp')], volumes={}, name='course_practical_guide_eks_resources-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'resources-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': '1912f7967cf58f808f7b5c741493a22c54b821d33ee4443b5010b39f8b24c288'}, image='course_practical_guide_eks_resources-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'5000/tcp': [{'HostIp': '', 'HostPort': '5000'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['resources-api'], 'IPAMConfig': {}}}})
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
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_front-end')
compose.cli.verbose_proxy.proxy_callable: docker inspect_image <- ('course_practical_guide_eks_clients-api')
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
compose.service.build_container_labels: Added config hash: f273140484adcfea4db2886a8d55a0c60c5faaf5d12b0596c59dd4efd8a6d857
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'80/tcp': ['5002']}, binds=['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '5002'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (ports=[('80', 'tcp')], volumes={'/usr/share/nginx/html/assets/json/config.json': {}}, name='course_practical_guide_eks_front-end_1', detach=True, environment=[], labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'front-end', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'f273140484adcfea4db2886a8d55a0c60c5faaf5d12b0596c59dd4efd8a6d857'}, image='course_practical_guide_eks_front-end', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/front-end-config.json:/usr/share/nginx/html/assets/json/config.json:rw'], 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '5002'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['front-end'], 'IPAMConfig': {}}}})
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e')
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
compose.service.build_container_labels: Added config hash: c1c2e984d68b373819dbf19cc5725e33a0fa4f0e45c599369b9cfcda82e419d9
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'5003/tcp': ['5003']}, binds=[], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': [],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'5003/tcp': [{'HostIp': '', 'HostPort': '5003'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (environment=['AWS_DEFAULT_REGION=us-east-1', 'AWS_ACCESS_KEY_ID=AKIAY4SYI7JUX2KZPDMN', 'AWS_SECRET_ACCESS_KEY=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'], ports=[('5003', 'tcp')], volumes={}, name='course_practical_guide_eks_clients-api_1', detach=True, labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'clients-api', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'c1c2e984d68b373819dbf19cc5725e33a0fa4f0e45c599369b9cfcda82e419d9'}, image='course_practical_guide_eks_clients-api', host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': [], 'PortBindings': {'5003/tcp': [{'HostIp': '', 'HostPort': '5003'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['clients-api'], 'IPAMConfig': {}}}})
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
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e', 'course_practical_guide_eks_default')
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '549149d26ea813228cfdf0c03cc5d4c954a78f1334a384ccf3c14f7339bd272c',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('549149d26ea813228cfdf0c03cc5d4c954a78f1334a384ccf3c14f7339bd272c')
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e', 'course_practical_guide_eks_default', aliases=['395908a5274e', 'resources-api'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
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
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('549149d26ea813228cfdf0c03cc5d4c954a78f1334a384ccf3c14f7339bd272c', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('549149d26ea813228cfdf0c03cc5d4c954a78f1334a384ccf3c14f7339bd272c', 'course_practical_guide_eks_default', aliases=['renting-api', '549149d26ea8'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '97cd517d8f395dd161994c00f43a176daeb5addd7336b6eaafd305f9f3e92701',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('97cd517d8f395dd161994c00f43a176daeb5addd7336b6eaafd305f9f3e92701')
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
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '192e4fd397a68e835ad1def0d855c5b417391a55bef398073996480ba1dc23e8',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('192e4fd397a68e835ad1def0d855c5b417391a55bef398073996480ba1dc23e8')
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('549149d26ea813228cfdf0c03cc5d4c954a78f1334a384ccf3c14f7339bd272c')
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
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('192e4fd397a68e835ad1def0d855c5b417391a55bef398073996480ba1dc23e8', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('97cd517d8f395dd161994c00f43a176daeb5addd7336b6eaafd305f9f3e92701', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('97cd517d8f395dd161994c00f43a176daeb5addd7336b6eaafd305f9f3e92701', 'course_practical_guide_eks_default', aliases=['97cd517d8f39', 'clients-api'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.parallel.feed_queue: Pending: {<Service: inventory-api>, <Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('192e4fd397a68e835ad1def0d855c5b417391a55bef398073996480ba1dc23e8', 'course_practical_guide_eks_default', aliases=['192e4fd397a6', 'front-end'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('97cd517d8f395dd161994c00f43a176daeb5addd7336b6eaafd305f9f3e92701')
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('192e4fd397a68e835ad1def0d855c5b417391a55bef398073996480ba1dc23e8')
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
compose.parallel.feed_queue: Pending: set()
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
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e')
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
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '63cf0bdbf3cd33847a9f361068df8b697ce8c9a234f5fdb3b4656983b32c66bf',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('63cf0bdbf3cd33847a9f361068df8b697ce8c9a234f5fdb3b4656983b32c66bf')
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
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('63cf0bdbf3cd33847a9f361068df8b697ce8c9a234f5fdb3b4656983b32c66bf', 'course_practical_guide_eks_default')
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker containers <- (all=False, filters={'label': ['com.docker.compose.project=course_practical_guide_eks', 'com.docker.compose.service=resources-api', 'com.docker.compose.oneoff=False']})
compose.cli.verbose_proxy.proxy_callable: docker containers -> (list with 1 items)
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('395908a5274e6c7c5c1c7c4d1a325e443f1f5d11b18d53d0e90dbaff3db0d80e')
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
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('63cf0bdbf3cd33847a9f361068df8b697ce8c9a234f5fdb3b4656983b32c66bf', 'course_practical_guide_eks_default', aliases=['63cf0bdbf3cd', 'inventory-api'], ipv4_address=None, ipv6_address=None, links=[('course_practical_guide_eks_resources-api_1', 'resources-api'), ('course_practical_guide_eks_resources-api_1', 'course_practical_guide_eks_resources-api_1'), ('course_practical_guide_eks_resources-api_1', 'resources-api_1')], link_local_ips=None)
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker start -> None
Creating course_practical_guide_eks_clients-api_1   ... done                                                                          number=1)
compose.parallel.feed_queue: Pending: set()
compose.parallel.parallel_execute_iter: Finished processing: <Service: clients-api>
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('63cf0bdbf3cd33847a9f361068df8b697ce8c9a234f5fdb3b4656983b32c66bf')
compose.parallel.feed_queue: Pending: set()
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
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: set()
compose.parallel.feed_queue: Pending: {<Service: proxy>}
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
compose.cli.verbose_proxy.proxy_callable: docker start -> None
compose.parallel.parallel_execute_iter: Finished processing: ServiceName(project='course_practical_guide_eks', service='inventory-api'
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
compose.service.build_container_labels: Added config hash: c8ae01f207fb435ca4d520f0a39afb74559a9c1e5d3cb763d07cfc9d365bacb3
compose.cli.verbose_proxy.proxy_callable: docker create_host_config <- (links=[], port_bindings={'80/tcp': ['80']}, binds=['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'], volumes_from=[], privileged=False, network_mode='course_practical_guide_eks_default', devices=None, device_requests=None, dns=None, dns_opt=None, dns_search=None, restart_policy=None, runtime=None, cap_add=None, cap_drop=None, mem_limit=None, mem_reservation=None, memswap_limit=None, ulimits=None, log_config={'Type': '', 'Config': {}}, extra_hosts=None, read_only=None, pid_mode=None, security_opt=None, ipc_mode=None, cgroup_parent=None, cpu_quota=None, shm_size=None, sysctls=None, pids_limit=None, tmpfs=None, oom_kill_disable=None, oom_score_adj=None, mem_swappiness=None, group_add=None, userns_mode=None, init=None, init_path=None, isolation=None, cpu_count=None, cpu_percent=None, nano_cpus=None, volume_driver=None, cpuset_cpus=None, cpu_shares=None, storage_opt=None, blkio_weight=None, blkio_weight_device=None, device_read_bps=None, device_read_iops=None, device_write_bps=None, device_write_iops=None, mounts=None, device_cgroup_rules=None, cpu_period=None, cpu_rt_period=None, cpu_rt_runtime=None)
compose.cli.verbose_proxy.proxy_callable: docker create_host_config -> {'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'],
 'Links': [],
 'LogConfig': {'Config': {}, 'Type': ''},
 'NetworkMode': 'course_practical_guide_eks_default',
 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '80'}]},
 'VolumesFrom': []}
compose.cli.verbose_proxy.proxy_callable: docker create_container <- (image='nginx:stable-alpine', ports=[('80', 'tcp')], volumes={'/etc/nginx/conf.d/default.conf': {}}, name='course_practical_guide_eks_proxy_1', detach=True, environment=[], labels={'com.docker.compose.project': 'course_practical_guide_eks', 'com.docker.compose.service': 'proxy', 'com.docker.compose.oneoff': 'False', 'com.docker.compose.project.working_dir': '/mnt/samsung/code/k8s/Course_Practical_Guide_EKS', 'com.docker.compose.project.config_files': 'docker-compose.yaml', 'com.docker.compose.container-number': '1', 'com.docker.compose.version': '1.29.2', 'com.docker.compose.config-hash': 'c8ae01f207fb435ca4d520f0a39afb74559a9c1e5d3cb763d07cfc9d365bacb3'}, host_config={'NetworkMode': 'course_practical_guide_eks_default', 'VolumesFrom': [], 'Binds': ['/mnt/samsung/code/k8s/Course_Practical_Guide_EKS/default.conf:/etc/nginx/conf.d/default.conf:rw'], 'PortBindings': {'80/tcp': [{'HostIp': '', 'HostPort': '80'}]}, 'Links': [], 'LogConfig': {'Type': '', 'Config': {}}}, networking_config={'EndpointsConfig': {'course_practical_guide_eks_default': {'Aliases': ['proxy'], 'IPAMConfig': {}}}})
compose.parallel.feed_queue: Pending: set()
compose.cli.verbose_proxy.proxy_callable: docker create_container -> {'Id': '5319a2719f0df2451f5e04ad4c9e3a4b82cf82c743aa2a16f1fc6f6283fe446c',
 'Warnings': []}
compose.cli.verbose_proxy.proxy_callable: docker inspect_container <- ('5319a2719f0df2451f5e04ad4c9e3a4b82cf82c743aa2a16f1fc6f6283fe446c')
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
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network <- ('5319a2719f0df2451f5e04ad4c9e3a4b82cf82c743aa2a16f1fc6f6283fe446c', 'course_practical_guide_eks_default')
compose.cli.verbose_proxy.proxy_callable: docker disconnect_container_from_network -> None
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network <- ('5319a2719f0df2451f5e04ad4c9e3a4b82cf82c743aa2a16f1fc6f6283fe446c', 'course_practical_guide_eks_default', aliases=['proxy', '5319a2719f0d'], ipv4_address=None, ipv6_address=None, links=[], link_local_ips=None)
compose.cli.verbose_proxy.proxy_callable: docker connect_container_to_network -> None
compose.cli.verbose_proxy.proxy_callable: docker start <- ('5319a2719f0df2451f5e04ad4c9e3a4b82cf82c743aa2a16f1fc6f6283fe446c')
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
WARNING: compose.service.start_container: Host is already in use by another container
Creating course_practical_guide_eks_proxy_1         ... error
compose.parallel.feed_queue: Pending: set()

ERROR: for course_practical_guide_eks_proxy_1  Cannot start service proxy: driver failed programming external connectivity on endpoint course_practical_guide_eks_proxy_1 (79f0b2dba13e5ed6d5d6ce2f6c1e233df7d8c675107e5921c383252abb23bcfe): Error starting userland proxy: listen tcp4 0.0.0.0:80: bind: address already in use
compose.parallel.parallel_execute_iter: Failed: <Service: proxy>
compose.parallel.feed_queue: Pending: set()

ERROR: for proxy  Cannot start service proxy: driver failed programming external connectivity on endpoint course_practical_guide_eks_proxy_1 (79f0b2dba13e5ed6d5d6ce2f6c1e233df7d8c675107e5921c383252abb23bcfe): Error starting userland proxy: listen tcp4 0.0.0.0:80: bind: address already in use
ERROR: compose.cli.main.exit_with_metrics: Encountered errors while bringing up the project.
```