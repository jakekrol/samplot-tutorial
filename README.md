# Setup
use python 3.7; had issues with new python versions
```
conda env create -f environment.yml -n samplot_env
conda activate samplot_env
```
decompress BAMs, make sure the indices (.bai) are in same directory
```
gunzip *bam.gz
```

# Samplot
```
# -b: bams (space-delim)
# -c, -s, -e: chromosome, start, end (respectively)
# -t: type of structural variant (SV)
# --zoom: context window surrounding the specified region (-c,-s,-e); +/- 1000 base pairs right/left of break points in this example 
# -o: output file
samplot plot \
    -b merged.HGSV_204433.mode_1.bam merged.HGSV_204433.mode_2.bam \
    -c 15 -s 99926479 -e 99928418 \
    -t DEL --zoom 1000 \
    -o output.png
```


