# SAW-Estimation
Self Avoiding Random Walk Estimation

This Github Repository contains 5 coding files as follows:
1. `Basic_Deterministic Method.ipynb`
 
 This file implements a **recursive backtracking algorithm** to compute the exact number $c_L$ of self-avoiding walks (SAWs) for lengths $L \leq 10$. Starting from `(0,0)`, the algorithm explores all possible paths in a **depth-first manner**, avoiding self-intersections by tracking visited sites. If $L=0$, it counts the walk as valid (base case). For $L>0$, it checks all four possible moves (up, down, left, right), recursively continuing from valid (unvisited) positions while discarding invalid ones. This method is practical only for small $L$.  
 
2. `Monte_Carlo_I.ipynb`

   This file implements a **rejection sampling** method to estimate the number of self-avoiding walks for lengths $L<50$. The algorithm generates a possible random walks of length $L$ and removes those that self-intersect. By simulating $N$ trials per $L$, we compute the fraction of valid SAWs, which approximates $4^L$, and multiply to this fraction to get an estimate of $c_L$.
   
3. `Monte_Carlo_II.ipynb`
   This file implements **importance sampling** to efficiently estimate the number of self-avoiding walks for large L, addressing the high rejection rates of naive methods. Unlike rejection sampling, it biases the sampling process toward valid SAWs by sampling the walk from next valid moves.
   
4. `PERM.ipynb`
   This file implements the **PERM algorithm**, an advanced Monte Carlo method designed to efficiently estimate the number of self-avoiding walks for large $L$. By avoiding the unbalance weight distributions and high rejection rates, PERM dynamically prunes low-weight walks (likely to fail) and enriches high-weight walks (likely to succeed), optimizing computational effort and reducing estimator variance.

5. `MulticanonicalMC.ipynb`
   This file implements the Multicanonical Wang-Landau method, an advanced Monte Carlo technique for estimating the growth constant $\mu$ of self-avoiding walks by uniformly sampling the configuration space. Inspired by Shirai & Kikuchi (2013), it addresses the challenges of rugged energy landscapes in SAWs. However, our exploration was challenged by the high demand of computational resources and fluctuating convergence of $\mu$. This method remains a potential research area that we hope to further explore.
