Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provision "shell", inline: <<-SHELL
    # Update package index
    sudo apt-get update

    # Instalamos NGINX
    sudo apt-get install -y nginx

    # Inicializamos NGINX
    sudo systemctl start nginx

    # Configura Nginx para que se inicia de manera automática. 
    sudo systemctl enable nginx

    # Creación de un documento HTML
    echo "<html><body><h1>Hello, this is a simple web page served by NGINX!</h1><h2>~Using Vagrant</h2></body></html>" | sudo tee /var/www/html/index.html
  SHELL
  #Establecemos un reenvio de puertos para que estén accesibles desde el host. 
  config.vm.network "forwarded_port", guest: 80, host: 8080
end

