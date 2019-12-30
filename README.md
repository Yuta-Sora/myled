# myled
このプログラムは、Raspberry Pi 3 Model B+上のRaspbianにおいてLEDを点灯、点滅させることができます。  
## 機能紹介  
このプログラムには４つの点灯、点滅パターンがあります。  
1. 点灯（継続）  
2. 点滅(1)・・・高速点滅（20回）  
3. 点滅(2)・・・点滅（10回）  
4. 点滅(3)・・・パターン点滅（10回）  
## 使い方  
1. ディレクトリdevdri内にmyled.cとMakefileがあることを確認  
2. ターミナル上でディレクトリdevdriを開く  
3. ディレクトリdevdri内でmakeを実行  
4. sudo insmod myled.koを実行  
5. tail /var/log/messages でmajor:以下を確認  
6. 確認したメジャー番号をもとに  
   sudo mknod /dev/myled0 c 240 c  
   を実行（240は確認したメジャー番号に変更）  
7. sudo chmod 666 /dev/myled0を実行  
8. echo 1 > /dev/myled0  
   echo 0 > /dev/myled0
   echo 2 > /dev/myled0  
   echo 3 > /dev/myled0  
   echo 4 > /dev/myled0  
9. 使用後は  
   sudo rmmod myled  
   を実行しアンインストール
## License  
This software is released under the GNU General Public License v 3.0, see LICENSE.
