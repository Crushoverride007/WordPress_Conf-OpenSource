==Before any installation or configuration of wordpress we need to make sure we have the LAMP stack installed==

<h1> Table of content </h1>

- [Installation of WordPress](#installation-of-wordpress)
		- [Installation of wordpress](#installation-of-wordpress-1)
		- [Configuration of Config files](#configuration-of-config-files)
		- [Configuration of Database](#configuration-of-database)
		- [First-Sign on](#first-sign-on)
		- [Initiat First Sign-on](#initiat-first-sign-on)
- [Configuration of a WordPress-Theme](#configuration-of-a-wordpress-theme)
		- [Theme Setup **PART I**](#theme-setup-part-i)
		- [Template choice](#template-choice)
		- [Theme Setup **PART II**](#theme-setup-part-ii)
		- [Problems](#problems)
		- [Theme Setup **PART III**](#theme-setup-part-iii)
					- [Finalization](#finalization)



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

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160739367-234720bd-29d9-4ff6-ac78-fea6112363b8.png " width="400" />
</p>

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
<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160740345-c9a6d305-93ab-418c-aef3-6ffedfb2fd3a.png" />
</p>


- Creation of #Database

```MySQL

CREATE DATABASE wp;

```

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160740455-5a852342-f41d-45f3-be5d-db15999e1dad.png"/>
</p


### First-Sign on

After installing and configuring the wordpress, we need now to sign in from the ==browser== to continue the setup of wordpress in our localhost

> 
<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160740524-17e3574d-6790-4cfe-80be-c1e58318b328.png" />
</p>


Choose the language you prefer and ==continue==

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160740627-de1ef07b-cdce-464d-97e9-3f147e13d08d.png"/>
</p>

<br>

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961344-6b18bc60-8e98-4d14-ac01-dfcca23b9599.png" width="450"/>
</p>

Provide them with the username, database name and password you've set whilst configuring the MySQL Database

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961435-e79e08ef-0d4d-4c1d-a2b8-db764b616b52.png" width="450"/>
</p>

### Initiat First Sign-on 

To complete the setup, we need to fill last details

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961488-c45d431b-9295-406a-a601-4a6ae1efad79.png" width="450"/>
</p>
<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961507-4c644b86-f9ca-45c0-9121-9508d3cb84e0.png" width="450"/>
</p>

- Congratulations we now have successfuly installed and configured our local WordPress

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961555-3e2d59ec-7c1c-4a41-a7f7-5b0e9b7becbb.png" width="590"/>
</p>

- It is also accessible from the ip address of the Virtual Machine

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160961988-2357845e-6438-4d10-ace1-277d33417bc7.png" />
</p>

# Configuration of a WordPress-Theme

This is the default dashboard of our local WordPress 

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962034-39102caf-c20a-4df8-b6ce-f317f959f3a3.png"/>
</p>

### Theme Setup **PART I**

- First things first, we need to change the default welcome page, to a configured/pre-made template

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962067-8bb8c1af-4239-4a0d-8195-fa2aa00e5ce0.png"/>
</p>

- I afterwards add a new theme

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962099-aedd0b67-820c-4cfb-8ea9-a31b9fc1fe89.png" />
</p>

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962115-b9ff6b5d-d509-4516-9d0e-2ab8bca8c41d.png" />
</p>


### Template choice

- Before installing our theme, we need first to first a compatible theme to our needs, since this is a testing course we are free to take any themes we want, in my case i choose


<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962153-b4d557d7-1932-454e-9ab3-f6439d0b5ebe.png"/>
</p>

This is a free theme, ==good practice==.

### Theme Setup **PART II**

After brainstorming, choosing and downloading the WordPress theme, we have to upload it and install it 

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962180-468d905c-72a6-47a0-af4b-9f48db659394.png" />
</p>


### Problems

- Whilst trying to install the theme I faced a problem of uploading the file

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160962226-cf3dfaba-765d-45ac-9db9-1efd1a82e2a6.png"/>
</p>


--- 
>  fixing phase

- Config file of PHP in Apache2 `/etc/php/7.4/apache2/php.ini`

	- I opened the config file of php in apache2 
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962334-5d224760-09c4-4e33-a6e4-956906d26737.png" width=300 height=60/>
		</p>
	- Added the following lines at the bottom of the file
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962771-f9b1a210-64f1-462b-8ec8-41b510589500.png" width=300 height=100/>
		</p>
	- Saved and Quit
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962821-1e5e9c7a-9c2a-4421-9777-2343a10c11bc.png" width=300 height=50/>
		</p>
	
	---
	
- Config file of PHP in WordPress folder `/var/www/html/mywp.com/php.ini`
	- I opened the config file of php in WordPress folder
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962861-11c5fdd7-5b35-4799-ab03-5f03283d53a2.png" width=300 height=120/>
		</p>
	- Added the following lines at the top of the file
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962922-bcd51e2a-b7e0-4c77-9deb-4d62a9fb99dd.png" width=300 height=100/>
		</p>
	- Saved and Quit
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160962963-0ca01f9d-9f5e-47eb-85f5-4732b3a38155.png" width=300 height=50/>
		</p>
	
---
- Config file of .htaccess in WordPress folder `/var/www/html/mywp.com/.htaccess`
	- I opened the config file of .htaccess in WordPress folder
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160963006-a8fc68e8-fb3e-4048-8c85-74bb1ff82669.png" width=300 height=60/>
		</p>
	-  Added the following lines at the top of the file
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160963030-e302a67b-2dc0-4b07-a49f-b4db054facd1.png" width=300 height=100/>
		</p>
	- Saved and Quit
		<p align="center">
		<img src="https://user-images.githubusercontent.com/45631812/160963078-b35af856-f056-4e8a-a694-d35482f16089.png" width=300 height=50/>
		</p>

---
		
With everything being configured, we need to restart the apache2 server with 

> ```bash
> systemctl restart apache2
> ```

### Theme Setup **PART III**
	
After restarting the apache2 server, we need to continue install our theme

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160963119-ba76afde-743c-438c-a9bf-ed5f22310747.png" width=450/>
</p>


- While being redirected to the dashboard we need to activate the theme..

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160963166-149158b2-f35b-41cc-bf4a-58fc18eb159a.png"/>
</p>

###### Finalization

Congratulations we now have successfully installed, configured a WordPress Theme.

<p align="center">
<img src="https://user-images.githubusercontent.com/45631812/160963206-17c8bf8b-a278-4464-98e6-fe613cf4bdb4.png" />
</p>

