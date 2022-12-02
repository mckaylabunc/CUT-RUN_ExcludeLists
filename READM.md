*Currently just using sup data*
1. get peaks by grp, eg. yw.igg.sup.rep1
2. expand ranges of all peaks by 500 bp both directions 
  - a less conservative approach would also be fine (ie. no expansion) but this does seem to better capture regions with small neg peaks that poorly overlap
3. reduce all grp granges
4. annotate peak df by identifying overlaps of individual peak sets with union set, using GRanges function %over%  
5. annotate "shared" peaks - those that overlap the union in all datasets
6. filter by "shared" and write out bed file

This approach is pretty conservative, it only produces a list of ~80 some peaks. 
Compared to Nordin et al. 2022 which kept regions present in >=30% of datasets. Though they used ~20 datasets I believe, and primarily only used IgG samples. 

