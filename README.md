==Before any installation or configuration of wordpress we need to make sure we have the LAMP stack installed==

# Installation of WordPress
### Installation of wordpress

- After Installing the LAMP stack, we need to install wordpress.
> to do that we need to type this command
> ```Bash
> wget https://wordpress.org/latest.zip
> ```


- With that being done, we need to move the zip file into the `/var/www/html` folder, and ==UNZIP== it

here's how the `/var/www/html` looks after unzipping

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160739096-0185b442-d3a3-47c8-a0c4-d9cfb4fa1387.png"/>
</p>

### Configuration of Config files

- In addition, we need to create a config file in the sites-available folder with:
> ```Bash
> nvim /etc/apache2/sites-available/mywp.com.conf
> ```

*nvim is equivalent of vim*

Since we've already created a config file in course, we copy-pasted the same configuration and modified the content to our need, here's a screenshot of the update file `mywp.com.conf`

<img align="center" src="https://user-images.githubusercontent.com/45631812/160739367-234720bd-29d9-4ff6-ac78-fea6112363b8.png " width="400" />


### Configuration of Database


With config file, we now need to create a ==database, a user and a password== of our choice to access wordpress

> ```Bash
> mysql -h localhost -u root -p
> ```



- Creation of #User
	
```MySQL

- CREATE USER 'wp'@'localhost' IDENTIFIED WITH authentication_plugin 
BY 'Password123#@!';

- GRANT ALL PRIVILEGES ON *.* TO 'wp'@'localhost' 
IDENTIFIED BY 'Password123#@!';

```

![[Greenshot 2022-03-30 01.02.22.png]]



- Creation of #Database

```MySQL

CREATE DATABASE wp;

```

![[Greenshot 2022-03-30 01.03.44.png]]

### First-Sign on

After installing and configuring the wordpress, we need now to sign in from the ==browser== to continue the setup of wordpress in our localhost

> ![[Pasted image 20220330011357.png]]

Choose the language you prefer and ==continue==

![[Screen Shot 2022-03-28 at 18.15.09.png|250|200]]

<br>

![[Pasted image 20220330011650.png|450]]

Provide them with the username, database name and password you've set whilst configuring the MySQL Database

![[Pasted image 20220330011810.png|450]]

### Initiat First Sign-on 

To complete the setup, we need to fill last details

![[Screen Shot 2022-03-28 at 19.33.05.png|450]]
![[Screen Shot 2022-03-28 at 19.33.43.png|450]]

- Congratulations we now have successfuly installed and configured our local WordPress

![[Screen Shot 2022-03-28 at 19.35.50.png|590]]

- It is also accessible from the ip address of the Virtual Machine
![[Screen Shot 2022-03-28 at 19.40.00.png]]

# Configuration of a WordPress-Theme

This is the default dashboard of our local WordPress 
![[Pasted image 20220330012604.png]]

### Theme Setup **PART I**

- First things first, we need to change the default welcome page, to a configured/pre-made template

![[Greenshot 2022-03-30 01.28.43.png]]

- I afterwards add a new theme

![[Greenshot 2022-03-30 01.30.33.png]]

![[Greenshot 2022-03-30 01.31.48.png]]


### Template choice

- Before installing our theme, we need first to first a compatible theme to our needs, since this is a testing course we are free to take any themes we want, in my case i choose


![[Pasted image 20220330013400.png]]

This is a free theme, ==good practice==.

### Theme Setup **PART II**

After brainstorming, choosing and downloading the WordPress theme, we have to upload it and install it 

![[Greenshot 2022-03-30 01.35.47.png]]


### Problems

- Whilst trying to install the theme I faced a problem of uploading the file

![[Screen Shot 2022-03-29 at 23.35.12.png]]

--- 
>  fixing phase

- Config file of PHP in Apache2 `/etc/php/7.4/apache2/php.ini`

	- I opened the config file of php in apache2 
	 ![[Screen Shot 2022-03-29 at 23.47.39.png|400|400]]
	- Added the following lines at the bottom of the file
	 ![[Screen Shot 2022-03-29 at 23.48.03.png|400|400]]
	- Saved and Quit
	 ![[Screen Shot 2022-03-29 at 23.48.24.png|400|400]]
	
	---
	
- Config file of PHP in WordPress folder `/var/www/html/mywp.com/php.ini`
	- I opened the config file of php in WordPress folder
	![[Pasted image 20220330014532.png|400|400]]
	- Added the following lines at the top of the file
	![[Screen Shot 2022-03-29 at 23.49.06.png|400|400]]
	- Saved and Quit
	![[Screen Shot 2022-03-29 at 23.49.13.png|400|400]]
	
---
- Config file of .htaccess in WordPress folder `/var/www/html/mywp.com/.htaccess`
	- I opened the config file of .htaccess in WordPress folder
		![[Pasted image 20220330015238.png|400|400]]
	-  Added the following lines at the top of the file
		![[Screen Shot 2022-03-29 at 23.50.07.png|400|400]]
	- Saved and Quit
		![[Screen Shot 2022-03-29 at 23.50.14.png|400|400]]

---
		
With everything being configured, we need to restart the apache2 server with 

> ```bash
> systemctl restart apache2
> ```

### Theme Setup **PART III**
	
After restarting the apache2 server, we need to continue install our theme

![[Pasted image 20220330015646.png|450]]

- While being redirected to the dashboard we need to activate the theme..

![[Greenshot 2022-03-30 02.00.33.png]]

###### Finalization

Congratulations we now have successfully installed, configured a WordPress Theme.

![[Screen Shot 2022-03-29 at 23.54.17.png]]
