# On-computing-with-some-convex-relaxations-for-the-maximum-entropy-sampling-problem
@ Zhongzhu Chen (zhongzhc@umich.edu), Marcia Fampa (fampa@cos.ufrj.br), Jon Lee (jonxlee@umich.edu).
This project includes the data, results, plots for: "On computing with some convex relaxations for the maximum-entropy sampling problem," INFORMS Journal on Computing (in press).

[TOC]

### Data File ###

The benchmark instances are stored in .mat format in the data folder (the sources of the data are listed in section 3.2 of our paper):

1. ``data63.mat``: positive definite of order $63$
2. ``data90.mat``: positive definite of order $90$
3. ``data124.mat``: positive definite of order $124$
4. ``dat2000.mat``: positive semidefinite of order $2000$ and rank $949$



### Experimental Setting ###

We ran our experiments under Windows, on an Intel Xeon E5-2667 v4 @ 3.20 GHz processor equipped with 8 physical cores (16 virtual cores) and 128 GB of RAM. We implemented our code in Matlab using Knitro, version 12.4, as our nonlinear-programming solver.



### Results ###

Our results data files are stored in ``.xlsx`` format. All files contain the order of data matrix as the first column and cardinality of the subset to choose as the second column.

#### Results-unconstrained ####

The experimental results for upper bounds without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63.xlsx``, ``data90.xlsx``, ``data124.xlsx``, ``data2000.xlsx``.

In the .xlsx file, each row represents the results for a specific $s$. The columns represent:

1. lower bound computed by a heuristic method (column 'c')
2. upper bounds constructed from dual feasible solutions (column 'E': factorization upper bound, column 'F': complementary factorization upper bound, column 'G': linx upper bound)
3. integrality gap (= upper bound $-$ lower bound)
4. duality gap when solving the continuous realxations of MESP
5. number of variables fixed to $0$ 
6. number of variables fixed to $1$
7. number of variables fixed to $0$ or $1$
8. wall clock time (seconds) for solving the continuous relaxations of MESP
   * for linx bound, we give time with BFGS/Newton method
(for ``data2000.mat`` instance, because of singularity, we do not calculate complemenrary DDFact bound)

---

The experimental results for computing optimal scale factors $\gamma$ for linx bound without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63gammaH.xlsx``, ``data90gammaH.xlsx``, ``data124gammaH.xlsx``, ``data2000gammaH.xlsx``, .

In the .xlsx file, each row represents the results for a specific $s$. The columns include:

1. number of iterations for calculating the optimal scale factor
2. integrality gap attained by the obtained scale factor
3. absolute residual at the obtained scale factor
4. difference of integrality gaps between obtained scale factor and last scale factor
5. obtained scale factor
6. time comsumed for the optimization process

---

The experimental results for mixing upper bounds without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63mix.xlsx``, ``data90mix.xlsx``, ``data124mix.xlsx``.

In the .xlsx file, each row represents the results for a specific $s$. The columns include:
1. single upper bounds
2. mixing upper bounds
3. single integrality gaps
4. mixing integrality gaps
5. mixing parameter values.

Note that for ``data63.mat`` and ``data63.mat``, we mix DDFact and linx upper bounds. For ``data124.mat``, we mix DDFact and linx upper bounds, complementary DDFact and linx upper bounds, and complementary DDFact and DDFact upper bounds. 


#### Results-constrained ####

The experimental results for upper bounds linear constraints $Ax\le b$ are stored in .xlsx format: ``data63mix_constr.xlsx``.

In the .xlsx file, each row represents the results for a specific $s$. The columns represent:

(mix1: DDFact + comp DDFact, mix2: DDFact + linx, mix3: comp DDFact + linx)

1. lower bound computed by a heuristic method
2. upper bounds constructed from a dual feasible solution for single and mixing upper bounds 
3. integrality gaps (= upper bound $-$ lower bound) for single and mixing upper bounds 
4. duality gaps when solving the continuous realxations of MESP for single and mixing upper bounds 
5. number of variables fixed to $0$ for single and mixing upper bounds 
6. number of variables fixed to $1$ for single and mixing upper bounds 
7. number of variables fixed to $0$ or $1$ for single and mixing upper bounds 
8. mixing parameter values for mixing upper bounds 
9. wall clock time for solving the continuous relaxations of MESP for single and mixing upper bounds 


### Graph ###

The graph folder constains graphs corresponding to each instance matrix, denoted by their order in the file name. 

Plots with ``_continous``, ``_time``, ``_mix``, ``_fixnum`` suffixes are for integrality gap, wall clock time, mixing bounds, number of fixed variables respectively.

Plots with ``_lincon_`` in the name are plots for experiments with linear constraint $Ax \le b$. 

Plots with ``Linx_time_ratio`` in name are time ratios for computing linx bound with BFGS/Newton methods.
