#Iniciamos configuración del vagrant con la version 2
Vagrant.configure("2") do |config|  
  # Especificamos que la imagen de la caja que va a utilizar. La maquina virtual va a ser la mencionada.
  config.vm.box = "ubuntu/bionic64" 
   #Utilizamos un script de shell para configurar que los comandos se ejecuten en secuencia.
  config.vm.provision "shell", inline: <<-SHELL
  #Actualizamos lista de paquetes disponibles.  
  sudo apt update 
  #Instalamos paquetes necesarios para instalar el “wrk”. build essential brinda herramientas básicas de compilación, 
  #libssl-dev se utiliza para la construcción de programas ssl, git es una herramienta de control de versión y unzip de descompresión.
    sudo apt install -y build-essential libssl-dev git unzip
    #Clonamos el repositorio de github en el directorio temporal
    git clone https://github.com/wg/wrk.git /tmp/wrk
    # Nos pasamos al directorio recién creado.
    cd /tmp/wrk
    #Compila el codigo fuente de wrk y produce el ejecutable
    make
    # Movemos el ejecutable wrk a un nuevo directorio para que este disponible globalmente.
    sudo mv /tmp/wrk/wrk /usr/local/bin/wrk
  SHELL
end

