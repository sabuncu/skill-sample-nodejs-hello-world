# Bir 'Alexa Merhaba Dünya' Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

[![Ses Arayüzü (SA)](https://user-images.githubusercontent.com/6242253/49790785-1f51f800-fd40-11e8-9f61-5adad636aa37.png)](./1-voice-user-interface.md)
[![Lambda Fonksiyonu](https://user-images.githubusercontent.com/6242253/49790804-2973f680-fd40-11e8-8932-fe79a3bff929.png)](./2-lambda-function.md)
[![SA'yı Koda Bağla SEÇİLİ](https://user-images.githubusercontent.com/6242253/49790813-2ed14100-fd40-11e8-8f74-9f98ad6ab544.png)](./3-connect-vui-to-code.md)
[![Testler](https://user-images.githubusercontent.com/6242253/49797809-a065bb00-fd51-11e8-8ebc-c1d210e888f6.png)](./4-testing.md)
[![Uyarlamalar](https://user-images.githubusercontent.com/6242253/49790859-43add480-fd40-11e8-87e5-2daea3d4f005.png)](./5-next-steps.md)

## Ses Arayüzünün Lambda Fonksiyonuna Bağlanması

Bu eğitimin [1. sayfasında](./1-voice-user-interface.md), kullanılmasını beklediğimiz niyet (intent) ve söyleyişler (utterances) için bir ses arayüzü geliştirdik.  Eğitimin [2. sayfasında](./2-lambda-function.md) yeteneğimizin mantığını içeren bir Lambda fonksiyonu yarattık.  Şimdi ise, söz konusu iki bileşeni birbirlerine bağlamamız gerekiyor.

1.  **[Amazon Alexa Geliştiricileri Ana Sayfası](https://developer.amazon.com/alexa/console/ask?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-3&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-3_Convert_WW_beginnersdevs&sc_segment=beginnersdevs)'nı tekrar ziyaret edin ve yeteneğinizi listeden seçin.** Not: Eğitime en başdan başladıysanız, ilgili sayfa halen tarayıcı sekmenizde açılı durumda olabilir.

2. Navigasyon panelinin sol tarafında bulunan **Endpoint (Uç Noktası)** sekmesini tıklayın.

3.  **Uç Noktası olarak "AWS Lambda ARN" ("AWS Lambda AKA - Amazon Kaynak Adı") seçeneğini seçin.**  Kodunuzu istediğiniz yerde barındırabilirsiniz, fakat basitlik ve tutumluluk adına bu eğitimde AWS Lambda hizmetini kullanacağız. ([Yeteneğiniz için gerekli olan web hizmetini kendiniz barındırmak isterseniz, bu linkdeki dokümanı okuyun (İngilizce)](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/developing-an-alexa-skill-as-a-web-service?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-3&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-3_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).)  AWS Free Tier (AWS Ücretsiz Katmanı) ile ayda 1 Milyon ücretsiz istek ve ayda 3,2 Milyon saniyeye varan compute (bilgi işleme) kotası kullanabilirsiniz. Daha fazla bilgi için [aws.amazon.com/free](https://aws.amazon.com/free/) linkini ziyaret edin. Ayrıca Amazon artık canlı yayında olan Alexa yeteneklerinin geliştiricilerine, yeteneklerinin AWS sitesindeki ilgili maliyetlerini karşılayan 
[AWS Tanıtım Kredisi](https://developer.amazon.com/alexa-skills-kit/alexa-aws-credits?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_GUI-3&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_GUI-3_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) vermektedir.

4.  Lambda kodunuzun ARN (AKA - Amazon Kaynak Adı) değerini **Default Region ("Varsayılan Bölge")** kutusuna yapıştırın.

5. Ana panelin üst kısmındaki **Save Endpoints ("Uç Noktaları Sakla")** butonunu tıklayın.

6. **Bu eğitimin 4. sayfasına ilerlemek için "Sonraki Adım" butonunu tıklayın.**

[![Next](https://user-images.githubusercontent.com/6242253/49817100-6c55be80-fd80-11e8-9ce6-9ff633e67c70.png)](./4-testing.md)
