# mermaid-wintersession
Repo for Winetrsession 2025  Mermaid.js course

```mermaid
flowchart TD
    Fastq@{ shape: document, label: ".fastq" }
    UBam@{ shape: document, label: ".ubam" }
    Reference@{ shape: document, label: ".fasta" }
    Bam@{ shape: document, label: ".bam" }
    Sam@{ shape: document, label: ".sam" }
    Cram@{ shape: document, label: ".cram" }
    Bed@{ shape: document, label: ".bed" }

    Fastq --- Mapping_Fastq@{ shape: start }
    Reference --- Mapping_Fastq
    Mapping_Fastq -- Mapper --> Bam

    UBam --- Mapping_UBam@{ shape: start }
    Reference --- Mapping_UBam
    Mapping_UBam -- Mapper --> Bam

    Bam <-- samtools --> Sam

    bam_to_cram@{ shape: start } --> Bam
    Reference --- bam_to_cram
    bam_to_cram -- samtools --> Cram

```