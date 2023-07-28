## ArasKargoAPI
Aras Kargo gönderi ve teslimat bilgilerini çekmek için ihtiyacın olan tek library.

### Özellikler
- Hızlı, class bazlı bir yapı.
- Gönderi ve teslimat bilgilerini çekme.

### Kullanım
```csharp

var aras = new ArasKargoClient("TAKIPNO");
var sonuc = aras.Al();

// Kargo İşlemleri (teslim alındı, dağıtıma çıktı vb.)
sonuc.Islemler.ForEach(x =>
{
   Console.WriteLine($"{x.Aciklama} - {x.Tarih}");
});

// Çıkış:
ÇIKIŞ ŞUBESİNDE; Kargonuz çıkış şubesinden transfer merkezine gönderilmek üzere aracımıza yüklenmiştir.  - 21.07.2023 12:23:21
YOLDA; Kargonuz çıkış transfer merkezinden varış transfer merkezine gönderiliyor. - 21.07.2023 21:01:58
YOLDA; Kargonuz çıkış transfer merkezinden varış transfer merkezine gönderiliyor. - 21.07.2023 21:05:00
YOLDA; Kargonuz çıkış transfer merkezinden varış transfer merkezine gönderiliyor. - 21.07.2023 21:54:00
TESLİMAT ŞUBESİNDE; Kargonuz transfer merkezimizden teslimat şubemize ulaşmıştır. - 24.07.2023 20:41:53

// sonuc.Gonderi ile gönderi bilgilerini (alici şube, alici isim, şube bilgileri, desi vb.) çekebilirsiniz


```

### Notlar

- Newtonsoft-Json paketini indirmeniz gerekebilir.
- Kodlar içindeki captcha code her 2 haftada bir expire yiyor. Eğer **gönderi alınamadı** hatası alıyorsanız captcha kodunu güncellemeniz gerekebilir.
- Dil seçeneği ingilizce ve türkçe olarak değiştirebilir.

### Lisans
MIT