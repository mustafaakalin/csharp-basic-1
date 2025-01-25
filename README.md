# C# Örnek Uygulamalar 📚

Bu repo, C# programlama dili ile yazılmış çeşitli örnek uygulamalar içermektedir. Her bir örnek, belirli bir problemi çözmek için tasarlanmıştır. Aşağıda, bu örneklerin açıklamalarını ve kodlarını bulabilirsiniz. 🚀

---

## 1. Suyun Halini Belirleme Programı 💧

### Açıklama:
Bu program, kullanıcıdan alınan sıcaklık değerine göre suyun halini (katı, sıvı, gaz) belirler.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Lütfen suyun sıcaklık değerini giriniz: ");
        int sicaklik = int.Parse(Console.ReadLine());

        if (sicaklik <= 0)
        {
            Console.WriteLine("Suyun hali: Katı");
        }
        else if (sicaklik > 0 && sicaklik < 100)
        {
            Console.WriteLine("Suyun hali: Sıvı");
        }
        else
        {
            Console.WriteLine("Suyun hali: Gaz");
        }
    }
}
```

---

## 2. Burs Miktarı Hesaplama Uygulaması 💰

### Açıklama:
Bu uygulama, öğrencinin okul türüne göre burs miktarını hesaplar. Hem `if` hem de `switch` kullanılarak iki farklı çözüm sunulmuştur.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Okul türünü seçiniz:");
        Console.WriteLine("1- İlkokul");
        Console.WriteLine("2- Ortaokul");
        Console.WriteLine("3- Lise");
        Console.WriteLine("4- Üniversite");
        
        int okulTuru = int.Parse(Console.ReadLine());
        int burs = 1000;

        if (okulTuru == 2)
        {
            burs += 200;
        }
        else if (okulTuru == 3)
        {
            burs += 500;
        }
        else if (okulTuru == 4)
        {
            burs += 1000;
        }

        Console.WriteLine($"Alacağınız burs miktarı: {burs} TL");
    }
}
```

---

## 3. Satıcının Komisyonunu Hesaplayan Uygulama 💼

### Açıklama:
Bu program, satıcının yaptığı satışlara göre komisyonunu hesaplar. Satış miktarı 200 TL'yi geçerse komisyon oranı %2, aksi halde %3'tür.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("3 satış miktarını sırayla giriniz:");

        Console.Write("Satış 1: ");
        double satis1 = double.Parse(Console.ReadLine());

        Console.Write("Satış 2: ");
        double satis2 = double.Parse(Console.ReadLine());

        Console.Write("Satış 3: ");
        double satis3 = double.Parse(Console.ReadLine());

        double toplamKomisyon = 0;

        toplamKomisyon += HesaplaKomisyon(satis1);
        toplamKomisyon += HesaplaKomisyon(satis2);
        toplamKomisyon += HesaplaKomisyon(satis3);

        Console.WriteLine($"Toplam komisyon: {toplamKomisyon:F2} TL");
    }

    static double HesaplaKomisyon(double satis)
    {
        double komisyonOrani = satis <= 200 ? 0.03 : 0.02;
        double komisyon = satis * komisyonOrani;
        Console.WriteLine($"Satış: {satis}, Komisyon: {komisyon:F2} TL");
        return komisyon;
    }
}
```

---

## 4. Aylık Elektrik Faturası Hesaplama Uygulaması ⚡

### Açıklama:
Bu program, kullanıcının aylık elektrik tüketimine göre fatura tutarını hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Aylık elektrik tüketiminizi (kWh) giriniz: ");
        double tuketim = double.Parse(Console.ReadLine());

        double birimFiyat;

        if (tuketim < 150)
        {
            birimFiyat = 0.10; // 10 kuruş
        }
        else if (tuketim <= 300)
        {
            birimFiyat = 0.20; // 20 kuruş
        }
        else
        {
            birimFiyat = 0.40; // 40 kuruş
        }

        double toplamFatura = tuketim * birimFiyat;

        Console.WriteLine($"Aylık elektrik faturanız: {toplamFatura:F2} TL");
    }
}
```

---

## 5. 1'den 100'e Kadar 3'e Bölünen Sayıları Bulma 🔢

### Açıklama:
Bu program, 1'den 100'e kadar olan sayılar arasında 3'e tam bölünen sayıları ve toplam adetini bulur.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        int adet = 0;

        Console.WriteLine("1'den 100'e kadar 3'e tam bölünen sayılar:");

        for (int i = 1; i <= 100; i++)
        {
            if (i % 3 == 0)
            {
                Console.WriteLine(i);
                adet++;
            }
        }

        Console.WriteLine($"Toplam 3'e tam bölünen sayı adedi: {adet}");
    }
}
```

---

## 6. Kullanıcıdan Alınan Bir Sayıya Kadar Olan Sayıların Toplamını Hesaplama ➕

### Açıklama:
Bu program, kullanıcıdan alınan bir sayıya kadar olan sayıların toplamını hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Lütfen bir sayı giriniz: ");
        int sayi = int.Parse(Console.ReadLine());

        int toplam = 0;

        for (int i = 1; i <= sayi; i++)
        {
            toplam += i;
        }

        Console.WriteLine($"1'den {sayi}'ya kadar olan sayıların toplamı: {toplam}");
    }
}
```

---

## 7. İki Değer Arasındaki Sayıların Toplamını Hesaplama ➕

### Açıklama:
Bu program, kullanıcıdan alınan iki sayı arasındaki sayıların toplamını hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Birinci sayıyı giriniz: ");
        int sayi1 = int.Parse(Console.ReadLine());

        Console.Write("İkinci sayıyı giriniz: ");
        int sayi2 = int.Parse(Console.ReadLine());

        int toplam = 0;

        if (sayi1 > sayi2)
        {
            int temp = sayi1;
            sayi1 = sayi2;
            sayi2 = temp;
        }

        for (int i = sayi1; i <= sayi2; i++)
        {
            toplam += i;
        }

        Console.WriteLine($"{sayi1} ile {sayi2} arasındaki sayıların toplamı: {toplam}");
    }
}
```

---

## 8. Sayıların Toplamı 100'ü Geçene Kadar Girilen Sayıların Toplamını ve Adedini Gösteren Uygulama 🔢

### Açıklama:
Bu program, kullanıcıdan sayılar alır ve bu sayıların toplamı 100'ü geçene kadar devam eder. Sonunda toplam sayı adedi ve toplam değeri ekrana yazdırılır.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        int toplam = 0;
        int adet = 0;

        while (toplam <= 100)
        {
            Console.Write("Bir sayı giriniz: ");
            int sayi = int.Parse(Console.ReadLine());

            toplam += sayi;
            adet++;
        }

        Console.WriteLine($"Toplam {adet} adet sayı girildi.");
        Console.WriteLine($"Girilen sayıların toplamı: {toplam}");
    }
}
```

---

## 9. Şekillerin Alan ve Çevresini Hesaplayan Uygulama 📐

### Açıklama:
Bu program, kullanıcının seçtiği şekle (kare, dikdörtgen, üçgen) göre alan ve çevre hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Hangi şekil için işlem yapmak istiyorsunuz?");
        Console.WriteLine("1 - Kare");
        Console.WriteLine("2 - Dikdörtgen");
        Console.WriteLine("3 - Üçgen");
        int secim = int.Parse(Console.ReadLine());

        switch (secim)
        {
            case 1:
                Console.Write("Karenin bir kenar uzunluğunu giriniz: ");
                double kenar = double.Parse(Console.ReadLine());
                Console.WriteLine($"Karenin Alanı: {kenar * kenar}");
                Console.WriteLine($"Karenin Çevresi: {4 * kenar}");
                break;

            case 2:
                Console.Write("Dikdörtgenin kısa kenarını giriniz: ");
                double kisaKenar = double.Parse(Console.ReadLine());
                Console.Write("Dikdörtgenin uzun kenarını giriniz: ");
                double uzunKenar = double.Parse(Console.ReadLine());
                Console.WriteLine($"Dikdörtgenin Alanı: {kisaKenar * uzunKenar}");
                Console.WriteLine($"Dikdörtgenin Çevresi: {2 * (kisaKenar + uzunKenar)}");
                break;

            case 3:
                Console.Write("Üçgenin birinci kenar uzunluğunu giriniz: ");
                double kenar1 = double.Parse(Console.ReadLine());
                Console.Write("Üçgenin ikinci kenar uzunluğunu giriniz: ");
                double kenar2 = double.Parse(Console.ReadLine());
                Console.Write("Üçgenin üçüncü kenar uzunluğunu giriniz: ");
                double kenar3 = double.Parse(Console.ReadLine());
                double cevre = kenar1 + kenar2 + kenar3;
                Console.WriteLine($"Üçgenin Çevresi: {cevre}");
                Console.WriteLine("Üçgenin Alanını hesaplamak için bir formül seçmeniz gerekebilir.");
                break;

            default:
                Console.WriteLine("Geçersiz seçim yaptınız!");
                break;
        }
    }
}
```

---

## 10. Klavyeden Girilen 3 Sayının En Küçüğünü Bulan Program 🔍

### Açıklama:
Bu program, kullanıcıdan alınan 3 sayıdan en küçüğünü bulur.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Birinci sayıyı giriniz: ");
        int sayi1 = int.Parse(Console.ReadLine());

        Console.Write("İkinci sayıyı giriniz: ");
        int sayi2 = int.Parse(Console.ReadLine());

        Console.Write("Üçüncü sayıyı giriniz: ");
        int sayi3 = int.Parse(Console.ReadLine());

        int enKucuk = sayi1;

        if (sayi2 < enKucuk)
        {
            enKucuk = sayi2;
        }

        if (sayi3 < enKucuk)
        {
            enKucuk = sayi3;
        }

        Console.WriteLine($"En küçük sayı: {enKucuk}");
    }
}
```

---

## 11. Klavyeden 10 Rakamını Girene Kadar Sayı Alıp Ortalamayı Hesaplayan Uygulama 🔢

### Açıklama:
Bu program, kullanıcıdan 10 rakamını girene kadar sayılar alır ve bu sayıların ortalamasını hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        int toplam = 0;
        int adet = 0;
        int girilenSayi;

        do
        {
            Console.Write("Bir sayı giriniz: ");
            girilenSayi = int.Parse(Console.ReadLine());

            if (girilenSayi != 10)
            {
                toplam += girilenSayi;
                adet++;
            }

        } while (girilenSayi != 10);

        if (adet > 0)
        {
            double ortalama = (double)toplam / adet;
            Console.WriteLine($"Girilen sayıların ortalaması: {ortalama:F2}");
        }
        else
        {
            Console.WriteLine("Herhangi bir sayı girilmedi.");
        }
    }
}
```

---

## 12. Rastgele 7 Sayı Üreten ve Son Rakamı 0 Olanların Toplamını Bulan Uygulama 🎲

### Açıklama:
Bu program, rastgele 7 sayı üretir ve son rakamı 0 olan sayıların toplamını bulur.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Random random = new Random();
        int[] sayilar = new int[7];
        int toplam = 0;

        Console.WriteLine("Rastgele üretilen sayılar:");

        for (int i = 0; i < 7; i++)
        {
            sayilar[i] = random.Next(1, 1000); // 1 ile 1000 arasında rastgele bir sayı üret
            Console.WriteLine(sayilar[i]);

            if (sayilar[i] % 10 == 0) // Son rakamı 0 ise
            {
                toplam += sayilar[i];
            }
        }

        Console.WriteLine($"Son rakamı 0 olan sayıların toplamı: {toplam}");
    }
}
```

---

## 13. 1 ile 100 Arasında Rastgele Sayı Üreten ve 50 Sayısını Üretene Kadar Devam Eden Uygulama 🎲

### Açıklama:
Bu program, 1 ile 100 arasında rastgele sayılar üretir ve 50 sayısını üretene kadar devam eder.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Random random = new Random();
        int sayi;
        int sayac = 0;

        Console.WriteLine("Üretilen sayılar:");

        do
        {
            sayi = random.Next(1, 101); // 1 ile 100 arasında rastgele bir sayı üret
            Console.WriteLine(sayi);
            sayac++;
        } while (sayi != 50); // 50 üretilene kadar devam et

        Console.WriteLine($"50 sayısını üretmek için toplam {sayac} sayı üretildi.");
    }
}
```

---

## 14. Boy ve Cinsiyet Bilgisine Göre İdeal Kilo Hesaplayan Uygulama ⚖️

### Açıklama:
Bu program, kullanıcının boy ve cinsiyet bilgilerine göre ideal kilosunu hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.Write("Boyunuzu cm cinsinden giriniz: ");
        int boy = int.Parse(Console.ReadLine());

        Console.Write("Cinsiyetinizi giriniz (E/K): ");
        char cinsiyet = char.ToUpper(Console.ReadLine()[0]);

        double idealKilo = 0;

        if (boy <= 150)
        {
            idealKilo = (cinsiyet == 'K') ? 45 : 48;
        }
        else
        {
            int ekstraBoy = boy - 150;
            double ekstraKilo = (cinsiyet == 'K') ? (ekstraBoy / 2.5) * 2.2 : (ekstraBoy / 2.5) * 2.7;
            idealKilo = (cinsiyet == 'K') ? 45 + ekstraKilo : 48 + ekstraKilo;
        }

        Console.WriteLine($"İdeal kilonuz: {idealKilo:F1} kg");
    }
}
```

---

## 15. Ulaşım Türüne Göre Bilet Fiyatı Hesaplayan Uygulama ✈️

### Açıklama:
Bu program, kullanıcının seçtiği ulaşım türüne ve diğer bilgilere göre bilet fiyatını hesaplar.

### Kod:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Ulaşım türünü seçiniz:");
        Console.WriteLine("1 - Yurt İçi");
        Console.WriteLine("2 - Yurt Dışı");
        int ulasimTuru = int.Parse(Console.ReadLine());

        Console.Write("Bilet fiyatını giriniz: ");
        double biletFiyati = double.Parse(Console.ReadLine());

        Console.Write("Kaç adet bilet alacaksınız? ");
        int biletAdedi = int.Parse(Console.ReadLine());

        if (ulasimTuru == 1)
        {
            Console.Write("Uçuş günü hafta içi mi (E/H): ");
            char gun = char.ToUpper(Console.ReadLine()[0]);
            double indirim = (gun == 'E') ? 0.27 : 0.07;
            double toplamTutar = biletFiyati * biletAdedi * (1 - indirim);
            Console.WriteLine($"Toplam bilet tutarınız: {toplamTutar:F2} TL (İndirimli)");
        }
        else if (ulasimTuru == 2)
        {
            Console.WriteLine("Hedef bölgeyi seçiniz:");
            Console.WriteLine("A - Avrupa");
            Console.WriteLine("B - Asya");
            Console.WriteLine("C - Afrika");
            char bolge = char.ToUpper(Console.ReadLine()[0]);

            double zam = bolge switch
            {
                'A' => 0.27,
                'B' => 0.17,
                'C' => 0.07,
                _ => throw new Exception("Geçersiz bölge seçimi!")
            };

            double toplamTutar = biletFiyati * biletAdedi * (1 + zam);
            Console.WriteLine($"Toplam bilet tutarınız: {toplamTutar:F2} TL (Zamlı)");
        }
        else
        {
            Console.WriteLine("Geçersiz ulaşım türü seçimi!");
        }
    }
}
```

---

Tüm örnekler bu kadar! Başka bir sorunuz varsa bana sormaktan çekinmeyin. 😊