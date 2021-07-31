# DIGI+ Talent 2021

DIGI+ Talent 跨域數位人才加速躍升計畫

## Overview
本課程將以生物資訊的角度切入，對NGS(Illumina based)基因數據分析提供基本概念與實作分析進行全面介紹。主要目標是讓學員具有理論基礎及獨立的基因組分析操作能力，非常適合初學者。

課程中涵蓋關鍵概念和分析策略。 將探索由現代 DNA 定序技術帶來的一系列生物學問題，包括序列比對，遺傳變異鑑定，結構變異分析等。

---
# Course lecture silide

* [Course overview and Introduction to Linux](https://drive.google.com/drive/folders/1-6F-cK9fmOqr2-911gTH1D2s6Uabba19?usp=sharing)
* [Intruduction to NGS Technologies](https://drive.google.com/drive/folders/1-rXCqgxBli7KAJHW9hDBLAfurP9VYF-f?usp=sharing) 
* [NGS Data Format and Analysis Flow](https://drive.google.com/drive/folders/1-r5uNxmqhuKXhvT2x8f7lihp9bhCRubE?usp=sharing)
* [NGS Alignment](https://drive.google.com/drive/folders/1-kQYy-4Zp4U1svHceqA6l-2sSruGmhVx?usp=sharing)
* [NGS Variant Calling (Germline/Somatic)](https://drive.google.com/drive/folders/1-q_YLJZSmkGb1bScMbxW0B6SKUPimuil?usp=sharing)
* [NGS SV/CNV Calling](https://drive.google.com/drive/folders/1-fHz40jk_jekN7vYXRTM-AgH5Cjv9b3M?usp=sharing)
* [NGS Variant Annotation for Clinical](https://drive.google.com/drive/folders/1-TiHgZzTE8dpnA_amWY26fo4E1hnutsl?usp=sharing)

---
# Hands-On

## NCHC resource
* 計畫代號：ACD109058
* 計算資源：
  * [NCHC Taiwania 1 (台灣杉一號)](https://iservice.nchc.org.tw/)
  * Node 為 3 CPU core, 4GB RMA
* 使用方式：
  * 採 PBSpro 送 job 進行相關的分析
  * job queue 為 `ngscourse`
* 軟體安裝路徑
  * `/pkg/biology/`

### NCHC Taiwania 1 PBS Pro CLI

```bash
#!/bin/bash
#PBS -P ACD109058
#PBS -W group_list=ACD109058
#PBS -N FastQC_job
#PBS -l select=1:ncpus=3
#PBS -q ngscourse
#PBS -o /work1/ACD109058/queue_status/
#PBS -e /work1/ACD109058/queue_status/
#PBS -M philippe.lin@ailabs.tw
#PBS -m e

/path/my_program –options seq_files
```
## AWS resource

---
# Raw Data

* Whole Exome Sequencing (WES) Paired End
  * Raw reads from [precisionFDA - Hidden Treasures - Warm Up](https://precision.fda.gov/challenges/1)
    * Dataset: NA12878MOD
    * Read Length: 2x126bp
    * Insert Size: 324bp
    * Total of Sequences: 63,853,196x2
    * Instrument and Sequencing Chemistry: Illumina HiSeq 2500 using Version 4 chemistry
    * Approximate Coverage: 76x
    * The data storage path is as follows:
      * NCHC Taiwania 1
        * `/work1/ACD109058/data/NA12878MOD_1.fastq.gz`
        * `/work1/ACD109058/data/NA12878MOD_2.fastq.gz`

---
# Reference Genome
* Human
  * HG19

    `/pkg/biology/reference/Homo_sapiens/GATK/hg19/ucsc.hg19.fasta`

  * HG38

    `/pkg/biology/reference/Homo_sapiens/GATK/hg38/Homo_sapiens_assembly38.fasta`


---
# NGS Tools

* [FASTQC 0.11.9](https://www.bioinformatics.babraham.ac.uk/projects/download.html#fastqc)
* [BWA-0.7.17(r1188)](https://github.com/lh3/bwa)
* [samtools 1.13](https://github.com/samtools/samtools)
* [htslib 1.13](https://github.com/samtools/htslib)
* [bcftools 1.3](https://github.com/samtools/bcftools)
* [sambamba 0.8.0](https://github.com/biod/sambamba)
* [bedtools2 2.30.0](https://github.com/arq5x/bedtools2)
* [GATK 4.2.1.0](https://github.com/broadinstitute/gatk/releases)
* [vcftools 0.1.16](https://github.com/vcftools/vcftools)
* [JAX-CNV 1.1.0](https://github.com/wanpinglee/JAX-CNV)
* [Annovar (2019Oct24)](https://www.openbioinformatics.org/annovar/annovar_download_form.php)
* [AnnotSV v3.0.9 ](https://github.com/lgmgeo/AnnotSV)


---
# Resource

* [Linux for Biologists - Part1](https://biohpc.cornell.edu/lab/doc/linux_workshop_part1.pdf)
* [An introduction to Linux for bioinformatics](https://sites.ualberta.ca/~stothard/downloads/linux_for_bioinformatics.pdf)
* [Bioinformatics on the Command Line](https://vicbioinformatics.com/documents/command-line/#/)
* [Introduction to Linux for bioinformatics](https://www.bits.vib.be/training-list/112-bits/training/upcoming-trainings/124-linux-for-bioinformatics)
* [Broad Institute - genomics public data on Google cloud](https://console.cloud.google.com/storage/browser/genomics-public-data;tab=objects?pli=1&prefix=&forceOnObjectsSortingFiltering=false)
* [Broad Institute - bundle - Mutect2]([shorturl.at/knuN3](https://gatk.broadinstitute.org/hc/en-us/articles/360037593851-Mutect2))
* [GATK tutorial data](https://drive.google.com/drive/folders/1aBcbV_Hlyg0wOOmZDDSBeIc0uw1r3f_w)

---
# Reference

* [2020 DIGI+ Talent](https://github.com/geniusphil/digitalent/tree/main/2020)
* [2019 Genomic Epidemiology Workshop](https://github.com/geniusphil/2019GenomicsEpidemiologyWorkshop)
* [Applied Computational Genomics Course at UU](https://bioinformaticsonline.com/bookmarks/view/42468/applied-computational-genomics-course-at-uu-spring-2020)
* [GATK Resource bundle](https://gatk.broadinstitute.org/hc/en-us/articles/360035890811-Resource-bundle)