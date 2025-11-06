# Fast_ddRAD_Enzyme_tests
- [SNP map](#snp-map)
- [PCA](#pca-with-plink)  
- [IQtree](#iqtree)
- [NJtree](#njtree)

# ipyrad stats


# SNP map 
Plotted genlight in R  
Unordered
<img width="1232" height="466" alt="image" src="https://github.com/user-attachments/assets/0d203942-34b2-4d9f-8020-babaf8fda4bf" />
Pairs of samples next to each other
<img width="1268" height="460" alt="image" src="https://github.com/user-attachments/assets/6b993a81-eee6-429a-95fa-dc900b62833e" />

# PCA with plink

    #!/bin/bash
    # load conda into the script
    
    source /Users/mayroberts/miniconda3/etc/profile.d/conda.sh
    
    #set variables path to vcf
    VCF=/Users/mayroberts/Documents/Projects/FastEnztest/ipyrad/FastEnz_test_outfiles/FastEnz_test.vcf
    OUT=/Users/mayroberts/Documents/Projects/FastEnztest/plink_PCA/fastEnz
    
    #run plink
    
    conda activate plink
    
    plink --vcf $VCF --pca --out $OUT --allow-extra-chr --double-id
    
    conda deacivate

pop files:
`FastEnz.txt`

    Lomatium_insulare_fastEnz_10727_GUZA
    Lomatium_insulare_fastEnz_10728_GUZA
    Lomatium_insulare_fastEnz_10729_GUZA
    Lomatium_insulare_fastEnz_10730_GUPS
    Lomatium_insulare_fastEnz_10731_GUPS
    Lomatium_insulare_fastEnz_10737_GUPS

'OrigEnz.txt`

    Lomatium_insulare_10727_GUZA
    Lomatium_insulare_10728_GUZA
    Lomatium_insulare_10729_GUZA
    Lomatium_insulare_10730_GUPS
    Lomatium_insulare_10731_GUPS
    Lomatium_insulare_10737_GUPS

`SNI.txt`

    Lomatium_insulare_9900_SNI1
    Lomatium_insulare_9901_SNI1
    Lomatium_insulare_9902_SNI1
    Lomatium_insulare_9917_SNI3
    Lomatium_insulare_9918_SNI3
    Lomatium_insulare_9919_SNI3

plot in R:  
<img width="638" height="399" alt="image" src="https://github.com/user-attachments/assets/487af5d4-13bd-4ab3-80ba-55bcf7defde8" />
<img width="634" height="397" alt="image" src="https://github.com/user-attachments/assets/095f5074-189f-4e81-a563-ce5fb34aa879" />
<img width="630" height="395" alt="image" src="https://github.com/user-attachments/assets/e0c66e17-dbf5-4c93-8c94-840988fee638" />

# NJtree

<img width="1007" height="586" alt="image" src="https://github.com/user-attachments/assets/4ec3e6ab-28e4-4e5f-9209-aabdfd423bbc" />


# IQtree

    -bnni -s infile.txt -st DNA -m MFP -o Lomatium_insulare_9900_SNI1 --sprrad 6 -B 1000 -safe --prefix output FastEnzTest
