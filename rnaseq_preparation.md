
# Rnaseq Hazırlama

## Sra-toolkit İndirme

```bash
wget https://ftp-trace.ncbi.nlm.nih.gov/sra/sdk/3.0.0/sratoolkit.3.0.0-ubuntu64.tar.gz

tar -xzf sratoolkit.3.0.0-ubuntu64.tar.gz
```

## fastqc indirme 

```bash
conda install fastqc

conda install fastqc -c bioconda -c conda-forge
```

## veri indirme 

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

