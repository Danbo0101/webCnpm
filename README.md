
# Subject : Chuyên đề Công Nghệ Phần Mềm
# Lecturer: Lê Hà Thanh


### Member:

- [@Phạm Hữu Ngân Phương - N19DCCN149]()
- [@Trương Hoàng Sang - N19DCCN157]()
- [@Nguyễn Trần Đức Thuận - N19DCCN203]()


# Project : Java open source e-commerce software

#           Headless commerce and Rest api for ecommerce


- Catalog
- Shopping cart
- Checkout
- Merchant
- Order
- Customer
- User

Shop Headless commerce consists of the following components:

- Spring boot Java / Spring boot backend

See the demo: 
User : http://031001.xyz/dichvu/khachhanghome.htm
Admin : http://031001.xyz/dichvu
-------------------

1.  Run from Docker images:

From the terminal:

```
docker run --name api --network=host thuanntd2001/api
```
       
2. Run sample-sites

⋅⋅⋅ Requires the java api backend to be running

```
docker run --name web --network=host thuanntd2001/web
```

Get the source code:
-------------------
Clone the repository:
     
	 $ git clone https://github.com/Danbo0101/webCnpm.git


If this is your first time using Github, review http://help.github.com to learn the basics.

You can also download the zip file containing the code from https://github.com/Danbo0101 
for each of the the projects above

To build the application:
-------------------

1. Sql(Mysql 8.4.0)


From the terminal:

	$ docker pull mysql:latest
	$ docker run -d --name mysql-container -e MYSQL_ROOT_PASSWORD=password -p 3306:3306 mysql:latest
	$ docker cp ~/webCnpm/database/datav4.sql mysql-container:/tmp/
	$ docker exec -i mysql-container mysql -u root -p password < /tmp/datav4.sql


2. backend (api)


From the terminal:

	$ cd api
	$ mvn clean install
	$ cd target 
	$ java -jar API-1.0.jar

3. Shop sample site


From the terminal:

	$ cd KinhDoanhIOT
	$ docker build -t KinhDoanhIOTImage:latest
	$ docker run --network=host --name web KinhDoanhIOTImage


Deloy project using ssh:
-------------------

1. IP_VPS
   - First, we need a VPS to have a static IP. In the project I rented an Ubuntu VPS from Vultr.
   - We can buy an additional domain name pointing to the VPS IP I just bought for convenient access later: in the project I bought from Vultr. NameCheap .
   - After that from the terminal we access via ssh with the command :
     
	$ ssh root@<IP_VPS> (Enter the ssh password provided by Vultr (service provider).
 
   - In the client, we generate the ssh key pair with the command :
     
	$ ssh-keygen

   - Copy the content of the public key (in the .pub file) into the file in the /root/.ssh/authentication_key directory, so we don't need to enter a password when ssh into the VPS as long as we keep the pirivate_key file.

2. Set up mySql

From the terminal:

	$ apt update && apt upgrade
 	$ apt install mysql
	$ mysql -u root
	$ ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
 	$ exit
	$ curl -LO https://raw.githubusercontent.com/thuanntd2001/webCnpm/main/database/datav4.sql
	$ mysql -u root -p (Enter password is password)
	$ create schema kinhdoanh;
	$ source datav4.sql
	$ exit

3. Set up Nginx

From the terminal:

	$ apt install nginx
	$ cd /etc/nginx/site-available 
	$ rm default
 	$ touch shop (Copy the content of the config-nginx file into the shop file)
	$ cd /etc/nginx/site-enable
	$ ln -s /etc/nginx/site-available/shop
	$ systemctl restart nginx


 4. Set up Docker

From the terminal:

	$ ufw allow 80
	$ apt install docker
	$ docker pull thuanntd2001/api
 	$ docker pull thuanntd2001/web
	$ docker run -d --network=host --name api thuanntd2001/api
	$ docker run -d --network=host --name web thuanntd2001/web
      

### Access the application:
-------------------

Access the headless web application at: http://localhost:8080/dichvu/khachhanghome.htm


The instructions above will let you run the application with default settings and configurations.
Please read the instructions on how to connect to MySQL, configure an email server and configure other subsystems


### How to Contribute:
-------------------
Fork the repository to your GitHub account

Clone from fork repository
-------------------

       $ git clone https://github.com/Danbo0101/webCnpm.git

Build application according to steps provided above

Create new branch in your repository
-------------------

	   $ git checkout -b branch-name


Push your changes to Shop
-------------------

Please open a PR (pull request) in order to have your changes merged to the upstream


