# 🧬 Oncology NGS Pipeline

This pipeline performs full germline/somatic variant analysis for cancer samples using WGS/WES data. It is designed for clinical/scientific applications and supports Docker and AWS Batch environments.

## 🧪 Features
- Germline & somatic SNP/Indel (GATK HaplotypeCaller / Mutect2)
- CNV detection (CNVkit or GATK CNV)
- SV detection (Manta)
- Fusion detection (STAR-Fusion, optional)
- Variant annotation (ANNOVAR, VEP)
- Clinical relevance integration (ClinVar, COSMIC, OncoKB)
- HTML + PDF reporting
- LIS-ready output

## 🚀 Quickstart
```bash
nextflow run main.nf -profile docker

## Project Structure

oncology-ngs-pipeline/
├── Dockerfile
├── Oncology-NGS-pipeline.nf   #  Nextflow 
├── nextflow.config
├── assets/
│   ├── report_template.Rmd    # Generate HTML report
│   └── genes_of_interest.txt  # Optional: mark the important genes
├── bin/
│   ├── parse_info_fields.py   # Extract VCF INFO 
│   ├── lis_output_formatter.py # Transfer to LIS JSON/PDF report
├── test_data/
│   ├── tumor_R1.fastq.gz
│   ├── tumor_R2.fastq.gz
│   ├── normal_R1.fastq.gz
│   ├── normal_R2.fastq.gz
├── README.md
├── LICENSE
├── .gitignore
└── .github/
    └── workflows/
        └── test_pipeline.yml  # GitHub Actions CI test

📦 Input
FASTQ files named:

tumor_R1.fastq.gz

tumor_R2.fastq.gz

normal_R1.fastq.gz

normal_R2.fastq.gz

📤 Output
*.g.vcf.gz, *_mutect.vcf.gz

*.cnv.cns, *_manta.vcf.gz

*_annotated.txt

report.html

lis_output.json


☁️ AWS Usage
Support for AWS Batch jobs with Nextflow Tower integration.



