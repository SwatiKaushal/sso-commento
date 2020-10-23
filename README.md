# sso-commento

What is Single Sign On (SSO)?
To access any secured page in a web application, the user needs to authenticate and if the user want to access multiple web applications, then the user has to login for each of those applications individually. Logging in multiple times can be eliminated with Single Sign On, i.e., user has to login only once and can access web multiple applications.

How to Enable Single Sign On?
The key for enabling Single Sign On is machineKey and authentication (forms). All the Web Applications should have the same configuration to make it work.

Steps to Implement Single Sign On in ASP.NET MVC?
 1.  Add three empty ASP.NET MVC Web Applications (SSO, WebApp1 & WebApp2) to the solution.
 2.  Write some simple forms authentication code like the below in the AccountController. For demo purposes, I am using FormsAuthentication.Authenticate method which will simply check the credentials stored in web.config and authenticates if username and the password are valid, you can also validate username and password stored in SQL Server database.
 3.  Now we need to add an html form in the login view for the users to login
 4.  Add machineKey to web.config of SSO, WebApp1 and WebApp2. You can create your own machine keys by following this or simply generate online from here. The machineKey should be added under system.web
 5.  Add forms authentication to web.config of SSO, WebApp1 and WebApp2. For WebApp1 and WebApp2 <credentials>…</credentials> is not required as we will authenticate users from only AccountController of SSO.
 6.  Add Index view for the HomeController in both WebApp1 and WebApp2 respectively.
 7.  Now browse for http://localhost/WebApp1. It will automatically redirect to http://localhost/SSO/Account/Login?ReturnUrl=%2fWebApp1%2f.
