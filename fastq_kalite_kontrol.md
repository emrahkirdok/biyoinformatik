# Kalite kontrol ders

Bu derste fastq dosyalarını indirerek, kalite kontrol işlemlerini gerçekleştireceğiz.

Bir proje dosyası oluşturalım:

```bash
mkdir Proje
```

Bu proje dosyası içerisine girelim ve verileri yükleyeceğimiz `data` klasörünü oluşturalım:

```bash
cd Proje
mkdir data
```

Şimdi aşağıdaki okumaları `data` klasörüne indirelim:

İleri okuma [ERR3473047_1.fastq](https://drive.google.com/file/d/1SCGhfWTrxr6mOxac-k4ro9qbiUNORxoq/view?usp=sharing)
Geri okuma [ERR3473047_2.fastq](https://drive.google.com/file/d/1DQYGoOP4-WUs2LGxkwH9320Wu8lEdzJ8/view?usp=sharing)

Şimdi de kullancağımız programları yükleyelim:

```bash
sudo apt-get install fastqc cutadap
```

Fastqc programını kullanarak okumalar hakkında kalite kontrol raporu oluşturabiliriz:

```
fastqc data/ERR3473047_1.fastq data/ERR3473047_2.fastq
```

Şimdi ise bu okumaları cutadapt isimli programla işleyelim:

```bash

cutadapt -q 20 -m 10 --trim-n -a AGATCGGAAGAG -A AGATCGGAAGAG -Z -j 4 -o data/ERR3473047_1_processed.fastq.gz -p data/ERR3473047_2_processed.fastq.gz data/ERR3473047_1.fastq data/ERR3473047_2.fastq

```