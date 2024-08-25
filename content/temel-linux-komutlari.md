# Temel Linux Komutları: Başlangıç Rehberi

Merhaba! Linux kullanmaya yeni mi başladınız? Linux terminaline yeni mi başlıyorsunuz? Bu makalede, GNU/Linux işletim sistemi üzerinde **en sık kullanılan** terminal komutlarını inceleyeceğiz.

Terminal, başta gibi karmaşık görünse de, temel komutları öğrendikçe aslında ne kadar **güçlü ve basit** bir araç olduğunu farkedeceksiniz.

## Terminal Nedir?

Terminal, **komutları doğrudan işletim sistemine iletebildiğiniz** bir arayüzdür. Terminal üzerinden dosya işlemleri yapabilir, program çalıştırabilir ve sisteminizi yönetebilirsiniz.
Haydi makalemizdeki komutları incelemeye başlayalım;

### 'ls' Komutu

'ls' komutu **"list files"** ifadesinin kısaltmasıdır. Bu komut bulunduğunuz dizindeki **dosya ve klasörlerin listelenmesini** sağlar.

```bash
$ ls
Belgeler Masaüstü Müzikler Resimler Videolar
```

### 'ls -a' Komutu

'ls -a' komutu **"list files all"** ifadesinin kısaltmasıdır. 'ls' komutundan farklı olarak bir dizindeki **tüm** dosya ve dizinleri listeler. Buna **gizli dosyalar** da dahildir.

```bash
$ ls -a
.config .gitignore .zshrc Belgeler Masaüstü Müzikler Resimler Videolar
```

### 'pwd' Komutu

'pwd' komutu **"print working directory"** ifadesinin kısaltmasıdır. Bu komutu kullanarak, terminalde o an **hangi dizinde (directory) olduğunuzu** öğrenebilirsiniz.

```bash
$ pwd
/home/ufuk
```

### 'cd' Komutu

'cd' komutu **"change directory"** ifadesinin kısaltmasıdır. Bu komut **dizinler arasında geçiş** yapabilmenizi sağlar.

```bash
$ pwd
/home/ufuk
$ cd Belgeler
$ pwd
/home/ufuk/Belgeler
$ ls
OrnekDizin OrnekBelge.txt 
```

### 'mkdir' Komutu

'mkdir' komutu **"make directory"** ifadesinin kısaltmasıdır. Bu komut **yeni bir dizin oluşturmak** için kullanılır. Örneğin, 'DenemeDizin' adında bir dizin oluşturalım;
**
```bash
$ cd Belgeler
$ ls
OrnekDizin OrnekBelge.txt 
$ mkdir DenemeDizin
$ ls
DenemeDizin OrnekDizin OrnekBelge.txt
```

### 'rmdir' Komutu

'rmdir' komutu **"remove directory"** ifadesinin kısaltmasıdır. Bu komut **boş dizinleri silmek için** kullanılır. Bu komut yalnızca içi boş olan dizinleri siler; eğer **dizin içerisinde herhangi bir dosya veya alt dizin varsa**, 'rmdir' komutu başarısız olur ve **dizini silemez**.

```bash
$ cd Belgeler
$ ls
DenemeDizin OrnekDizin OrnekBelge.txt
$ rmdir DenemeDizin
$ ls
OrnekDizin OrnekBelge.txt
```

### 'rm' Komutu

'rm' komutu **"remove"** ifadesinin kısaltmasıdır. Bu komut **dosyaları silmek** için kullanılır. Örneğin, 'Belgeler' klasörümüzün içerisindeki 'OrnekBelge.txt' dosyasını silmeyi deneyelim;

```bash
$ cd Belgeler
$ ls
OrnekDizin OrnekBelge.txt
$ rm OrnekBelge.txt
$ ls
OrnekDizin
```

### 'touch' Komutu

Bu komut genellikle **boş bir dosya oluşturmak** veya **mevcut bir dosyanın zaman damgalarını güncellemek** için kullanılır. **Dosya zaten mevcutsa,** touch komutu dosyanın değiştirilme ve erişilme zamanını günceller, ancak **içeriğini değiştirmez.** Bir dizinde boş bir dosya oluşturmak için touch komutunu kullanabilirsiniz;

```bash
$ cd Belgeler
$ ls
OrnekDizin
$ touch Ornek.txt
$ ls
OrnekDizin Ornek.txt
```

### 'mv' Komutu

'mv' komutu **"move"** ifadesinin kısaltmasıdır. Bu komut **dosyaları taşıma veya yeniden adlandırma işlemleri** için kullanılır.

```bash
$ cd Belgeler
$ ls
OrnekDizin Ornek.txt
$ mv Ornek.txt YeniOrnek.txt
$ ls
OrnekDizin YeniOrnek.txt
```

### 'cat' Komutu

'cat' komutu **"concatenate"** ifadesinin kısaltmasıdır. Bu komut genellikle **dosya içeriklerini terminalde hızlıca görmek ya da birden fazla dosyayı birleştirip tek bir dosya haline getirmek** için tercih edilir.

```bash
$ cd Belgeler
$ ls
OrnekDizin YeniOrnek.txt
$ cat YeniOrnek.txt
Merhaba, Dünya!
```

### 'echo' Komutu

Bu komut **terminale metin, değişken veya komut çıktısı yazdırmak** için kullanılır. Bu komut, özellikle betik yazarken (bash script) çıktıları kullanıcıya göstermek veya değişkenlerin değerlerini ekrana yazdırmak için oldukça kullanışlıdır. Birkaç örnek verelim;

```bash
$ echo "Merhaba, Dünya!"
Merhaba, Dünya!
```

```bash
$ echo "Bugünün tarihi: $(date)"
Bugünün tarihi: Sun Aug 25 12:34:56 UTC 2024
```

```bash
$ echo -e "Merhaba\nDünya!"
Merhaba
Dünya!
```

```bash
$ ad="Ufuk"
$ echo "Merhaba, $ad!"
Merhaba, Ufuk!
```

### 'whoami' Komutu

Bu komut **hangi kullanıcı olarak oturum açtığınızı veya şu anda hangi kullanıcı hesabını kullandığınızı** öğrenmenizi sağlar.

```bash
$ whoami
ufuk
```

### 'cal' Komutu

'cal' komutu **"calendar"** ifadesinin kısaltmasıdır. Bu komut **takvim görüntülemek** için kullanılır. Kullanıcıların takvim tarihlerini hızlıca görselleştirmelerine yardımcı olur.

```bash
$ cal 12 2024
    December 2024
Su Mo Tu We Th Fr Sa
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
29 30 31
```

### 'man' Komutu

'man' komutu **"user manual"** ifadesinin kısaltmasıdır. Bu komut terminaldeki komutlar için **ayrıntılı yardım ve belgeleri görüntülemek için kullanılır.** Bu komut, kullanıcıların bir komutun nasıl kullanılacağını, hangi seçeneklerin mevcut olduğunu ve komutun işlevlerini öğrenmelerini sağlar.

```bash
$ man ls
ls (1) - list directory contents
```

## Sonuç

Bu makalede, Linux işletim sisteminde dosya ve dizinlerle etkili bir şekilde çalışabilmek için **temel komutları** ele aldık. Öğrendiğiniz bu komutlar, terminal üzerinden dosya yönetimi ve sistem bilgisi sağlama konularında size büyük bir kolaylık sunacaktır.

Bu temel komutları öğrenmek, Linux terminalinde daha **verimli** çalışmanıza ve sistem yönetiminde daha **yetkin** olmanıza yardımcı olacaktır. Komutların işleyişini ve uygulamalarını daha iyi anlamak, günlük bilgisayar kullanımınızı önemli ölçüde **iyileştirebilir.** Gelişmiş özellikler ve komut seçeneklerini keşfederek, Linux becerilerinizi daha da geliştirebilirsiniz.

Linux terminalini öğrenme yolculuğunuzda işinize yarayabilecek başka makaleler için ana sayfaya göz atabilirsiniz. [@ufuayk](https://github.com/ufuayk)