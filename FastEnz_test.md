# Fast_ddRAD_Enzyme_tests
- [ipyrad stats](#ipyrad-stats)
- [SNP map](#snp-map)
- [PCA](#pca-with-plink)
- [R pop stats](#r-pop-stats)
- [NJtree](#njtree)
- [IQtree](#iqtree)




# ipyrad stats

    ## Final Sample stats summary
                                          state  reads_raw  reads_passed_filter  clusters_total  clusters_hidepth  hetero_est  error_est  reads_consens  loci_in_assembly
    Lomatium_insulare_10727_GUZA              7    4208445              4206498          196860             43171    0.061550   0.017983          19580              2964
    Lomatium_insulare_10728_GUZA              7    6352964              6347280          236805             58467    0.059960   0.015841          31704              3225
    Lomatium_insulare_10729_GUZA              7    3623416              3616320          298417             48724    0.059443   0.014815          23871              2013
    Lomatium_insulare_10730_GUPS              7    4617702              4612770          227296             47686    0.058779   0.018170          21530              2914
    Lomatium_insulare_10731_GUPS              7    5252618              5249294          226483             48065    0.061550   0.017983          21490              2965
    Lomatium_insulare_10737_GUPS              7    6050152              6043594          248618             54212    0.058440   0.017363          25147              3174
    Lomatium_insulare_9900_SNI1               7    6176005              6167159          263484             68427    0.047059   0.017211          35316              3137
    Lomatium_insulare_9901_SNI1               7    4645865              4638825          223139             58171    0.045010   0.017546          30199              3377
    Lomatium_insulare_9902_SNI1               7    5882504              5875831          218533             65475    0.043972   0.016555          35768              3365
    Lomatium_insulare_9917_SNI3               7    3327028              3323334          167625             41310    0.044314   0.016660          20897              2474
    Lomatium_insulare_9918_SNI3               7    2876945              2874306          121718             47345    0.034026   0.013167          29533              1654
    Lomatium_insulare_9919_SNI3               7    1355961              1354054          118788             19368    0.052972   0.019599           7322              1073
    Lomatium_insulare_fastEnz_10727_GUZA      7    8500023              8496491          180594             60328    0.062234   0.013570          33910              3362
    Lomatium_insulare_fastEnz_10728_GUZA      7    7532406              7528962          212770             73719    0.055799   0.014304          45022              3352
    Lomatium_insulare_fastEnz_10729_GUZA      7    8475160              8468666          311877             79660    0.056141   0.009562          46610              3371
    Lomatium_insulare_fastEnz_10730_GUPS      7    1730551              1729541           98645             23396    0.061810   0.016892          10919              1786
    Lomatium_insulare_fastEnz_10731_GUPS      7    8037076              8034200          189583             56212    0.053807   0.014241          31355              3388
    Lomatium_insulare_fastEnz_10737_GUPS      7    5061107              5059348          146977             50222    0.059960   0.015841          27366              3005


## Alignment matrix statistics:
snps matrix size: (18, 5578), 32.23% missing sites.
sequence matrix size: (18, 234445), 24.62% missing sites.

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

PCA with just FastEnz and OrigEnz pairs:  
<img width="675" height="491" alt="image" src="https://github.com/user-attachments/assets/6d143696-cab4-4574-86ab-04f5ea868bbd" />
<img width="674" height="489" alt="image" src="https://github.com/user-attachments/assets/3df31026-f98f-4286-b840-48d7e9ac2568" />
<img width="686" height="485" alt="image" src="https://github.com/user-attachments/assets/9ba400e7-9ee5-4ee1-9c4f-bce4507bd107" />

# NJtree

<img width="1007" height="586" alt="image" src="https://github.com/user-attachments/assets/4ec3e6ab-28e4-4e5f-9209-aabdfd423bbc" />
<img width="1418" height="678" alt="image" src="https://github.com/user-attachments/assets/3b5f3ab2-b831-4ea6-8245-ea46e6cbf541" />


# R population stats

<img width="297" height="187" alt="image" src="https://github.com/user-attachments/assets/7d8927fd-21c7-4ffb-bebf-9aeba64204dd" />  
<img width="243" height="191" alt="image" src="https://github.com/user-attachments/assets/966c01cb-ebf0-4fe8-90b1-a008864a8e85" />


# IQtree

    -bnni -s infile.txt -st DNA -m MFP -o Lomatium_insulare_9900_SNI1 --sprrad 6 -B 1000 -safe --prefix FastEnzTest
    
<img width="810" height="804" alt="image" src="https://github.com/user-attachments/assets/54fa515c-a615-4206-9d68-f8031e67955d" />
