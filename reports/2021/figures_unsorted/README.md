This directory contains the figures related to project **A19-1844**

Taken from emails with UCD Seq Center
* HMW*.jpg == pulse field gel taken from sequencing center

## KAT PLOTS
The following copied with `noglob scp -P 2022 sejoslin@farm.cse.ucdavis.edu:/home/sejoslin/git_repos/genome_assembly/output/kat_raw/*.png kat_raw/.`
* (seq_tech_k*_kat_gcp.mx.png == GC count in raw files (contamination)
* {seq_tech}_k*_kat_hist.png == histogram of distinct kmers (contamination)
* {seq_tech}_k*_kat_comp-main.mx.density.png == R1 vs R2 (seq bias)

## LONGQC PLOTS
The following in the `longqc_raw/` directory were coppied with: `noglob scp -P 2022 sejoslin@farm.cse.ucdavis.edu:/home/sejoslin/git_repos/genome_assembly/output/longqc/?_hifi_?/figs/*.png longqc_raw/.`
```
noglob scp -r -P 2022 sejoslin@farm.cse.ucdavis.edu:/home/sejoslin/git_repos/genome_assembly/output/longqc/?_hifi_? longqc_raw/.
for i in longqc_raw/*_hifi_*
do
rm -r $i/analysis
dir=$(echo $i | cut -f2 -d/ )
for file in $i/figs/*.png
do
filename=$(echo $file | rev | cut -f1 -d/ | rev)
pth=$(echo $file | cut -f1-3 -d/)
mv $file ${pth}/${dir}.${filename}
done
done
```
* *average_qv.png
* *coverage.png
* *gcfrac.png
* *length.png
* *masked_region.png

