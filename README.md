# RouterSetupGuide

## Cначала обновляем пакеты
```
sudo apt update && sudo apt upgrade -y
```
![Image text](https://github.com/cybernekit/RouterSetupGuide/blob/main/img/Screenshot%20from%202022-05-17%2016-49-11.png)
## Устанавливаем docker
(не обязательно если установленный docker)
```
sudo apt-get install ca-certificates curl gnupg lsb-release -y
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io -y
```
## Устанавливаем docker-compose
(не обязательно если установлен docker-compose)
```
mkdir -p ~/.docker/cli-plugins/
curl -SL https://github.com/docker/compose/releases/download/v2.2.3/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose
chmod +x ~/.docker/cli-plugins/docker-compose
sudo chown $USER /var/run/docker.sock
```
## Клонируем репозиторий connext
```
cd ~
git clone https://github.com/connext/nxtp-router-docker-compose.git
git checkout amarok
```
## Далее заходим в файл nxtp-router-docker-compose и настраиваем config
Переименовываем ```.env.example``` на ```.env``` и ```config.example.yaml``` на  ```config.yaml``` проверяем свой файл .env
```
mv .env.example .env & mv config.example.yaml config.yaml
```
провіряємо файли
```
nano .env
```


