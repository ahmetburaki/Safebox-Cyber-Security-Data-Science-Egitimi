### Birinci Ödev 

Bu kod, kullanıcıdan bir kullanıcı adı ve şifre isteyen bir giriş sistemi simüle ediyor. Ardından, "kullanici_bilgileri.txt" adlı bir dosyayı açıyor ve dosyadaki kullanıcı bilgilerini kontrol ederek giriş doğrulaması yapıyor.

Kodun çalışma mantığı şu şekildedir:

- Kullanıcıdan bir kullanıcı adı ve şifre istenir ve bu değerler "kullanici_adi" ve "sifre" değişkenlerine atanır.
- "kullanici_bilgileri.txt" adlı dosya "r" (okuma) modunda açılır ve dosyadaki her satır için bir döngü başlatılır.
- Her satır, "satir" değişkenine atanır ve "strip()" ve "split(",")" yöntemleri kullanılarak gereksiz boşluklar silinir ve kullanıcı adı, şifre gibi bilgiler virgül ile ayrılmış şekilde ayrıştırılır.
- Eğer kullanıcı adı (bilgiler[0]) ve şifre (bilgiler[1]) girilen değerlerle eşleşirse, "Giriş yapıldı." mesajı yazdırılır ve işlem sonlandırılır.
- Eğer döngü tamamlanır ve hiçbir eşleşme bulunmazsa, "Kullanıcı adı veya şifre hatalı." mesajı yazdırılır.

Bu kod, "kullanici_bilgileri.txt" dosyasında depolanan kullanıcı bilgileriyle kullanıcı girişi kontrolü yapar. Dosya formatı kullanıcı adı ve şifrenin virgülle ayrıldığı bir yapıya sahip olmalıdır.


```python
  kullanici_adi = input("Kullanıcı Adı: ")
    sifre = input("Şifre: ")

    with open("kullanici_bilgileri.txt", "r") as dosya:
        for satir in dosya:
            bilgiler = satir.strip().split(",")
            if kullanici_adi == bilgiler[0] and sifre == bilgiler[1]:
                print("Giriş yapıldı.")
                return

    print("Kullanıcı adı veya şifre hatalı.")
```
