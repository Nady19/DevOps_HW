First the dockerfile should look like this :

 `FROM ubuntu`
 
 `RUN sudo apt update` 
 
 `RUN sudo apt install nginx -y`
 
 `COPY ./index.html /var/www/html/`  
 
 `CMD ["nginx", "-g", "daemon off;"]`

then i built the dockerfile using 

`sudo docker build -t nady/wnginx .`

then i ran the docker image i just built

`sudo docker run -p 80:80 nady/wnginx`

then i opened another bash terminal and typed

`sudo docker ps`

here i can see my container id, to note i only need the first two digit of the id (in my case which was 71)

`sudo docker exec -it 71 sh`

from here i can get a proof that my dockerimage is running.

then i went to localhost:80 from my browser and there was my personalized image (html webpage).

# WHY

The reason why my dockerimage ran properly and gave me the output was mainly the directory.


# Reason behind the problem

In the last class we used the directory `. /src/share/nginx/html/`

we copied the index.html file of ours into this directory by simply writing `COPY ./index.html /src/share/nginx/html/`

When the dockerimage was running i had the same problem like last class,no matter how much i reloaded the localhost webpage was showing basic nginx html message.

So i googled and saw that the problem lies in the directory.

Basically what happens is whenever we build a dockerfile with nginx and run that, the nginx searches for the html file it is going to show in the directory `. /var/www/html/`

but not in the directory `. /src/share/nginx/html/`

so when i copied my html file in this  `. /src/share/nginx/html/` directory and then ran and built the dockerfile ,the dockerfile went to  `. /var/www/html/` this directory (which it usually does) and eventually found the default welcome page.

Then, after this i stopped the container using ` sudo docker stop 71` and copied my html file to  `. /var/www/html/`

`COPY ./index.html /var/www/html/`

then i rebuilt it and ran it and got the expected output with my personalized message using nginx server withoout anymore complication.

# How to find the default directory


if there are still problems occuring for anyone regarding this directory you can check where you shoukd copy your html file by simply going to the terminal and :

`sudo docker ps`

`sudo docker exec -it 71 sh`

`cd /etc/nginx/`

`ls`

`cd conf.d`

`ls`

system will show nothing.then, 

`cat nginx.conf`

scroll down to virtual host part of the code

there is a mentioning of a directory to be included `/etc/nginx/sites-enabled/`

go to this directory

`cd /etc/nginx/sites-enabled/`

`ls`

it will show a file named as `default`

`cat default`

here you can find the directory where you will be putting your personalized html file.
in my case it was `. /var/www/html/`

That's all.
