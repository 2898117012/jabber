<VirtualHost *:80>
	ServerName www.sousa.cm
	DocumentRoot d:/iwork/sousa/master
	<Directory "d:/iwork/sousa/master/">
		Options +Indexes +FollowSymLinks +MultiViews
		AllowOverride All
		Require local
	</Directory>
</VirtualHost>