# Linux'a RDP Masaüstü Kurulumu

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

# microsoft Remote Desktop üzerinden bağlanabilirsiniz.
Applications > Web Browsers > Firefox
