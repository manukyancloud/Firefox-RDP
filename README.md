# Linux'a Ceremony için RDP Masaüstü Kurulumu
# Docker 

```console
sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
# XRDP
```console
sudo apt install xfce4 xfce4-goodies -y

sudo apt install xrdp -y

sudo systemctl enable xrdp
sudo systemctl start xrdp

echo "xfce4-session" >~/.xsession

# Rdp için kullanılan portu açalım
sudo ufw allow 3389/tcp

# Firefox Tarayıcı için:
sudo apt install firefox -y

# Microsoft Remote Desktop üzerinden IP adresiniz, kullanıcı adınız -Muhtemelen root- ve VPS şifreniz ile bağlanabilirsiniz. NOT: şifreniz "." gibi harfler içeriyorsa "ç" basıp deneyin. Klavye remote desktop'ta farklıdır. 
Applications > Web Browsers > Firefox
```
# Kalan süreç aynı.
https://ceremony.union.build/ adresine gidip linux seçip bağlanın. Kodu kopyalayın ve VPS'e bu sefer SSH client ile bağlanın -Termius vb.-.


> screen -S ceremony yazıp kodu yapıştırın. Her şey doğruysa ctrl + A + D ile screen'den çıkın
> -tekrar girmek için screen -r ceremony yazmanız yeterli-

# Ceremony key'inizi katılım sonrasında VPS'ten almayı unutmayın. 
