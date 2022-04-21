
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

## Veri indirme 

Veri indirmek için [bu linkten](https://www.ncbi.nlm.nih.gov/sra) SRA veri tabanı açılmalıdır. 

İndirmek istenilen verinin ismi yazılararak, çalışmaya uygun olan opsiyonlar seçilmelidir.  

![SRA'da seçilecek opsiyonlar](biyoinformatik/images/rnaseq_1.png)

Veriyi indirmek için ID'si kopyalanmalıdır.  

![Kopyalanması gereken ID](biyoinformatik/images/rnaseq_2.png)

Kopyalanan ID aşağıda belirtilen `fasterq-dump` pakedi ile indirilir. 

Örnek değişken:

SRR=ERR3473047

```bash
fasterq-dump ${SRR} \
    --progress \
    --skip-technical \
    --split-files \
    --outdir data/raw/ 

```

## fastqc ile kalite kontrol

İndirilen verinin kalite kontrolü yapılır.  

```bash
fastqc data/raw/${SRR}_1.fastq data/raw/${SRR}_2.fastq
```

## Cutadapt

Cutadapt, istenmeyen dizi türlerini yüksek verimli dizileme okumalarından bulur ve kaldırır. Bunun için öncelikle `cutadapt` paketi indirilmelidir.

```bash
conda install cutadapt

conda install -c bioconda cutadapt

conda install cutadapt -c bioconda -c conda-forge
```

Paketi çalıştırmak için aşağıdaki komut kullanılmalıdır. Değişkenler örnekteki gibidir. Yapılan çalışmaya göre parametreler değişkenlik gösterir. 

SRR=ERR3473047
ADAPTER1=AGATCGGAAGAG
ADAPTER2=AGATCGGAAGAG
THREADS=4
Q1=20
Q2=20
MIN_LEN=10

```bash
cutadapt -q ${Q1} -Q ${Q2} -m ${MIN_LEN} --trim-n -Z -j ${THREADS} -a  ${ADAPTER1} -A ${ADAPTER2} -o data/processed/${SRR}_1.fastq.gz -p data/processed/${SRR}_2.fastq.gz data/raw/${SRR}_1.fastq data/raw/${SRR}_2.fastq
```

Verinin son halini görebilmek için tekrardan kalite kontrol yapılır.

```bash
fastqc data/processed/${SRR}_1.fastq.gz data/processed/${SRR}_2.fastq.gz
```