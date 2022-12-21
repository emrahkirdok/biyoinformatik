# Hizalama ve varyant çağırma çalışması

Hizalama çalışması için öncelikle [E. coli](https://drive.google.com/file/d/1gvoOF6KXhgqUoYtCRpVRfeHQsbgla-nL/view?usp=sharing) referans genomunu `data` klasörüne indirelim.

Programlar:

```bash
sudo apt-get install bwa samtools bcftools vcftools

```

Veya conda ile yükleyin:

```bash
conda install bwa samtools bcftools vcftools
```  

## Hizalama aşaması

Ardından ilk olarak `bwa` programı ile referans genomu indeksleyelim.

```bash 
bwa index data/E_coli.fna

```

Şimdi ise ileri ve geri yönlü okumaları referans genoma hizalayalım. Unutmayın, bir ders önce işlediğimiz okumaları hizalayacağız.

İlk olarak sonuçları depolayacağımız `results` klasörünü oluşturalım:

```bash
mkdir results
``` 

Şimdi ise hizalama indeks dosyalarının oluşturalım:

```bash
 bwa aln -t 4 data/E_coli.fna data/ERR3473047_1_processed.fastq.gz > results/ERR3473047_1.sai

bwa aln -t 4 data/E_coli.fna data/ERR3473047_2_processed.fastq.gz > results/ERR3473047_2.sai

```

Bir sonraki adımda hizalama işlemini gerçekleştirelim:

```bash

bwa sampe data/E_coli.fna results/ERR3473047_1.sai results/ERR3473047_2.sai data/ERR3473047_1_processed.fastq.gz data/ERR3473047_2_processed.fastq.gz > results/ERR3473047.sam
```

Elde ettiğimiz dosya bir `sam` dosyası olacaktır.

Ama bu dosya hizalanmamış okumaları da içeriyor. Sonraki adımlara geçmek için sadee hizalanmış okumaları alalım ve sıkıştırılmış `bam` dosyası elde edelim.

```bash

samtools view -F12 -q30 -Sb results/ERR3473047.sam > results/ERR3473047.bam

```

İstersek `samtools view` komutu ile bu dosyayı inceleyebiliriz:

```bash
samtools view results/ERR3473047.bam | less
``` 

Ama istersek tüm bu adımları tek bir satıra indirgeyebiliriz:

```bash
bwa sampe data/E_coli.fna results/ERR3473047_1.sai results/ERR3473047_2.sai data/ERR3473047_1_processed.fastq.gz data/ERR3473047_2_processed.fastq.gz | samtools view -F4 -q30 -Sb > results/ERR3473047.bam

``` 

## Varyant çağırma

Varyant çağırmak için ilk olarak elde ettiğimiz bam dosyasını indeksleyip, sıralamamımz gerek

```bash
samtools sort results/ERR3473047.bam -o results/ERR3473047_sorted.bam
samtools index results/ERR3473047_sorted.bam
```

Bu işlem sonucunda `bai` uzantılı bir index dosyası oluşmalı. Bu dosya bizim için önemli. Bir yerden bir yere kopyalama esnasında, bu dosyayı da yüklemeliyiz.

Sonraki adımda ise `bcftools` programını kullanarak varyant çağırma işlemini gerçekleştirebiliriz:

```bash
 bcftools mpileup -Ov --fasta-ref data/E_coli.fna results/ERR3473047_sorted.bam | bcftools call -mv -Ov -o results/calls.vcf
```

