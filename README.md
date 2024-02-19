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
