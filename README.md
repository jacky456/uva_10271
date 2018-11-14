# uva_10271

This problem named "Chopsticks" can also be resolved by dynamic programming. We need to build the matrix DP by input sequence L, where DP[i][j] indicates the minimal badness with i chopsticks and j people. DP is initialized by MAX_NUM (here 33000 is enough) except that the first column is all 0s. The most important observation is that, the 2 shorter chopsticks of a set in the optimal solution must be adjacent in the input sequence. And the recursion equation is shown as:

DP[i][j]=min⁡(DP[i-1][j],DP[i-2][j-1]+(L_i-L_(i-1))^2)

To assure there always exists a longer chopstick when both Li and Li-1 are taken, the input sequence should be sorted in decreasing order and only cases with i ≥ 3*j are considered. Hence, the value in DP[N][K+8] is the answer.
