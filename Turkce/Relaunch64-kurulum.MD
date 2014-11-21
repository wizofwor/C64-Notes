# Relaunch64 kurulumu

Relaunch64 IDE bizlere oldukça pratik bir geliştirme ortamı sunuyor. Bu dökümanda yeni başlayanlar için kurulum adımlarını basitçe anlatmaya çalıştım.
Şimdilik ihtiyaç olmadığını düşünerek cruncher eklemiyorum. Daha sonra crunher da aynı sisteme dahil edilebilir.  

### Tedarik

http://www.popelganda.de/relaunch64.html adresinden Realunch64 Windows versiyonunu indiriyoruz.
http://codebase64.org/doku.php?id=base:crossdev adresinden ACME093 win32 binary dosyasını indiriyoruz.

### Kurulum

İndirdiğimiz programlar kurulum gerektirmiyor. Ben Relaunch64.exe ve acme.exe dosyalarını istediğimiz yere kopyalayabiliyoruz. Ben dosyaları D:\ klasörüne atıyorum.

Hemen komut istemcisine geçip `d:\acme –V` yazarak kontrol ediyorum.

```This is Acme, Relase 0.93 (“Zarquon”), 11 Oct 2006
   Ported to Windows by Martin Piper```
Yanıtını aldığıma göre doğru şekilde çalışıyor.
Relaunch’a geçiyorum
Option / Pref / Compile&Run’a geliyorum. Buradaki betiği allataki gibi değitirip update script diyorum.
```D:\acme.exe --format cbm SOURCEFILE
D:\7DX\WinVICE-2.2-x64\x64.exe OUTFILE```


