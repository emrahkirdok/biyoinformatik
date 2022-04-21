# Ubuntu üzerine program kurulumu

İlk olarak ubuntu programımızı güncelleyelim:

```bash
sudo apt-get update
sudo apt-get upgrade
```

Bu komutlar uzun sürebilir. Biraz bekleyelim.

Artık istediğimiz programları kurabiliriz:

Önce `fastqc` programını kuralım:

```bash

sudo apt-get install fastqc
```

Cutadapt programı:

```bash
sudo apt-get install cutadapt
```

Şimdi de hizalama çalışmaları için gerekli programları kuralım:

```bash
sudo apt-get install bwa samtools

```