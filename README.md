# On-computing-with-some-convex-relaxations-for-the-maximum-entropy-sampling-problem

@ Zhongzhu Chen (zhongzhc@umich.edu), Marcia Fampa (fampa@cos.ufrj.br), Jon Lee (jonxlee@umich.edu).
This project includes the data, results, plots for: "On computing with some convex relaxations for the maximum-entropy sampling problem," INFORMS Journal on Computing (in press).

### Data File ###

The benchmark instances are stored in .mat format in the data folder (the sources of the data are listed in section 3.2 of our paper):

1. ``data63.mat``: positive definite of order $63$
2. ``data90.mat``: positive definite of order $90$
3. ``data124.mat``: positive definite of order $124$
4. ``dat2000.mat``: positive semidefinite of order $2000$ and rank $949$



### Experimental Setting ###

We ran our experiments under Windows, on an Intel Xeon E5-2667 v4 @ 3.20 GHz processor equipped with 8 physical cores (16 virtual cores) and 128 GB of RAM. We implemented our code in Matlab using Knitro, version 12.4, as our nonlinear-programming solver.



### Results ###

Our results data files are stored in ``.xlsx`` format. All files contain the order of data matrix as the first column and cardinality of the subset to choose as the second column. In the following, we use ‘linx’, ‘DDFact’, and ‘comp DDFact’ to represent the values corresponding to linx upper bound, factorization upper bound, and complementary factorization upper bound respectively. 

#### Results-unconstrained ####

The experimental results for upper bounds without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63.xlsx``, ``data90.xlsx``, ``data124.xlsx``, ``data2000.xlsx``.

In the ``data63.xlsx``, ``data90.xlsx``, and ``data124.xlsx`` file, each row represents the results for a specific $s$. The columns represent:

1. lower bound computed by a heuristic method:

   *  column 'C'

2. upper bounds constructed from dual feasible solutions :

   * column 'D': linx
   * column 'E': DDFact
   * column 'F': comp DDFact

3. integrality gaps:

   * column 'G': linx
   * column 'H': DDFact
   * column 'I': comp DDFact

4. duality gap when solving the continuous realxations of MESP, optimality verification:

   * column 'J': linx
   * column 'K': DDFact
   * column 'L': comp DDFact

5. number of variables fixed to $0$:

   * column 'M': linx
   * column 'N': DDFact
   * column 'O': comp DDFact

6. number of variables fixed to $1$:

   * column 'P': linx
   * column 'Q': DDFact
   * column 'R': comp DDFact

7. number of variables fixed to $0$ or $1$:

   * column ‘S': linx
   * column ‘T’: DDFact
   * column 'U': comp DDFact

8. wall clock time (seconds) for solving the continuous relaxations of MESP (seconds):

   * column ‘V’: linx with BFGS method
   * column ‘W’: linx with Newton method
   * column ‘X’: DDFact with BFGS method
   * column ‘Y’: comp DDFact with BFGS method

   

In the `data2000.xlsx`, each row represents the results for a specific $s$. Because the data matrix is singular, we are unable to calculate values corresponding to complementary factorization upper bound. The columns represent:

1. lower bound computed by a heuristic method:
   *  column 'C'
2. upper bounds constructed from dual feasible solutions:
   * column 'D': linx
   * column 'E': DDFact
3. integrality gaps:
   * column 'F': linx
   * column 'G': DDFact
4. duality gap when solving the continuous realxations of MESP, optimality verification:
   * column 'H': linx
   * column 'I': DDFact
5. number of variables fixed to $0$:
   * column 'J': linx
   * column 'K': DDFact
6. number of variables fixed to $1$:
   * column 'L': linx
   * column 'M': DDFact
7. number of variables fixed to $0$ or $1$:
   * column ‘N': linx
   * column ‘O’: DDFact
8. wall clock time (seconds) for solving the continuous relaxations of MESP (seconds):
   * Column ‘P’: linx with BFGS method
   * Column ‘Q’: linx with Newton method
   * Column ‘R’: DDFact with BFGS method

---

The experimental results for computing optimal scale factors $\gamma$ for linx bound without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63gammaH.xlsx``, ``data90gammaH.xlsx``, ``data124gammaH.xlsx``, ``data2000gammaH.xlsx``, .

In the .xlsx file, each row represents the results for a specific $s$. The columns include:

1. number of iterations for calculating the optimal scale factor:
   * column ‘C’
2. integrality gap attained by the obtained scale factor:
   * column ‘D’
3. absolute residual at the obtained scale factor:
   * column ‘E’
4. difference of integrality gaps between obtained scale factor and last scale factor:
   * column ‘F’
5. linx bound under obtained scale factor:
   * column ‘G’
6. obtained scale factor:
   * column ‘H’
7. time comsumed for the optimization process (seconds):
   * column ‘I’

---

The experimental results for mixing upper bounds without linear constraint $Ax\le b$ are stored in .xlsx format: ``data63mix.xlsx``, ``data90mix.xlsx``, ``data124mix.xlsx``.

In the ``data63mix.xlsx`` and``data90mix.xlsx`` file, each row represents the results for a specific $s$. The columns include:

1. upper bounds constructed from dual feasible solutions:

   * column ‘C’: DDFact
   * column ‘D’: linx

   * column ‘E’: mixing DDFact and linx

2. integrality gaps:

   * column ‘F’: DDFact
   * column ‘G’: linx

   * column ‘H’: mixing DDFact and linx

3. mixing parameters, ranging from $0$ to $1$:

   * column ‘I’: mixing DDFact and linx



In the ``data124mix.xlsx`` file, each row represents the results for a specific $s$. The columns include:

1. upper bounds constructed from dual feasible solutions:

   * column ‘C’: DDFact
   * column ‘D’: comp DDFact
   * column ‘E’: linx

   * column ‘F’: mixing DDFact and comp DDFact
   * column ‘G’: mixing DDFact and linx
   * column ‘H’: mixing comp DDFact and linx

2. integrality gaps:

   * column ‘I’: DDFact
   * column ‘J’: comp DDFact
   * Column ‘K’: linx

   * column ‘L’: mixing DDFact and comp DDFact
   * column ‘M’: mixing DDFact and linx
   * column ‘N’: mixing comp DDFact and linx

3. mixing parameters, ranging from $0$ to $1$:

   * column ‘O’: mixing DDFact and comp DDFact
   * column ‘P’: mixing DDFact and linx
   * column ‘Q’: mixing comp DDFact and linx


#### Results-constrained ####

The experimental results for upper bounds linear constraints $Ax\le b$ are stored in .xlsx format: ``data63mix_constr.xlsx``.

In the .xlsx file, each row represents the results for a specific $s$. The columns represent:

(mix1: DDFact + comp DDFact, mix2: DDFact + linx, mix3: comp DDFact + linx)

1. lower bound computed by a heuristic method:
   * Column ‘C’
2. upper bounds constructed from dual feasible solutions 
   * column ‘D’: DDFact
   * column ‘E’: comp DDFact
   * column ‘F’: linx
   * column ‘G’: mixing DDFact and comp DDFact
   * column ‘H’: mixing DDFact and linx
   * column ‘I’: mixing comp DDFact and linx
3. integrality gaps:
   * column ‘J’: DDFact
   * column ‘K’: comp DDFact
   * column ‘L’: linx
   * column ‘M’: mixing DDFact and comp DDFact
   * column ‘N’: mixing DDFact and linx
   * column ‘O’: mixing comp DDFact and linx
4. duality gaps when solving the continuous realxations of MESP, optimality verification:
   * column ‘P’: DDFact
   * column ‘Q’: comp DDFact
   * column ‘R’: linx
   * column ‘S’: mixing DDFact and comp DDFact
   * column ‘T’: mixing DDFact and linx
   * column ‘U’: mixing comp DDFact and linx
5. number of variables fixed to $0$:
   * column ‘V’: DDFact
   * column ‘W’: comp DDFact
   * column ‘X’: linx
   * column ‘Y’: mixing DDFact and comp DDFact
   * column ‘Z’: mixing DDFact and linx
   * column ‘AA’: mixing comp DDFact and linx
6. number of variables fixed to $1$:
   * column ‘AB’: DDFact
   * column ‘AC’: comp DDFact
   * column ‘AD’: linx
   * column ‘AE’: mixing DDFact and comp DDFact
   * column ‘AF’: mixing DDFact and linx
   * column ‘AG’: mixing comp DDFact and linx
7. number of variables fixed to $0$ or $1$:
   * column ‘AH’: DDFact
   * column ‘AI’: comp DDFact
   * column ‘AJ’: linx
   * column ‘AK’: mixing DDFact and comp DDFact
   * column ‘AL’: mixing DDFact and linx
   * column ‘AM’: mixing comp DDFact and linx
8. mixing parameter values for mixing upper bounds:
   * column ‘AN’: mixing DDFact and comp DDFact
   * column ‘AO’: mixing DDFact and linx
   * column ‘AP’: mixing comp DDFact and linx
9. wall clock time for solving the continuous relaxations of MESP:
   * column ‘AQ’: DDFact
   * column ‘AR’: comp DDFact
   * column ‘AS’: linx
   * column ‘AT’: mixing DDFact and comp DDFact
   * column ‘AU’: mixing DDFact and linx
   * column ‘AV’: mixing comp DDFact and linx


### Graph ###

The graph folder constains graphs corresponding to each instance matrix, denoted by their order in the file name. 

Plots with ``_continous``, ``_time``, ``_mix``, ``_fixnum`` suffixes are for integrality gap, wall clock time, mixing bounds, number of fixed variables respectively.

Plots with ``_lincon_`` in the name are plots for experiments with linear constraint $Ax \le b$. 

Plots with ``Linx_time_ratio`` in name are time ratios for computing linx bound with BFGS/Newton methods.
