Start the first container as normal. With our standard docker-compose.yml file. 

`docker-compose up -d`

The second requires a docker-compose.yml file that has been modified to run exclusive to the normal one. That is the 3.11.yml

`docker-compose -f 3.11.yml up -d`

`docker cp ./nginx-3.11.conf medic-os-three:/srv/settings/medic-core/nginx/nginx.conf && docker exec medic-os-three /boot/svc-restart medic-core`


Then you can navigate to https://localhost:444

There is a caveat to this. Since our cookies are based on the domain trying to do https://localhost in one tab and then https://localhost:444 in another will log you out of one. There are a few workaround. One tab at https://localhost and another at https://127.0.0.1:444. Another is to launch chrome with a different profile. There are other options but it is up to you. 