<h1> Webserver-configuration-using-Terraform</h1>
<h3>LAMP Stack</h3>
<p>Perform following commands to set up your LAMP stack using mysql</p>
<ul>Connect to ec2 instance
  <li>sudo apt update
</li>
  <li>sudo apt install apache2
</li>
  <li>sudo ufw app info "Apache Full"
</li>
  <li>sudo apt install mysql-server
</li>
  <ol>sudo mysql_secure_installation Note: Choose options according to your choice
</li>
  <li>sudo mysql
</li>
  <li>exit
</li>
  <li>sudo apt install php libapache2-mod-php php-mysql
</li>
  <li>sudo mkdir /var/www/your_domain
  </li><li>sudo chown -R $USER:$USER /var/www/your_domain
</li>
  <li>sudo chmod -R 755 /var/www/your_domain
</li>
  <li>nano /var/www/your_domain/index.html
</li>
  <li>Add following in the vim:
  <html>
    <head>
        <title>Welcome to Your_domain!</title>
    </head>
    <body>
        <h1>Success!  The your_domain server block is working!</h1>
    </body>
</html></li>
  <li>
  sudo nano /etc/apache2/sites-available/your_domain.conf
</li>
  <li>Add following:
  <VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName your_domain
    ServerAlias www.your_domain
    DocumentRoot /var/www/your_domain
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost></li>
  <li>sudo a2ensite your_domain.conf
</li>
  <li>sudo a2dissite 000-default.conf
</li>
  <li>sudo apache2ctl configtest
</li>
  <li>sudo systemctl restart apache2
</li>
  <li>Goto http://your_domain/http://Public_IP</li>
  <ul>
    <H4>RESULTS</h4>
<img src=\>
