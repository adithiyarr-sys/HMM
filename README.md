Design of the Viterbi Value matrix
Rows correspond to the hidden states, and the columns correspond to the emissions that is the observed nucleotide sequences. Here I am showing the calculation for the first two nucletides.

             C                                                          T     T
s [s-s-C(0.00) max(s-s-C-s-T, s-E-C-s-T, s-5-C-s-T, s-I-C-s-T, s-e-C-s-T)     .] 
E [s-E-C(0.25) max(s-s-C-E-T, s-E-C-E-T, s-5-C-E-T, s-I-C-E-T, s-e-C-E-T)     .] 
5 [s-5-C(0.00) max(s-s-C-5-T, s-E-C-5-T, s-5-C-5-T, s-I-C-5-T, s-e-C-5-T)     .]
I [s-I-C(0.00) max(s-s-C-I-T, s-E-C-I-T, s-5-C-I-T, s-I-C-I-T  s-e-C-I-T)     .]
e [s-e-C(0.00) max(s-s-C-e-T, s-E-C-e-T, s-5-C-e-T, s-I-C-e-T, s-e-C-e-T)     .]
It is important to remember that you will be working in the log scale.
Implementation of Viterbi Algorithm
Write a function calculate_prob_for_a_node() that populate a single cell in the matrix. The function will return two values:

the maximum value, for example, look at the 2nd row, 2nd column in the matrix: max(s-s-C-E-T, s-E-C-E-T, s-5-C-E-T, s-I-C-E-T, s-e-C-E-T). If the probability for s-E-C-E-T is highest (lets say X), then the function should return X
AND

The index of that maximum value described in the first point: so index of X is 1 (recall that Python works on the 0-based index system)
Populate viterbi_value_matrix with X for row 2 and col 2

Populate viterbi_trace_matrix with 1 for row 2 and col 2
