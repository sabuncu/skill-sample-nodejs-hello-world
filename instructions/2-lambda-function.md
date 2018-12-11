# Bir 'Alexa Merhaba Dünya' Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Ses Arayüzü (SA)](https://user-images.githubusercontent.com/6242253/49790785-1f51f800-fd40-11e8-9f61-5adad636aa37.png)](./1-voice-user-interface.md)
[![Lambda Fonksiyonu SEÇİLİ](https://user-images.githubusercontent.com/6242253/49790810-2bd65080-fd40-11e8-8963-dc937183a352.png)](./2-lambda-function.md)
[![SA'yı Koda Bağla](https://user-images.githubusercontent.com/6242253/49790840-3abd0300-fd40-11e8-9414-849bb162e09e.png)](./3-connect-vui-to-code.md)
[![Testler](https://user-images.githubusercontent.com/6242253/49797809-a065bb00-fd51-11e8-8ebc-c1d210e888f6.png)](./4-testing.md)
[![Uyarlamalar](https://user-images.githubusercontent.com/6242253/49790859-43add480-fd40-11e8-87e5-2daea3d4f005.png)](./5-next-steps.md)

## Amazon Web Services Altyapısı Kullanarak bir Lambda Fonksiyonunun Hazırlanması

 [Bu eğitimin ilk adımında](./1-voice-user-interface.md), Alexa yeteneğimiz için bir Ses Arayüzü geliştirdik.  Şimdiki adımda ise, [Amazon Web Services](http://aws.amazon.com) altyapısı kullanarak bir AWS Lambda fonksiyonu yaratacağız. Lambda fonksiyonları hakkında detaylı bilgiyi [burada okuyabilirsiniz (İngilizce)](http://aws.amazon.com/lambda); bu eğitim için bilmeniz gereken, kodumuzun AWS Lambda'da yer alacağıdır. Kullanıcılar Alexa yeteneğimizi kullanmak istediklerinde, gerekli etkileşimi yürüten ve kullanıcılarla konuşan, Lambda fonksiyonumuz olacaktır.

 1.  **http://aws.amazon.com sayfasına gidin ve konsola giriş yapın.** [Henüz bir AWS hesabınız bulunmuyorsa, yeni hesap açmak için bu linkdeki açıklamaları takip edin (İngilizce).](https://github.com/alexa/alexa-cookbook/tree/master/aws/set-up-aws.md)
 
     [![Developer Console](https://user-images.githubusercontent.com/6242253/49803604-54227700-fd61-11e8-9b8b-16a097d0c9c8.png)](https://console.aws.amazon.com/console/home)
    

2.  **Açılan sayfanın üst kısmında yer alan "Services" ("Hizmetler") linkini tıklayın ve ekrana gelen arama alanına "Lambda" kelimesini girin.**  Lambda hizmetini sayfanın "Compute" ("Bilgi İşleme") hizmetleri bölümünde de bulabilirsiniz.

    [![Lambda](https://user-images.githubusercontent.com/6242253/49803614-584e9480-fd61-11e8-94ca-87fa50673d73.png)](https://console.aws.amazon.com/lambda/home)

3.  **Seçili olan AWS bölgenizi kontrol edin.** AWS Lambda hizmeti, Alexa Yetenek Kiti'ni halen şu bölgelerde destekler: ABD Doğu (N. Virginia), ABD Batı (Oregon), Asya Pasifik (Tokyo) ve AB (İrlanda).  Müşterilerinize en yakın olan bölgeyi seçtiğinize emin olun. Yeteneğinizi Türkiye ya da Avrupa'dan kullanan müşterileriniz için AB İrlanda (EU Ireland) bölgesini seçin.

    ![Check Region](https://user-images.githubusercontent.com/6242253/49803618-5d134880-fd61-11e8-9cf9-67a6cef724a2.png)

4.  **Turuncu renkli "Create function" ("Fonksiyon yarat") butonunu tıklayın.** Buton ekranın üst kısmında bulunur.

    ![Create a function](https://user-images.githubusercontent.com/6242253/49803627-60a6cf80-fd61-11e8-8822-3cfb7cf9eae1.png)

5.  Açılan sayfada üç adet buton yer alacaktır: "Author from scratch" ("Sıfırdan başlayın"), "Blueprints" ("Şablonlar") ve "AWS Serverless Application Repository" ("AWS Sunucusuz Uygulama Deposu"). **"AWS Serverless Application Repository" butonunu tıklayın.**  Söz konusu depoda, yeteneğiniz için gerekli olan tüm kod mantığını içeren hazır bir uygulama bulunmaktadır.

6. **`alexa-skills-kit-nodejs-factskill` isimli uygulama deposunu aramak için arama kutusuna `fact` ("bilgi") kelimesini girin.** Arama sonuçlarının sayısını sınırlandırmak için gerekirse arama kutusuna deponun tam ismini girin.

> _Not: Söz konusu yeteneği kullanarak önce Lambda fonksiyonunu yaratacağız, sonraki adımlarımızda ise fonksiyonun kodunu değiştireceğiz._

7. **Uygulama linkini tıklayın.** Böylece Lambda fonksiyonu yaratılacak, Alexa Yetenek Kiti'ne fonksiyonu çağırma yetkisi verilecek, ve sizin için bir IAM ("Kimlik ve Erişim Yönetimi") rolü tanınacaktır.  Ayrıca ilgili GitHub deposundaki kod ve bağımlı paketler sizin birşey yapmanıza gerek kalmadan otomatik olarak yüklenecektir.

8. İsterseniz uygulamanın adını değiştirin, sonra sayfanın sağ-alt kısmındaki **"Deploy" ("Konuşlandır") butonunu tıklayın.**

9. Tüm kaynakların **CREATE_COMPLETE ("Oluşturma Tamamlandı")** durumuna gelmesini bekleyin.

10. Lambda konsoluna geçmek için **Test App ("Uygulama Testi")** butonunu tıklayın.

11. **Yeni yaratılan** fonksiyonu, üzerine tıklayarak **açın**.

12. (Opsiyonel, uygulanması önerilir) **Söz konusu Lambda fonksiyonu güvenli hale getirmek için** [bu linkdeki (İngilizce)](https://github.com/alexa/alexa-cookbook/blob/master/aws/secure-lambda-function.md) talimatları yerine getirin.

13. Sayfayı aşağı kaydırın ve **Function code ("Fonksiyon kodu")** bölümüne gelin.

11. Şu linkde bulunan Lambda fonksiyonu **açın**: [Kaynak kod dosyası](../lambda/custom/index.js). Dosyanın içeriğini kopyalayın, Lambda kod editöründe yer alan index.js dosyası üzerine yapıştırın.  Saklamayı unutmayın.

13. Sayfanın sağ-üst köşesinde bir Amazon Resource Identifier / ARN ("Amazon Kaynak Kimliği / AKK") göreceksiniz. Bu değer ilgili lambda fonksiyonu için benzersiz kimlik görevi yapar.  Bu eğitimin sonraki aşamalarında kullanmak üzere **bu ARN (AKK) değerini saklayın (bir kopyasını alın)**.

    ![Copy ARN](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/2-12-copy-ARN._TTH_.png)

[![Next](https://user-images.githubusercontent.com/6242253/49804343-60a7cf00-fd63-11e8-88bf-ee3a538967ac.png)](./3-connect-vui-to-code.md)
