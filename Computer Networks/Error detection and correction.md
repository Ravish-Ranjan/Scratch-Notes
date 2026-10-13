# Error detection and correction

1. detection 
  1. hamming distance = no. of bits in xor of 2 datawords   (hammingdist(1011, 1000) = 1011 xor 1000 = 0011 = 2) s error can be found uniqely by s+1 distance minimum (if for any codeword hamming distance in n bits then n-1 bit erro can be found only)
  2. parity check (odd bit error detection)
  3. cyclic code : linear coding where if codeword is rotated it is also a codeword
    1. CRC : 
      1. dataword size = d
      2. generator size = k
      3. d > k
      4. codeword size = d + k
      5. single bit error can only be caught when 
        1. generator has more than 1 term 
        2. least significant bit is set
        3. gen should not divide x^t + 1
        4. gen should have factor x+1
    2. Checksum
      1. datawords : m bits x n words
      2. sum : m bits 1 word
      3. codeword : m bits x n+1 words
      4. xor all n words to get res (add higher bits if more thatn m bits)
      5. take 1's complement of the res to get sum
      6. send all data with sum to reciever
      7. is sum of all is all 1's , it is correct
      8. problem if 2 words are same
        1.  fletcher algo (Di = next 8 bit data,R= 0 ,L = 0)
          1. R = (R + Di) % 2^bits
          2. L = (L + R) % 2^bits
          3. checksum = L*2^bits + R
        2. adler algo (Di,16 bits, R= 1, L = 0)
          1. R = (R + D)%(65521)
          2. L = (L + R)%(65521)
          3. checksum = L*65536 + R
2. correction
  1. min hamming dist = 2t + c where t is the no. of bits to correct
  2. or use xor 
  3. or chunk interleaving (send x packets or y size as y packets of x size ) if one packet lost only a bit of a original packet is lost
  4. Combing : combination of hamming distance in a packet and then inerleave many packets   m x t bit correction 
  5. compunding : send lowres of previous packet with actual highres of current packer
  6.  

 

 