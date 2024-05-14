# -ValerijBel_infra

# HW-001
bastion_IP = 158.160.32.173
someinternalhost_IP = 10.128.0.24

# Подключение в одну строку:
# ssh -i ~/.ssh/appuser -A -J appuser@158.160.32.173 appuser@10.128.0.24

# Подключение с помощью алиаса:

# Добавляем алиасы в конфиг vim ~/.ssh/config
# Host bastion
#   HostName 158.160.32.173
#   Port 22
#   IdentityFile ~/.ssh/appuser
#   User appuser

# Host someinternalhost
#   HostName 10.128.0.24
#   Port 22
#   IdentityFile ~/.ssh/appuser
#   User appuser
#   ProxyJump bastion

# Теперь можно подключаться к хосту за бастионом короткой командой:
# ssh someinternalhost

# Админка vpn сервера доступна по адресу https://otushw003.valerijbel.cloud

# HW-004 Основное задение
testapp_IP = 62.84.117.162
testapp_port = 9292

# HW-004 Дополнительное задание
yc compute instance create \
  --name reddit-app \
  --hostname reddit-app \
  --memory=4 \
  --create-boot-disk image-folder-id=standard-images,image-family=ubuntu-1604-lts,size=10GB \
  --network-interface subnet-name=default-ru-central1-a,nat-ip-version=ipv4 \
  --metadata serial-port-enable=1 \
  --metadata-from-file='user-data=./metadata.yaml'

# HW-005
Установили packer
Создали сервисный аккаунт
Делегировали ему права
Создали файл шаблона packer
Собрали по нему образ
Проверили образ
Изучили параметризацию фаблонов

# HW-006
Установили terraform версии 0.12.8
Настроили provider
Инициализировали конфигурацию
Добавили ресурс
Спланировали изменения
Выполнили изменения
Проверили добавление ключа для авторизации на вм
Ознакомились с работой output переменных
Проверили работу provisioners
Ознакомились с работой input переменных

# HW-007
Проверили как terraform работает с зависимостями
Подняли несколько vm
Разбили конфигурацию на файлы
Ознакомились с работой с модулями
Ознакомились с работой с окружениями

# HW-008
Настроили ansible и проверили его работу
