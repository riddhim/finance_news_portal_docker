Steps and result:

1. Build the image from the docker file:
   
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> docker build -t finance-news:v1 .
[+] Building 90.5s (8/8) FINISHED
 => [internal] load build definition from Dockerfile                                                                      6.0s
 => => transferring dockerfile: 84B                                                                                       1.2s
 => [internal] load .dockerignore                                                                                         4.9s
 => => transferring context: 2B                                                                                           0.5s
 => [internal] load metadata for docker.io/library/nginx:alpine                                                          15.9s
 => [auth] library/nginx:pull token for registry-1.docker.io                                                              0.0s
 => [1/2] FROM docker.io/library/nginx:alpine@sha256:a59278fd22a9ght11121e190bcec8aa57b306aa3332cd9197777583beb728f59    56.5s
 => => resolve docker.io/library/nginx:alpine@sha256:a59278fd22a9ght11121e190bcec8aa57b306aa3332cd9197777583beb728f59     1.9s
 => => sha256:a59278fd22a9ght11121e190bcec8aa57b306aa3332cd9197777583beb728f59 6.70kB / 6.70kB                            0.0s
 => => sha256:2d2a2257c6e9d2e5b50d4fbeb36d8d2f355631c2a89935a425b417eb95212686 2.19kB / 2.19kB                            0.0s
 => => sha256:529b5644c430c06553d2e8082c6713fe19a4169c9dc2369cbb960081f52924ff 11.72kB / 11.72kB                          0.0s
 => => sha256:c926b61bad3b94ae7351bafd0c184c159ebf0643b085f7ef1d47ecdc7316833c 3.40MB / 3.40MB                            1.9s
 => => sha256:fed54a1dc458a7f591fa1c98666999csd655ad54d260d53691c8ef41185883d4 1.90MB / 1.90MB                            3.1s 
 => => sha256:d4735778d47c0be8db66c446904aa2ba47f3e7509c0c9c3985ecb3b96bb7179f 629B / 629B                                1.6s
 => => sha256:8695c106552e600555fefc1bc2b299b420c52583bbf537e6c0468bc7821a3f7b 955B / 955B                                2.5s
 => => extracting sha256:c926b61bad3b94ae7351bafd0c184c159ebf0643b085f7ef1d47ecdc7316833c                                14.5s
 => => sha256:dffa16519b51a7abc6df8837b2cefcdb699eedd09394ecfeff363ae5321cb7ad2 366B / 366B                                3.5s 
 => => sha256:fe117667dcd024947ead1f25ad99a5e522efcf3b7dbd0752b6fb5e73feffb407 12.65MB / 12.65MB                          9.3s 
 => => sha256:5ddd532e9cec09472cd07e594cb6dce78c43ba5248310263f8f766c74b9fb6ae 1.40kB / 1.40kB                            6.2s
 => => sha256:9e50a0e580b1e5240c8bf21f791b11fb7a8f3c04249f5db56f1bc72f2fa73929 1.21kB / 1.21kB                            6.5s
 => => extracting sha256:fed54a1dc458a7f591fa1c986669998655ad54d260d53691c8ef4841185883d4                                 2.4s
 => => extracting sha256:d4735778d47c0be8db66c446904aa2ba47f3e7509c0c9c3985ecb3b96bb7179f                                 0.1s
 => => extracting sha256:8695c106552e600555fefc1bc2b299b420c52583bbf537e6c0468bc7821a3f7b                                 0.0s
 => => extracting sha256:dffa16519b51a7abc6df8837b2cevfb699eedd09394ecfeff363ae5321cb7ad2                                 0.0s
 => => extracting sha256:9e50a0e580b1e5240c8bf21f791b11fb7a8f3c04249f5db56f1bc72f2fa73929                                 0.0s
 => => extracting sha256:5ddd532e9cec09472cd07e594cb6dce78c43ba5248310263f8f766c74b9fb6ae                                 0.0s
 => => extracting sha256:fe117667dcd0mj49cd47cead1f25ad99a5e522efcf3b7dbd0752be73feffb407                                 5.7s
 => [internal] load build context                                                                                         1.8s
 => => transferring context: 2.39kB                                                                                       0.3s
 => [2/2] COPY . /usr/share/nginx/html                                                                                    8.2s
 => exporting to image                                                                                                    1.6s
 => => exporting layers                                                                                                   1.1s
 => => writing image sha256:02df630ed1551119d69cbg8d9eff56dba7b3d51e7fe475c6fb6a45abd7e873a4                              0.0s
 => => naming to docker.io/library/finance-news:v1   


2. List all the images to verify:
                                                               
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> docker images   
REPOSITORY                    TAG       IMAGE ID       CREATED          SIZE
finance-news                  v1        02df630ed155   56 seconds ago   42.6MB
hello-world                   latest    d2c94e258dcb   8 months ago     13.3kB
gcr.io/k8s-minikube/kicbase   v0.0.39   67a4b1138d2d   9 months ago     1.05GB
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> 
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game>
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game>

3. Check before starting the container:
   
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED        STATUS                      PORTS             
                                                                                                                     NAMES
11befb1e0571   hello-world                           "/hello"                 26 hours ago   Exited (0) 26 hours ago                       
                                                                                                                     sweet_archimedes      
9978678dc53e   gcr.io/k8s-minikube/kicbase:v0.0.39   "/usr/local/bin/entr…"   7 months ago   Exited (255) 7 months ago   127.0.0.1:32772->22/tcp, 127.0.0.1:32771->2376/tcp, 127.0.0.1:32770->5000/tcp, 127.0.0.1:32769->8443/tcp, 127.0.0.1:32768->32443/tcp   minikube
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> 
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game>
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game>

4. Run the container from the image:

PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> docker run -d -p 80:80 finance-news:v1         
9347bf98081574337a25027c045d0424a7e89106d31292a04d63811249d8d9d9
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game>

5. Check if the container started properly:
   
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> docker ps -a
CONTAINER ID   IMAGE                                 COMMAND                  CREATED              STATUS                      PORTS                                                                                                                                  NAMES
9347bf980815   finance-news:v1                       "/docker-entrypoint.…"   About a minute ago   Up 42 seconds               0.0.0.0:80->80/tcp                                                                                                                     hungry_payne    
11befb1e0571   hello-world                           "/hello"                 26 hours ago         Exited (0) 26 hours ago                 
                                                                                                                           sweet_archimedes
9978678dc53e   gcr.io/k8s-minikube/kicbase:v0.0.39   "/usr/local/bin/entr…"   7 months ago         Exited (255) 7 months ago   127.0.0.1:32772->22/tcp, 127.0.0.1:32771->2376/tcp, 127.0.0.1:32770->5000/tcp, 127.0.0.1:32769->8443/tcp, 127.0.0.1:32768->32443/tcp   minikube        
PS C:\Users\H P\Desktop\Riddhi\devops\docker_game> 


**************************************************************************************
Application running from localhost:


<img width="959" alt="image" src="https://github.com/riddhim/finance_news_portal_docker/assets/46811067/1e4fa608-e101-43ba-ae1f-84a04f172420">

Built Image:


<img width="773" alt="image" src="https://github.com/riddhim/finance_news_portal_docker/assets/46811067/960aea84-dc15-4fe2-9dab-fc227fdf8ebc">


Running container:


<img width="764" alt="image" src="https://github.com/riddhim/finance_news_portal_docker/assets/46811067/c4c9ed0c-9b73-4525-9025-3d3b752d175b">


