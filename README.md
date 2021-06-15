# A collection of Dockerfiles for programs that do not have Docker images

## lcmlkin
I had to modify the code for this a little and you'll find the forked c++ repo for this here.
The original code had some compilation errors. I have also modified it so that it will handle
null haploid genotypes.

## read
This image has Rscript and python2.7 installed, both of which are available in path.
I have also modified the READ.py script so that it directly runs /usr/local/bin/READscript.r rather than looking
for it in the current directory

## 

