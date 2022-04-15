
# Rnaseq Hazırlama

## Sra-toolkit İndirme

Ubuntu komut satırına aşağıda verilen kodu yapıştırınız. 

```bash
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/3.0.0/sratoolkit.3.0.0-ubuntu64.tar.gz

tar -xzf sratoolkit.3.0.0-ubuntu64.tar.gz
```

## fastqc indirme 

`fastqc` rnaseq verilerinin kalite kontolünü yapmamızı sağlayan bir pakettir. Bu paket aşağıda verilen komutla indirilir. 

```bash
conda install fastqc

conda install fastqc -c bioconda -c conda-forge
```

## veri indirme 

Veri indirmek için [bu linkten](https://www.ncbi.nlm.nih.gov/sra) SRA veri tabanı açılmalıdır. 

İndirmek istediğimiz verinin ismini yazarak, çalışmaya uygun olan opsiyonlar seçilmelidir.  

![SRA'da seçilecek opsiyonlar](biyoinformatik/images/rnaseq_1.png)

Veriyi indirmek için ID'si kopyalanmalıdır.  

![Kopyalanması gereken ID](biyoinformatik/images/rnaseq_2.png)

Kopyalanan ID aşağıda belirtilen `fasterq-dump` pakedi ile indirilir. 

```bash
SRR=ERR3473047

fasterq-dump ${SRR} \
    --progress \
    --skip-technical \
    --split-files \
    --outdir data/raw/ 

```

## fastqc ile kalite kontrol

```bash
fastqc data/raw/${SRR}_1.fastq data/raw/${SRR}_2.fastq
```

