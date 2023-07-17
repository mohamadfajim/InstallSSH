# به نام خداوند بخشنده مهربان
# حاصل چندین سال زحمت و تلاش و تجربه


سرور مورد نیاز : Ubuntu 22


 1.دستور زیر:
 
````
curl https://get.acme.sh | sh
````

================================================================================

2.دستور زیر برای نصب پنل

یوزرنیم و پسوورد دلخواه وارد کنید (برای پسوورد از کاراکتر استفاده نکنید فقط از عدد و حروف استفاده کنید)

UDPGW PORT هم عدد 7301 قرار بدید

بعد از نصب لینک پنل - نام کاربری - کلمه عبور - پورت نشان میدهد

bash <(curl -Ls https://raw.githubusercontent.com/mohamadfajim/InstallSSH/main/Ssh-User-management-main/install.sh --ipv4)

مثال لینک پنل: http://ipserver/p/index.php


================================================================================

3. وارد پنل شوید > قسمت تنظیمات > پورت SSH > پورت SSH را از عدد 22 به عدد 28 تغییر بدهید و ذخیره را بزنید


================================================================================

4. کد زیر را برای ذخیره تغییر پورت SSH وارد کنید:


systemctl restart sshd

================================================================================

5. کد های زیر را به منظور بستن آی پی های ایران برای حفاظت بیشتر از فیلتر شدن آی پی سرور وارد کنید

bash <(curl -s https://raw.githubusercontent.com/mohamadfajim/InstallSSH/main/wepn-master/wepn.sh)


اینتر بزنید > گزینه Block Iranian Websites > گزینه Block outgoing traffic from this server to Iranian Websites کلیک کنید سپس > گزینه allow arvancloud CDN and Servers انتخاب کنید سپس > گزینه allow derak Cloud CDN and Servers انتخاب کنید > حالا بر روی گزینه save settings کلیک کنید و برگردید و خارج شوید

================================================================================

6. کد زیر را بازم برای بستن ای پی های ایران به منظور حفاظت از ای پی سرور وارد کنید:


bash <(curl -s https://raw.githubusercontent.com/mohamadfajim/InstallSSH/main/Ssh-User-management-main/newblockiran.sh --ipv4)


دقت کنید پورت را میپرسد پورت 28 که ست کردید را وارد کنید > اگر گزینه ای امد روی OK و YES کلیک کنید

================================================================================

7. دوباره باز هم به کد زیر را برای بستن آی پی ایران وارد کنید

bash <(curl -s https://raw.githubusercontent.com/mohamadfajim/InstallSSH/main/Ssh-User-management-main/block-iran.sh --ipv4)


================================================================================

8. کد بستن تورنت و امثال اینها برای نخوردن ABUSE یا همان اخطار سرورتان از طرف دیتاسنتر

wget https://raw.githubusercontent.com/mohamadfajim/InstallSSH/main/blockpublictorrent-iptables-main/bt.sh && chmod +x bt.sh && bash bt.sh


================================================================================

9. باید یک سری ای پی ها و آدرس هارو ببیندید تا از خطر ABUSE در امان باشید


کد هارا دسته ای وارد کنید

sudo iptables -A OUTPUT -o eth0 -d 0.0.0.0/8 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 10.0.0.0/8 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 100.64.0.0/10 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 127.0.0.0/8 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 169.254.0.0/16 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 172.16.0.0/12 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 192.0.2.0/24 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 192.168.0.0/16 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 198.18.0.0/15 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 224.0.0.0/4 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 240.0.0.0/4 -j DROP
sudo iptables -A OUTPUT -o eth0 -d 203.0.113.0/24 -j DROP 
sudo iptables -A OUTPUT -o eth0 -d 224.0.0.0/3 -j DROP 
sudo iptables -A OUTPUT -o eth0 -d 198.51.100.0/24 -j DROP 
sudo iptables -A OUTPUT -o eth0 -d 192.88.99.0/24 -j DROP 
sudo iptables -A OUTPUT -o eth0 -d 192.0.0.0/24 -j DROP
iptables -A OUTPUT -o eth0 -d 223.202.0.0/16 -j DROP
iptables -A OUTPUT -o eth0 -d 194.5.192.0/19 -j DROP
iptables -A OUTPUT -o eth0 -d 209.237.192.0/18 -j DROP
iptables -A OUTPUT -o eth0 -d 169.254.0.0/16 -j DROP


=============================

iptables -A OUTPUT -p tcp -s 0/0 -d 10.0.0.0/8 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 172.16.0.0/12 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 192.168.0.0/16 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 100.64.0.0/10 -j DROP
iptables -A OUTPUT -p udp -s 0/0 -d 10.0.0.0/8 -j DROP
iptables -A OUTPUT -p udp -s 0/0 -d 172.16.0.0/12 -j DROP
iptables -A OUTPUT -p udp -s 0/0 -d 192.168.0.0/16 -j DROP
iptables -A OUTPUT -p udp -s 0/0 -d 100.64.0.0/10 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 141.101.78.0/23 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 173.245.48.0/20 -j DROP
iptables -A OUTPUT -p tcp -s 0/0 -d 192.0.2.0/24 -j DROP

=============================

ufw deny out from any to 10.0.0.0/8
ufw deny out from any to 172.16.0.0/12
ufw deny out from any to 192.168.0.0/16
ufw deny out from any to 100.64.0.0/10
ufw deny out from any to 141.101.78.0/23
ufw deny out from any to 173.245.48.0/20
ufw deny out from any to 192.0.2.0/24

=============================

iptables-save


کد های بالا را وارد کنید 



================================================================================

10. بستن پورت های اضافی و باز کردن پورت های لازم:


ufw allow 80/tcp
ufw allow 80/udp
ufw allow 443/tcp
ufw allow 443/udp
ufw allow 7301/tcp
ufw allow 7301/udp
ufw allow 28/tcp
ufw allow 28/udp
enable ufw

================================================================================


تا به اینجا مراحل نصب به اتمام رسیده حالا یک یوزر ساخته و متصل شوید و وارد سایت گوگل شوید اگر سایت گوگل را باز کرد که همه چیز درست است اگر باز نکرد و با خطای 403 مواجع شدید باید کد زیر را وارد کنید


curl -O https://raw.githubusercontent.com/jinwyp/one_click_script/master/install_kernel.sh && chmod +x ./install_kernel.sh && ./install_kernel.sh

مراحل نصب آن به ترتیب زیر : 

2

12

y

y

1


================================================================================
