# MEGA Rehberi
## İndirme
MEGA'yı indirmek için (https://www.megasoftware.net) bağlantısına gidin ve sistem özelliklerinizi seçtikten sonra "DOWNLOAD" butonuna tıklayın.

![download step](images/mega_download1.png)

Gelen ekranı aşağıya indirin ve "Accept" butonuna tıklayarak devam edin.

![download step](images/mega_download2.png)

Açılan ekrandaki gerekli bilgileri kendinize uygun bir şekilde doldurun ve "DOWNLOAD" butonuna tıklayın.

![download step](images/mega_download3.png)

Açılan ekrandan indirmek istediğiniz konumu seçin ve "kaydet" seçeneğine tıklayın.

![download step](images/mega_download4.png)

Bu aşamada "Mega_setup.exe" dosyası indiriliyor olması lazım.

## Kurulum

İndirdiğiniz "Mega_setup.exe" dosyasını çift tıklayın ve "Çalıştır" seçeneğine tıklayın.

![setup step](images/mega_setup1.png)


İlk seçeneği seçerek "Next" butonuna tıklayın. 

![setup step](images/mega_setup2.png)


"Browse" butonuna tıklayarak kurulumu yapmak istediğiniz konumu seçin ve "Next" seçeneğine tıklayarak devam edin.

![setup step](images/mega_setup3.png)


"Next" seçeneğine tıklayarak devam edin.

![setup step](images/mega_setup4.png)

Seçeneklere tik atarak "Next" seçeneği ile devam edin.

![setup step](images/mega_setup5.png)

Seçeneklere tik atarak "Next" seçeneği ile devam edin.

![setup step](images/mega_setup6.png)

"Install" butonuna tıklayarak kurulumu başlatın.

![setup step](images/mega_setup7.png)

Kurulum bittikten sonra "Finish" butonuna tıklayın ve kurulumu bitirin. Kurulum bittikten sonra program artık kullanılmaya hazır.

## Analiz Materyalinin İndirilmesi

İlk olarak (https://www.ncbi.nlm.nih.gov) adresine gidin ve veri tabanı seçeneğini "Nucleotide" olarak ayarlayın. Ardından çalışmak istediğiniz diziyi "Search" kısmına yazın ve aratın. Daha sonra çıkan arama sonuçlarından birini seçin.

![fasta step](images/mega_fasta1.png)

Seçtiğiniz arama sonucunun başlığının sol üstünde yer alan "Send to:" seçeneğine tıklayın
Açılan pencereden: 
"Choose Destination" seçeneğini "File" olarak,
"Format" seçeneğini "FASTA" olarak ayarlayın ve "Create File" butonuna tıklayın.

![fasta step](images/mega_fasta2.png)

FASTA dosyası bilgisayarınızın indirilenler kısmına inmiş olmalı. Fasta dosyasını burdan kendi proje klasorünüze aktarabilirsiniz.

## Blast Analizi

İlk olarak (https://blast.ncbi.nlm.nih.gov/Blast.cgi) adresine gidin ve "Nucleotide BLAST" seçneğini seçin.

![blast step](images/mega_blast1.png)

Bu ekranda dosya seç butonuna tıklayın.
![blast step](images/mega_blast2.png)

Açılan pencereden "Tüm dosyaları göster" seçeneğine tıklayın.
![blast step](images/mega_blast3.png)

Açılan ekrandan indirdiğiniz FASTA dosyasının bulunduğu klasöre gidin; FASTA dosyasını seçin ve "Aç" butonuna tıklayın.
Böylece FASTA dosyanızı siteye analiz için yüklemiş oldunuz.
![blast step](images/mega_blast4.png)

Burdaki seçeneklerden çalışmanıza uygun arama kümesini seçin.
![blast step](images/mega_blast5.png)

Burdaki seçeneklerden de çalışmanıza uygun parametreleri seçin ve "BLAST" butonuna tıklayın.
![blast step](images/mega_blast6.png)

Bu ekranda BLAST aramasının bitmesini bekleyin.
![blast step](images/mega_blast7.png)

Arama bittikten sonra açılan ekranı aşağıya indirin ve "Sequences producing significant alignments" kısmındaki "select all" seçeneğinin tikini kaldırın ve çalışmak istediğiniz dizilerin yanındaki kutucuklara tik atın.
![blast step](images/mega_blast8.png)

Daha sonra "Download" kısmından "FASTA(complete sequence)" seçeneğine tıklayarak dosyayı indirin.
![blast step](images/mega_blast9.png)

## MEGA'yı kullanmadan önce

Blast sonuçları bilgisayarınıza txt formatında inmiş olabilir. Bu durumda öncelikle bu dosyayı FASTA formatına çevirmeliyiz. Bunun için dosyaya sağ tıklayın ve "Birlikte aç" seçeneğinden "Başka bir uygulama seç" kısmına tıklayın.
![preset step](images/mega_preset1.png)

Açılan pencereden "Not Defteri" uygulamasını seçin ve "Tamam" butonuna tıklayın.
![preset step](images/mega_preset2.png)
Böylece dosya formatı txt'den, fasta'ya dönmüş oldu.



MEGA'yı kullanmadan önce yapmanız gereken bir diğer şey de ilk indirdiğimiz FASTA dosyasındaki nükleotit dizisini kopyalamalısınız.
![preset step](images/mega_preset4.png)
Kopyaladığınız nükleotit dizisini blast sonuçlarının olduğu, son oluşturduğunuz FASTA dosyasının en altına satır başı yaparak ekleyin.
Böylece çalışmak istediğiniz nükleotit dizisini, elde ettiğiniz blast sonuçlarıyla birlikte analiz edebileceksiniz.
![preset step](images/mega_preset3.png)

## MEGA Kullanım Rehberi

Bilgisayarınıza kurduğunuz MEGA programını çalıştırın ve açılan program ekranının sol üstünde yer alan "File" kısmına tıklayın ve "Open A File/Session..." seçeneğini seçin.

![guide step](images/mega_guide1.png)

Açılan pencereden,iki fasta dosyasını birleştirerek son aşamada oluşturduğunuz fasta dosyasını seçin.

![guide step](images/mega_guide2.png)

Karşınıza gelen kutucuktan "Align" seçeneğini seçerek devam edin.
![guide step](images/mega_guide3.png)

Hizalanan nükleotit dizilerinin uzunluk farklarını mousenuzla seçin ve klavyenizdeki "DELETE" tuşuna basın.
Böylece nükleotit uzunluklarını eşitlemiş olduk.

![guide step](images/mega_guide4.png)

Şimdi görseldeki şekle tıklayın ve "Align DNA" seçeneğine tıklayın.

![guide step](images/mega_guide5.png)

Açılan penceredeki ayarları çalışmanıza uygun şekilde veya görseldeki gibi yapabilirsiniz.

![guide step](images/mega_guide6.png)

Böylece nükleotitleri hizalamış olduk.

![guide step](images/mega_guide7.png)

Şimdi sol üstteki "Data" butonundan "Export Alignment" ve "Mega Format" seçeneklerini seçin. Daha sonra verinizi kaydedeceğiniz dosya konumunu belirleyin.

![guide step](images/mega_guide8.png)

Verinizi isimlendirin ve "Ok" butonuna tıklayın.

![guide step](images/mega_guide9.png)

Karşınıza gelen kutucukta "NO" seçeneğine tıklayın.

![guide step](images/mega_guide10.png)

Daha sonra MEGA'nın ana ekranına dönün ve "PHYLOGENY" semboline tıklayın ve çalışmanıza uygun seçeneği veya görseldeki gibi "/Test Neighbor..." 2. seçeneği seçin.

![guide step](images/mega_guide11.png)

Açılan pencereden, en son MEGA'da oluşturup kaydettiğiniz meg dosyasını seçin ve "Aç" butonuna tıklayın.

![guide step](images/mega_guide12.png)

Karşınıza gelen pencereden çalışmanıza uygun parametreleri veya görseldeki parametreleri seçin.

![guide step](images/mega_guide13.png)

+ Tebrikler! Kendi filogenetik ağacınızı oluşturdunuz.

![guide step](images/mega_guide14.png)

Son olarak klavyenizin "ctrl" + "s" tuşlarına aynı anda basarak filogenetik ağacınızı kaydedebilirsiniz.

![guide step](images/mega_guide15.png)
