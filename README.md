# nextcloud-aio-remote-reverse-proxy
nextcloud aio configuration with a remote reverse proxy 

If you want to use Nextcloud All-in-One by using its Docker imgae you can find this here:
https://github.com/nextcloud/all-in-one/

I wanted to use the Nextcloud-AIO container, but with my existing reverse proxy (nginx). It cost me a few evenings to get this working. To save others from having todo the same trouble-shooting I have documented my setup in a mindmap, as you can see below. The Image is large but for copy-pasting stuff the pdf is better.

In the mind map you can find: 
1. A network drawing showing the reverse proxy on one host (192.168.0.15) and the second different host (192.168.0.5) with the Nextcloud-aio docker container. This setup is different from the default Nextcloud-aio setup which has all functionality on the same hot under one docker daemon. But if you have a number of different websites at home, and you want to keep them seperate logically, a seperate (remote) reverseproxy is a solution. (meaning it is not on the same docker-host as the websitres themselves) 
2. In the network drawing reverse proxy and Nextcloud host are connected via tcp port 11000
3. The configuations of the reverse proxy and the docker-compose file of the Nextcloud-Aio containers that work in my setup are included, but I have also pasted them in this file https://raw.githubusercontent.com/hanscees/nextcloud-aio-remote-reverse-proxy/main/nextcloud-aoi-2024-config 
4. In the mindmap also in green the six stages you go through while doing a fresh install. For Nextcloud-Aio to work you need to have a working TLS certificate installed, or logging in as admin after the installation will fail without a clear error (that was what took me so long to find out).

The configuaration in this setup was tested on debian bookworm and also Alpine 3.19 as the Nextcloud-Aio docker host.



https://github.com/hanscees/nextcloud-aio-remote-reverse-proxy/blob/main/nextcloud-aio-docker-reverseproxy-remote.pdf

<img src="https://raw.githubusercontent.com/hanscees/nextcloud-aio-remote-reverse-proxy/main/nextcloud-aio-docker-reverseproxy-remote.png">


