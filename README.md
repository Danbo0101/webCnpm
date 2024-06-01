
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

See the demo: http://031001.xyz/dichvu/khachhanghome.htm
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


