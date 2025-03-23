using System;

// Erişim Belirleyiciler Hakkında Açıklamalar
/*
   1. public: Her yerden erişilebilir. Örneğin, bir okulun duyuru panosu herkesin erişimine açıktır.
   2. private: Sadece tanımlandığı sınıf içinde erişilebilir. Örneğin, bir çalışanın maaş bilgisi yalnızca kendisine ve muhasebeye özeldir.
   3. protected: Sadece tanımlandığı sınıf ve ondan türeyen sınıflar erişebilir. Örneğin, bir aile içinde paylaşılan özel bir şifre gibi.
   4. internal: Sadece aynı proje içinden erişilebilir. Örneğin, bir firmanın iç sisteminde çalışanlar tarafından erişilebilen belgeler gibi.
*/

class User
{
    private string adSoyad; 
    private int yas; 
    public string Email { get; set; } 

    public string GetAdSoyad()
    {
        return adSoyad;
    }

    public void SetAdSoyad(string value)
    {
        adSoyad = value;
    }

    public int GetYas()
    {
        return yas;
    }

    public void SetYas(int value)
    {
        if (value > 0) 
        {
            yas = value;
        }
        else
        {
            Console.WriteLine("Geçersiz yaş!");
        }
    }

    public void BilgileriGoster()
    {
        Console.WriteLine($"Ad Soyad: {adSoyad}, Yaş: {yas}, Email: {Email}");
    }
}

class Program
{
    static void Main()
    {
        User kullanici = new User();
      
        kullanici.SetAdSoyad("Ahmet Yılmaz");
        kullanici.SetYas(25);
        kullanici.Email = "ahmet.yilmaz@example.com";

        kullanici.BilgileriGoster();
    }
}
