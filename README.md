SC Decoding:

K is the number of message bits.
N is the number of bits transferred.

To use it set K and N and if instead of Generating message bits at 0.5 probability of 0 and 1 if any other message generating situation is there than
replace 0.5 in msg=rand(1,K)<=0.5 with p where p is the probability of 1 getting generated in msg.

Nblocks is the number of monte carlo simulation so set it as the number of monte carlo simulation you want to do.

You can set the EbNodB by the any array of it's values if you want or you can change it as you want.

Then run the code and it will give BLER.


SCL Decoding

All else is same as SC Decoding.

other than that set nL the size of list you want.

Change the pat array with the polynomial you want for adding crc bits it's in form of highest degree to lowest degree from left to right where 1 mean 
x^that dgree is present and 0 means that x^that degree is absent.

Here the length of message is A instead of K and K is final length of message after crc is added that is A+(max degree of Polynomial) so set the message 
length in A instead of K.


Make sure that N is a power of 2 for both Decoding.
Max value of N is 1024.

Gaussian_approximation is code to generate bhattacharya parameter for a given SNR you can change it's SNRdb in it
for getting bhattacharya parameter for different values of SNR.

getReliabilitySequence is a function that takes SNR and N as input and returns reversed reliability sequence of size 1*N.

In SCL for each sigma we get reliability sequence and that's commented so to use it comment or remove data load and req and Q1 and F before loop to avoid any error.


The 5G standard reliability sequence used is in .mat file provided.
