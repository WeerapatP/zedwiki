# Rate of Stochastic Codes 

We code symbols as sufficiently distinct PFSA, and actual communication is carried ouit with binary symbols generated by these stochastic symbol generators

Let \\\(n_0\\\) be the length of symbol stream extracted from each PFSA that results in vaishingly small decoding error.
Then, it is immediate that the rate of such codes is given by:

$$r = \frac{1}{n_0} \log_2 \vert \mathcal{M} \vert $$

Importantly, this is independenty of the actual communicated word length.

From our experiments, we see that for \\\(\vert \mathcal{M} \vert = 2\\\), we have 

$$ n_0 \leqq 10 $$

implying 

$$r \geqq 0.1 $$

# Deletion to Erasure Channel conversion using PFSAs

Can we design a set of PFSA, and then allow a *CANNOT TELL* response, so that the decoding can either say which PFSA was input or is allowed to say *CANNOT TELL* with probability \\\(p\\\). Then we have an erasure channel. The optimization problem will be to minimize n keeping a constraint on p.


# Table of deletion probability vs. rate 

| citation | deletion probability | rate | comment |
|:--|:--|:--|:--|
| \[2\] | .006 | .7 | The double-layered method (watermark) (30 errors in 5000 long block) | 
| \[2\] | .098 | .214 | The double-layered method (watermark) (450 erros in 4600 long block) |
| \[11\]| .03  |.5 | fixed and psuedo-random mark, 120 errors at sequence length 4000 (the 120 was not stated explicitly in paper, I calculate it from reading a table) |
| \[14\]| .01 | .86 | LDPC outer layer and optimized fixed marker inner layer |
| \[14\]| .1 | .486 | |
| \[15\] | .29 | .25 | 2900 errors in 10012 long block, Non-binary channel|
| \[15\] | .08 (or .16) | .7 | Number read from figure 8 of the paper, block size not listed. Also .08 is for deletion only, but the paper actually considered insertion too. Insertion is assume to have the same probability as deletion in this figure 8 and hence the .16. (double-checked) | 
| \[6\] | \\\(1 - \varepsilon\\\)| \\\(poly(\varepsilon)\\\) | on alphabet size  \\\(poly(1/\varepsilon)\\\). \[7\] is purely theoretical, and no numerical experiment was given|
| \[6\] | \\\(\varepsilon\\\) | \\\(1 - \tilde{O}\(\sqrt{\varepsilon}\)\\\) | 
| \[6\] | \\\(.5 - \varepsilon\\\) | \\\(poly(\varepsilon)\\\) | list-decoded |
| \[5\] | \\\(p\\\) | \\\(\(1-p\)/120\\\) | for all \\\(p\\\). \[6\] is purely theoretical, and no numerical experiment was given| 

\[2\]: [Matthew C Davey and David JC MacKay. Reliable communication over channels with insertions, deletions, and substitutions.](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=910582)

\[11\]:[ Edward A Ratzer. Marker codes for channels with insertions and deletions.](https://link.springer.com/article/10.1007/BF03219806)

\[15\]: [Raman Yazdani and Masoud Ardakani. Reliable communication over nonbinary insertion/deletion channels.](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=6334504)

\[6\]: [Deletion Codes in the High-Noise and High-Rate Regimes](https://ieeexplore.ieee.org/document/7835185)

\[5\]: [Venkatesan Guruswami and Ray Li. Polynomial time decodable codes for the binary deletion channel.](https://ieeexplore.ieee.org/document/8502134)
\[14\]: [Symbol-Level Synchronization and LDPC Code Design for Insertion/Deletion Channels](https://ieeexplore.ieee.org/abstract/document/5733455)