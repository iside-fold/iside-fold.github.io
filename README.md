## Ab initio protein folding

The ISIDE algorithm can predict the threedimensional structure of proteins through a metaheuristic exploration (tabu search) of a conformational space discretized by the use of a structural alphabet (Protein Blocks).  
The method is entirely implemented in C++ and can be run in parallel on UNIX-like operating systems.

### Install

Compile ISIDE:
```markdown
$ make
```
Then compile TMscore:
```markdown
$ cd TMscore
$ gfortran -static -O3 -ffast-math -lm -o TMscore TMscore.f
```
or
```markdown
$ g77 -static -O3 -lm -o TMscore TMscore.f
```
To get help:
```markdown
$ ./ISIDE -h
```


### Examples

```markdown
$ ./ISIDE -t 38 -c examples/folds/a_9.pdb -j job01 -n 4 -f examples/pbmtx/a_9.pbmtx -s 1000
$ ./ISIDE -t 38 -j job01 -n 4 -f examples/pbmtx/a_9.pbmtx -s 1000 -i RVIAMPSVRKYAREKGVDIRLVQGTGKNGRVLKEDIDAFLAG
$ ./ISIDE -t 38 -c examples/folds/a_9.pdb -j job01 -n 4 -f examples/pbmtx/a_9.pbmtx -s 1000 -y 0.20
$ ./ISIDE -t 38 -c examples/folds/a_9.pdb -j job01 -n 15 -f examples/pbmtx/a_9.pbmtx -s 1000 -r 0.08
```
Note: The tabu list size should be selected based on the protein sequence length, so that (seq length)x0.5 < [-t arg] < (seq length)x2

###### © 2019 Postic G, Santuz H, Deniau R, Gelly JC.
###### Contact: [guillaume.postic@univ-paris-diderot.fr](mailto:guillaume.postic@univ-paris-diderot.fr); [jean-christophe.gelly@univ-paris-diderot.fr](mailto:jean-christophe.gelly@univ-paris-diderot.fr)
