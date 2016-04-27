# rpi-rc522
Automatically exported from code.google.com/p/rpi-rc522

## Original  
http://rpi-rc522.googlecode.com/svn/trunk/  

## Raspberry Pi 3 Model Bの GPIOに SPI通信方式の NFCリーダライタ RFID-RC522を接続して NFCタグを読む方法

http://www.neko.ne.jp/~freewing/raspberry_pi/raspberry_pi_3_spi_nfc_rfid_rc522/  


sudo raspi-config  
enable Device Tree  
bcm2835-1.50.tar.gz  

● BCM2835制御 Cライブラリ  
cd  
wget http://www.airspayce.com/mikem/bcm2835/bcm2835-1.50.tar.gz  
tar -zxf bcm2835-1.50.tar.gz  
cd bcm2835-1.50  
./configure  
sudo make install  
  
● rpi-rc522 C言語サンプルプログラム  
cd  
sudo apt-get install subversion  
svn checkout http://rpi-rc522.googlecode.com/svn/trunk/ rpi-rc522-read-only  
cd ./rpi-rc522-read-only/rc522  
gcc config.c rfid.c rc522.c main.c -o rc522_reader -lbcm2835  
sudo cp RC522.conf /etc/  
sudo ./rc522_reader -d  

