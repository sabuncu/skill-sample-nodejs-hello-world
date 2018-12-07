# Bir Alexa Merhaba Dünya Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Voice User Interface](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/1-locked._TTH_.png)](./1-voice-user-interface.md)[![Lambda Function](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/2-on._TTH_.png)](./2-lambda-function.md)[![Connect VUI to Code](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/3-locked._TTH_.png)](./3-connect-vui-to-code.md)[![Testing](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/4-locked._TTH_.png)](./4-testing.md)[![Next Steps](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/navigation/5-locked._TTH_.png)](./5-next-steps.md)

## Amazon Web Services Altyapısı Kullanarak bir Lambda Fonksiyonunun Hazırlanması

 [Bu eğitimin ilk adımında](./1-voice-user-interface.md), Alexa yeteneğimiz için bir Ses Arayüzü geliştirdik.  Şimdiki adımda ise, [Amazon Web Services](http://aws.amazon.com) altyapısı kullanarak bir AWS Lambda fonksiyonu yaratacağız. Lambda fonksiyonları hakkında detaylı bilgiyi [burada okuyabilirsiniz (İngilizce)](http://aws.amazon.com/lambda); bu eğitim için bilmeniz gereken, kodumuzun AWS Lambda'da yer alacağıdır. Kullanıcılar Alexa yeteneğimizi kullanmak istediklerinde, gerekli etkileşimi yürüten ve kullanıcılarla konuşan, Lambda fonksiyonumuz olacaktır.

 1.  **http://aws.amazon.com sayfasına gidin ve konsola giriş yapın.**
 If you don't already have an account, you will need to create one.  [Henüz bir AWS hesabınız bulunmuyorsa, yeni hesap açmak için buradaki açıklamaları takip edin (İngilizce).](https://github.com/alexa/alexa-cookbook/tree/master/aws/set-up-aws.md)
 
    [![Developer Console](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-1-sign-in-to-the-console._TTH_.png)](https://console.aws.amazon.com/console/home)

2.  **Açılan sayfanın üst kısmında yer alan "Services" ("Hizmetler") linkini tıklayın ve ekrana gelen arama alanına "Lambda" kelimesini girin.**  Lambda hizmeti sayfanın "Compute" ("Bilgi İşleme") hizmeti bölümünde de bulunur.

    [![Lambda](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-2-services-lambda._TTH_.png)](https://console.aws.amazon.com/lambda/home)

3.  **Seçili olan AWS bölgenizi kontrol edin.** AWS Lambda hizmeti, Alexa Yetenek Kiti'ni şu bölgelerde destekler: ABD Doğu (N. Virginia), ABD Batı (Oregon), Asya Pasifik (Tokyo) ve AB (İrlanda).  Müşterilerinize en yakın olan bölgeyi seçtiğinize emin olun (yeteneğinizi Türkiye'den ya da Avrupa'dan kullanan müşterileriniz için AB İrlanda bölgesi).

    ![Check Region](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-3-check-region._TTH_.png)

4.  **Turuncu renkli "Create function" ("Fonksiyon yarat") butonunu tıklayın.** Buton ekranın üst kısmında bulunur.

    ![Create lambda function](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/2-4-create-a-lambda-function._TTH_.png)

5.  Açılan sayfada üç adet buton bulunmaktadır: "Author from scratch" ("Sıfırdan başlayın"), "Blueprints" ("Şablonlar") ve "AWS Serverless Application Repository" ("AWS Sunucusuz Uygulama Deposu"). **"AWS Sunucusuz Uygulama Deposu" butonunu tıklayın.**  Söz konusu depoda, yeteneğiniz için gerekli olan tüm kod mantığını içeren hazır bir uygulama bulunmaktadır.

6. **`alexa-skills-kit-nodejs-factskill` isimli uygulama deposunu aramak için arama kutusuna `fact` ("bilgi") kelimesini girin.** Arama sonuçlarının sayısını sınırlandırmak için gerekirse arama kutusuna deponun tam ismini girin.

> _Not: Söz konusu yeteneği kullanarak önce Lambda fonksiyonunu yaratacağız, sonraki adımlarda ise kodu değiştireceğiz._

7. **Uygulamayı tıklayın.** Böylece Lambda fonksiyonu yaratılacak, Alexa Yetenek Kiti'ne fonksiyonu çağırma yetkisi verilecek, ve sizin için bir IAM ("Kimlik ve Erişim Yönetimi") rolü tanınacaktır.  Ayrıca ilgili GitHub deposundaki kod ve bağımlı paketler sizin birşey yapmanıza gerek kalmadan otomatik olarak yüklenecektir.

8. İsterseniz uygulamanın adını değiştirin, sonra sayfanın sağ-alt kısmındaki **"Deploy" ("Konuşlandır") butonunu tıklayın.**

9. Tüm kaynakların **CREATE_COMPLETE ("Oluşturma Tamamlandı")** durumuna gelmesini bekleyin.

10. Lambda konsoluna geçmek için **Test App ("Uygulama Testi")** butonunu tıklayın.

11. **Yeni yaratılan** fonksiyonu, üzerine tıklayarak **açın**.

12. (Opsiyonel, uygulanması önerilir) **Söz konusu Lambda fonksiyonu güvenli hale getirmek için** [bu linkdeki (İngilizce)](https://github.com/alexa/alexa-cookbook/blob/master/aws/secure-lambda-function.md) talimatları yerine getirin.

13. Sayfayı aşağı kaydırın ve **Function code ("Fonksiyon kodu")** bölümüne gelin.

11. Şu linkde bulunan Lambda fonksiyonu **açın**: [Kaynak kod dosyası](../lambda/custom/index.js). Dosyanın içeriğini kopyalayın, Lambda kod editöründe yer alan index.js dosyası üzerine yapıştırın.  Saklamayı unutmayın.

13. Sayfanın sağ-üst köşesinde bir Amazon Resource Identifier / ARN ("Amazon Kaynak Kimliği / AKK") göreceksiniz. Bu değer ilgili lambda fonksiyonu için benzersiz kimlik görevi yapar.  Bu eğitimin sonraki aşamalarında kullanmak üzere **bu ARN (AKK) değerini saklayın (bir kopyasını alın)**.

    ![Copy ARN](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/2-12-copy-ARN._TTH_.png)
<!--TODO: THIS IMAGE NEEDS TO BE CUSTOMIZED FOR YOUR SKILL TEMPLATE. -->

[![Next](https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/general/buttons/button_next_connect_vui_to_code._TTH_.png)](./3-connect-vui-to-code.md)
