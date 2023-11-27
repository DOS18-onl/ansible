# 1. Установили virtualbox
# 2. Установили Vagrant https://developer.hashicorp.com/vagrant/downloads
# 3. Вставили этот файл в директорию
# 4. vagrant up --provider=virtualbox
# 5. Если проблемы с загрузками - подключаем VPN и пробуем заново
# 6. vagrant ssh-config -> получаем из конфига ssh key & user'a
# 7. Заходим на машину и пользуемся :)
# 8. vagrant ssh <vagrant1-2-3> или ssh vagrant@<ip из настроек ниже> -i <путь до private_ssh_key>
VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
		config.ssh.insert_key = false
		config.vm.define "vagrant1" do |vagrant1|
		vagrant1.vm.box = "ubuntu/focal64"
		vagrant1.vm.hostname = "demo-03"
		vagrant1.vm.network :public_network, ip: '192.168.0.113'
		vagrant1.vm.network "forwarded_port", guest: 80, host: 8080
		vagrant1.vm.network "forwarded_port", guest: 443, host: 8443
	end
		config.vm.define "vagrant2" do |vagrant2|
		vagrant2.vm.box = "ubuntu/focal64"
		vagrant2.vm.hostname = "demo-02"
		vagrant2.vm.network :public_network, ip: '192.168.0.112'
		vagrant2.vm.network "forwarded_port", guest: 80, host: 8081
		vagrant2.vm.network "forwarded_port", guest: 443, host: 8444
	end
		config.vm.define "vagrant3" do |vagrant3|
		vagrant3.vm.box = "ubuntu/focal64"
		vagrant3.vm.hostname = "demo-01"
		vagrant3.vm.network :public_network, ip: '192.168.0.111'
		vagrant3.vm.network "forwarded_port", guest: 80, host: 8082
		vagrant3.vm.network "forwarded_port", guest: 443, host: 8445
	end
end
