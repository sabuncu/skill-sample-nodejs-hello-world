# Bir 'Alexa Merhaba Dünya' Yeteneği Geliştirin
<img src="https://m.media-amazon.com/images/G/01/mobile-apps/dex/alexa/alexa-skills-kit/tutorials/quiz-game/header._TTH_.png" />

## ASK KSA (Komut Satırı Arayüzü) Kullanarak Kurulum Yapmak

### Bu Bölüm Hakkında
Bu bölümdeki açıklamalara geçmeden önce, geliştirme ortamınızı hazır hale getirmiş olduğunuzu, ayrıca KSA (Komut Satırı Arayüzü) araçları ile [AWS](https://aws.amazon.com/) ve [ASK Geliştirici Ana Sayfası](https://developer.amazon.com/alexa-skills-kit?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Content&sc_detail=hello-world-nodejs-V2_CLI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Content_hello-world-nodejs-V2_CLI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) kullanımlarına bir miktar aşina olduğunuzu varsayıyoruz.  Söz konusu konuları daha detaylı anlatan  bir eğitim arıyorsanız [burayı](./1-voice-user-interface.md) tıklayın.

### Ön gereksinimler

* Node.js (v8 sürümü ya da yukarısı)
* Bir [AWS Hesabı](https://aws.amazon.com/) açın
* Bir [Amazon Geliştirici Hesabı](https://developer.amazon.com?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Content&sc_detail=hello-world-nodejs-V2_CLI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Content_hello-world-nodejs-V2_CLI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) açın
* [ASK Komut Satırı Arayüzü](https://developer.amazon.com/docs/smapi/quick-start-alexa-skills-kit-command-line-interface.html?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Content&sc_detail=hello-world-nodejs-V2_CLI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Content_hello-world-nodejs-V2_CLI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) kurulumunu yapın

### Kurulum
1. **Önemli:** KSA'nın en son sürümünü kullandığınızı teyit edin.

	```bash
	$ npm update -g ask-cli
	```

2. Bu repo'yu **kopyalayın**.

	```bash
	$ git clone https://github.com/alexa/skill-sample-nodejs-hello-world
	```

3. [ASK KSA](https://developer.amazon.com/docs/smapi/quick-start-alexa-skills-kit-command-line-interface.html?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Content&sc_detail=hello-world-nodejs-V2_CLI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Content_hello-world-nodejs-V2_CLI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs)'yı ilk defa kullanıyorsanız repo klasörüne geçin ve `ask init` komutunu çalıştırın.

	```bash
	$ cd skill-sample-nodejs-hello-world
	$ ask init
	```

4. npm bağımlılıklarını kurmak için `/lambda/custom` klasörüne geçin ve `npm install` komutunu çalıştırın.

	```bash
	$ cd lambda/custom
	$ npm install
	```

### Dağıtım

ASK KSA, **yetenek ve Lambda fonksiyonunu sizin için yaratacaktır**.
Lambda fonksiyonu için varsayılan bölge olarak `us-east-1 (Northern Virginia)` değeri kullanılacaktır.

1. Repo'nun kök dizinine geçin; dizinde 'skill.json' adında bir dosya göreceksiniz.

2. Aşağıdaki komutu çalıştırarak yetenek ve Lambda fonksiyonunun dağıtımlarını tek bir adımda yapabilirsiniz:

	```bash
	$ ask deploy
	```

### Testler

1. Testlerinizi yapabilmek için Alexa Geliştirici Konsolu'na giriş yapıp **yeteneğinizin "Test" sekmesinde "Test" anahtarını etkin hale getirmeniz gerekir**.

2. Yeteneğinizle sözlü etkileşimin simülasyonunu yapmak için aşağıdaki örneği kullanın (bu komutun çalışması birkaç dakika alabilir):

	```bash
	 $ ask simulate -l en-US -t "start Hello World"

	 ✓ Simulation created for simulation id: 4a7a9ed8-94b2-40c0-b3bd-fb63d9887fa7
	◡ Waiting for simulation response{
	  "status": "SUCCESSFUL",
	  ...
	 ```

3. "Test" anahtarını etkinleştirdiğinizde, yeteneğinizin testini geliştirici hesabınıza bağlı olan farklı cihazlardan da yapabilirsiniz.  Etkinleştirilmiş bir cihazdan, tarayıcınız vasıtasıyla [echosim.io](https://echosim.io/welcome) sitesinden ya da Amazon Mobil Uygulamanıza konuşun ve aşağıdaki cümleyi söyleyin:

	```text
	Alexa, start hello world
	```
## Özelleştirme

1. `./skill.json`

   Yetenek adını, örnek terimleri, simgeleri ve test direktiflerini değiştirebilirsiniz.

   Birçok bilginin yerel ayarlara bağlı olduğunu ve her bir yerel ayar için değiştirilmesi gerektiğini hatırlatmak isteriz (örneğin en-US, en-GB, de-DE, vb).

   Detaylı bilgi için lütfen yeteneğe ait [Beyan (Manifest) Dokümentasyonu'na (İngilizce)](https://developer.amazon.com/docs/smapi/skill-manifest.html?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=hello-world-nodejs-V2_CLI-3&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_hello-world-nodejs-V2_CLI-3_Convert_WW_beginnersdevs&sc_segment=beginnersdevs) başvurun. 

2. `./lambda/custom/index.js`

   Yeteneğinizi özelleştirmek için kaynak kodunda bulunan ileti ve verileri değiştirin.


3. `./models/*.json`

	Yetenek çağrı adını ve her bir niyete karşılık gelen örnek terimleri değiştirmek için model tanımında değişiklik yapın.  Desteklediğiniz her bir yerel ayar için işlemleri tekrarlayın.

4. Değişikliklerin etkin hale gelebilmesi için yeteneğiniz ve Lambda fonksiyonunuzun tekrar dağıtımını yapmayı unutmayın.

	```bash
	$ ask deploy
	```
