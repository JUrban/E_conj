This is a dataset for developing conjecturing methods or (in other
words) for finding useful "cuts". It is generated from the Mizar40
dataset [1].

It consists of 3161 CNF problems that can be proved with E and many
useful intermediate lemmas (cuts) for them.

Each of the E's final proof clauses C for a problem P is used as a
potentially useful intermediate lemma with which we can try to speed
up the proof search of P.

This is done by splitting P into two subproblems:

(P1) problem of proving (refuting) P with C added (positively - as an
axiom),

and

(P2) problem of proving C using P. This is reformulated due to the
clausal setting as the problem of refuting P with ~C added.

If we can prove P1 and P2, we compare the sum of their proof search
lengths L1 and L2 with the proof search length L of P. If the sum is
smaller, C is a useful cut.

The statistics for all the problems and their cuts is in the file
"statistics". The format is:

RatioOf_L1+L2_To_L : P : C : L1 : L2 : L1 + L2 :# Processed clauses : L

e.g.:

0.969339622641509:l100_fomodel0:ac_0_22.res:783:39:822:# Processed clauses : 848


The original CNF problems are in the subdirectory "problems".

The intermediate lemmas are in the file "lemmas".

The "enigma" subdirectory uses the ENIGMA features [2] to model the
problem as a regression task that for each pair (conjecture,cut)
estimates the value (ratio) of the cut.

[1]: Cezary Kaliszyk, Josef Urban: MizAR 40 for Mizar
40. J. Autom. Reasoning 55(3): 245-256 (2015)

[2]: Jan Jakubuv, Josef Urban: ENIGMA: Efficient Learning-Based
Inference Guiding Machine. CICM 2017: 292-302