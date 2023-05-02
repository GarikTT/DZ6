1. Урок №7 "Управление пакетами. Дистрибьюция софта".
2. Цели занятия
	устанавливать софт в Linux;
	собирать из исходников;
	репозитории, yum и rpm;
	dnf;
	snap.
3. Домашнее задание : Создание своего RPM-пакета и размещение в своем репозитории
4. Устанавливаем плагин - vagrant plugin install vagrant-vbguest.
5. Для выполнения работы скачиваем Vagrantfile с дистрибутивом centos/8 и запускаем его в чистом виде.
6. Для обеспечения работы с общей папкой устанавливаем в гостевую машину плагин Virtualbox Guest Additions 6.1.38:
	1. sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
	2. sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
	3. yum update -y
7. Выходим из vagrant'a и делаем исправления в Vagrantfile -
	1. config.vm.synced_folder ".", "/home/vagrant_data",type:"virtualbox"
	2. Добавляем в секцию "config.vm.provision "shell", inline: <<-SHELL" последовательно необходимые команды
	3. Выполняем vagrant reload и получаем вновь собранный пакет RPM.
	4. Сохраняем его в общей папке и получаем все на хост-машине.
8. В файлах homework.begin.log и homework.log результат работы.
9. Все.
	