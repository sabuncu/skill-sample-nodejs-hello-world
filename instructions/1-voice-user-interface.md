# Bir Alexa Merhaba Dünya Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Ses Arayüzü (SA)](https://user-images.githubusercontent.com/6242253/49790798-27119c80-fd40-11e8-9845-23784f825500.png)](./1-voice-user-interface.md)
[![Lambda Fonksiyonu](https://user-images.githubusercontent.com/6242253/49790804-2973f680-fd40-11e8-8932-fe79a3bff929.png)](./2-lambda-function.md)
[![SA'yı Koda Bağla](https://user-images.githubusercontent.com/6242253/49790840-3abd0300-fd40-11e8-9414-849bb162e09e.png)](./3-connect-vui-to-code.md)
[![Testler](https://user-images.githubusercontent.com/6242253/49797809-a065bb00-fd51-11e8-8ebc-c1d210e888f6.png)](./4-testing.md)
[![Uyarlamalar](https://user-images.githubusercontent.com/6242253/49790859-43add480-fd40-11e8-87e5-2daea3d4f005.png)](./5-next-steps.md)

1.  **[Amazon Alexa Geliştiricileri Ana Sayfası](http://developer.amazon.com/alexa?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs)'nı ziyaret edin.  Sayfanın sağ-üst köşesindeki "Sign In" ("Kayıt Ol") butonunu tıklayın.**
(Henüz bir Amazon hesabınız bulunmuyorsa, ücretsiz hesap açabilirsiniz.)

2.  Giriş yaptıktan sonra, farenizi ekranın sağ-üst kısmındaki **Your Alexa Consoles ("Alexa Konsollarınız")** yazısı üzerinde tutun ve açılan menüde **Skills ("Yetenekler")** linkini tıklayın.

3.  Açılan **Alexa Developer Console ("Alexa Geliştirici Konsolu")** sayfasında, sayfanın sağ tarafındaki **Create Skill ("Yetenek Yarat")** butonunu tıklayın.  (Bu yaratacağınız ilk yetenek ise, sayfanın ortasında aynı işlevi gören bir **Yetenek Yarat** butonu daha bulunacaktır.)

4.  Sonraki sayfada yeteneğinize bir **Skill name ("Yetenek adı")** verin.  Bu ad, Alexa Skills Store (Alexa Yetenek Mağazası)'nda gösterilecektir ve kullanıcılarınız yeteneğinizi bu ad ile çağıracaktır.  Yetenek adınız boşluk içerebilir.  Eğitimi basit tutmak amacıyla **Default language ("Varsayılan dil")**  için burada **English (US)** (**"İngilizce (ABD)"**) seçeneğini kullanacağız. (Başka dil seçeneklerini daha sonra ekleyebilirsiniz.)

5.  Sayfanın **Choose a model to add to your skill ("Yeteneğinize eklemek için model seçin")** kısmında, **Custom ("Özel")** modelin ön-seçimli olduğunu göreceksiniz; bu seçeneği koruyarak sayfanın sağ-üst kısmındaki **Create Skill ("Yetenek Yarat")** butonunu tıklayın.

6.  Yeni açılan **Choose a template ("Şablon seçimi")** sayfasında **Start from scratch ("Sıfırdan başlayın")** şablonunun ön-seçimli olduğunu göreceksiniz. Bu seçeneği koruyarak sayfanın sağ-üst kısmındaki **Choose ("Seçim yapın")** butonunu tıklayın.

7.  Şimdi, Alexa Geliştirici Konsolu'nun **Build ("Geliştirme")** sekmesi gösterilecektir.  **Artık yeteneğinizin ektileşim modelini geliştirmeye başlayabilirsiniz**:

    1. Soldaki navigasyon panelinde bulunan **Interaction Model ("Etkileşim Modeli")** başlığı altındaki **JSON Editor ("JSON Editörü")** sekmesini seçin.  Açılan metin panelinde gösterilen kod yerine, [Interaction Model ("Etkileşim Modeli")](../models/en-US.json) linkinde verilen kodu kopyalayıp yapıştırın.  Sayfanın sol-üst kısmında bulunan **Save Model ("Modeli Sakla")** butonunu tıklayın.
    2. Skill Invocation Name ("Yetenek Çağrı Adı")'nı değiştirmek istiyorsanız, **Invocation ("Çağırma")** sekmesini tıklayın.  **Skill Invocation Name ("Yetenek Çağrı Adı")** alanını doldurun.  Kullanıcılarınız yeteneğinizi işleme koymak için bu çağrı adını söyleyecektir.  Bu örnekteki çağrı adı 'hello world' ("merhaba dünya") olarak önceden ayarlanmıştır.
    3. "Build Model" ("Modeli Yarat") butonunu tıklayın.

    **Not:** **Intents ("Amaçlar")** ve **Slot Types ("Yuva Türleri")** alanlarının, modelinize uyguladığınız JSON Interaction Model ("JSON Etkileşim Modeli") temel alınmak üzere otomatik olarak doldurulduğunu göreceksiniz.  Bu alanlarda farklı değerler denemekten çekinmeyin.  **Amaçlar**, **Yuvalar** ve **Utterances ("Söyleyişler")** konularında daha fazla bilgi edinmek için [ilgili teknik dokümantasyon sayfamıza (İngilizce)](https://developer.amazon.com/docs/custom-skills/create-intents-utterances-and-slots.html?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) bakabilirsiniz (yeni pencere açılacaktır).

8. **Opsiyonel:** Soldaki navigasyon panelinde **Intents ("Amaçlar")** sekmesini açarak bir amaç seçin.  Yeni üretilen amaçlarınıza örnek söyleyişler ekleyin.  Belirli bir amacı kullanmaya yönelik olarak bir kullanıcı tarafından söylenmesi olası olan tüm farklı yöntemleri değerlendirin.  Sayfada bazı örnekler verilmiştir. Yaptığınız değişiklikleri tamamladıktan sonra sayfadaki **Save Model ("Modeli Sakla")** ve **Build Model ("Modeli Yarat")** butonlarını sırasıyla tıklamayı unutmayın.

9. Etkileşim modeliniz başarılı olarak yaratılırsa, bir sonraki adıma geçin.  Aksi halde bir hata mesajı gösterilecektir. Hataları çözümlemeye çalışın. Bu eğitimin sonraki adımlarında AWS geliştirici konsolunu kullanarak Lambda fonksiyonumuzu yaratacağız, fakat tarayıcınızda bu sayfayı açık tutun, çünkü [Page #3: Connect VUI to Code ("Sayfa 3: Ses Arayüzünü Koda Bağlayın")](./3-connect-vui-to-code.md) kısmında tekrar buraya döneceğiz.


     Etkileşim modelinizde bir hata ile karşılaşırsanız, çözüm için lütfen aşağıdaki adımları deneyin:

     *  **Verilen kodu doğru şekilde kopyalayıp yapıştırdınız mı?**
     *  **Etkileşim Modeli'ne yanlışlıkla fazladan karakter girmiş olabilir misiniz?**

[![Sonraki Adım](https://user-images.githubusercontent.com/6242253/49443232-f5974f00-f7dc-11e8-95cd-9561ab658856.png)](./2-lambda-function.md)
