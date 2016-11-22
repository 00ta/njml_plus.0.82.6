NJML+ 0.82.6  Manual

Satoshi Oota

Bioresource Information Division
Department of Biological Systems
RIKEN Bioresource Center
3-1-1 Koya-dai, Tsukuba 305-0074, JAPAN 
Tel: +81-29-836-9039
Fax:+81-29-836-9077

How to compile

Just ``make'' in this directory. Depending on your environments, a lot of warnings will be generated
from subsets of PHYLIP and CLUSTALW but they are OK.

NJML+ 0.82.6 source code was pre-compiled for MacOS (El Capitan). So if you are using El Capitan, you do not need to recompile. Currently I tested NJML+ 0.82.6 only on Unix-like system including MacOS (El Capitan). But it should work also on Windows with some modifications.

How to use

After the compilation, set environment variable NJMLDIR into the directory where NJML+ 0.82.6 resides. For example:

In case of bash shell:

export NJMLDIR=/home/oota/njml_plus.0.82.6;

In cases of csh/tcsh shell:

setenv NJMLDIR /home/oota/njml_plus.0.82.6;

``/home/oota'' should be replaces with a directory you prefer.

NJML+ 0.82.6 is controlled by a Yang's paml-like control file:
``njml_plus.ctl''

Example of njml_plus.ctl

seqfile = Mel.seq /* sequence data file name */
threshold = 90    /* Absolute # of reliability measure as a threshold; auto: experimental dynamic assignment of the threshold */
model = JTT   /* evolutionary model: JC; K2P; HKY; JTT; Dayhoff */
TS/TV = 4.0
mode = A     /* likelihood computation mode: A, B, C, or D */
n = 3     /* # of removed internal branches */


A Sample file is $NJMLDIR/njml_plus.0.82/src/njml_plus.ctl.

After setting the control file in $NJMLDIR/njml_plus.0.82.6/src, just
run ``./njml_plus.''

At the current version, I recommend you to copy sequence file in $NJMLDIR/njml_plus.0.82/src directory and run njml_plus. Created working files may destroy your files.

A result will be in ``finaltree2.'' Each negative number indicates reevaluated internal branches by NJML+ at step s, where s = the negative number * -1. Statistical information (Bootstrap values of candidate trees and standard error of the maximum likelihood values) is reported for the reevaluated internal branches but the current version does not have a convenient utility to show them. The utility will be added in the next release.

I recommend you to use NJPLOT to display the final tree.

How to cite

Please cite the following papers:

1. Ota, S. & Li, W.-H. NJML+: An Extension of the NJML Method to Handle Protein Sequence Data and Computer Software Implementation. Mol Biol Evol 18, 1983-1992 (2001).
2. Ota, S. & Li, W.-H. NJML: A Hybrid Algorithm for the Neighbor-Joining and Maximum-Likelihood Methods. Mol Biol Evol 17, 1401-1409 (2000).


Known problems

1.	NJML+ 0.82.6 requires part of two packages PHYLIP and CLUSTALW. While they are included in NJML+ 0.82.6, they were modified from the originals. If you want to redistribute NJML+ 0.82.6, please do it as the whole package.
2.	Generated statistic information tables are not sorted by the log maximum likelihood values. They are in order of generated topologies.
3.	A lot of messy messages are displayed during execution.
4.	NJML+ 0.82.6 uses a set of intermediate files in the src directory, which will be overwritten. Please be cautious if you run NJML+ 0.82.6 on a mainframe machine. The intermediate topologies with branch lengths and bootstrap values are output just to standard output. You need to redirect if you want to gather them.



Enjoy!



Satoshi (2016/11/21)

