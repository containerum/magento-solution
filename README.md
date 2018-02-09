# Magento

Magento is one of the most popular Open-Source CMS platforms for e-Commerce. It is used for building online stores selling both digital and non digital products.

Magento can be seamlessly integrated with many third party services like payment gateways, database applications, shipping, shipment tracking etc. The platform supports Google Analytics, Google Checkout and Google Base out-of-the-box.

### It consists of:

* Magento  
* MySQL

To launch this solution on Containerum.com sign up with the service, download and use [Containerum CLI](https://github.com/containerum/chkit) `chkit`.


1. Run the Solution with `chkit solution`:
```
chkit solution run containerum/magento-solution -e MYSQL_DATABASE=magento2 -e MYSQL_USER=magento2 -e MYSQL_PASSWORD=password
```
specify the following parameters:

* MYSQL_DATABASE database name
* MYSQL_USER database username
* MYSQL_PASSWORD database password

2. Make sure that the Solution is running:

```
$ chkit get deploy

+-------------------------+------+-------------+------+-------+-----+
|          NAME           | PODS | PODS ACTIVE | CPU  |  RAM  | AGE |
+-------------------------+------+-------------+------+-------+-----+
| solution-magento2-q23ba |    1 |           1 | 500m | 512Mi | 1d  |
| solution-mysql-q23ba    |    1 |           1 | 500m | 512Mi | 1d  |
+-------------------------+------+-------------+------+-------+-----+

```
3. Using `chkit get` get the address and the port to access the running Solution:
```
$ chkit get svc

+-------------------------+----------------+----------+-------------------+--------------+-----+
|          NAME           |   CLUSTER-IP   | EXTERNAL |       HOST        |    PORTS     | AGE |
+-------------------------+----------------+----------+-------------------+--------------+-----+
| solution-magento2-q23ba | 10.100.216.141 | true     | x3.containerum.io | 38289:80/TCP | 1d  |
| solution-mysql-q23ba    | 10.107.141.191 | false    |                -- | 3306/TCP     | 1d  |
+-------------------------+----------------+----------+-------------------+--------------+-----+
```
4. Go to `x3.containerum.io:38289` and setup Magento using UI.

Then follow the installation steps.

In step 2 enter the following parameters to launch this Solution:
* Database Server Host `10.107.141.191:3306`
* Database Server Username `magento2`
* Database Server Password `password`
* Database Name `magento2`

![](/gif/magentosln_1.gif)

In step 5 create an Admin account to manage your store:
![](/gif/magentosln_2.gif)

Done!

Your store is available at `x3.containerum.io:38289`.

You can access the Admin page to manage your store at `x3.containerum.io:38289/admin`.

![](/gif/magentosln_3.gif)
