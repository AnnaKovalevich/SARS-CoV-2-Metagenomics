# Поиск вирусных последовательностей в геноме с прогнозированием праймеров
> **Проект предполагает идентификацию вирусных последовательностей в геноме (на примере вируса SARS-CoV-2). Используются база данных SRA и NCBI для анализа полученных результатов. В ходе работы была выполнена сборка контигов, использованы инструменты QUAST, BLAST, Prokka для идентификации и классификации вирусных последовательностей. После проведено сравнение с референсным геномом SARS-CoV-2.**

команды для исполнения проекта (малая часть):

*quast spades_scaffolds.fasta -o quast_out*

*quast spades_scaffolds.fasta -o quast_out*

*samtools faidx spades_scaffolds.fasta*

*samtools faidx spades_scaffolds.fasta contig_name > contig.fa*

*more spades_scaffolds.fasta.fai | awk '$2 >= 3000 {print $1}' | xargs samtools faidx spades_scaffolds.fasta > 3000.fa*

*blastn -query contig.fa -db nt -entrez_query "1900/01/01:2020/01/01[PDAT]" -taxids 10239 -out blast_results.txt* 
