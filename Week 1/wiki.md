# Collaborative Wiki 1

Hamming and Reed-Solomon Codes Wiki

Hamming

Developed by Richard Hamming in 1950, Hamming Codes are among the earliest error-correcting codes designed to detect and correct single-bit errors in digital data. They are widely used in memory storage and telecommunications where data reliability is crucial. Unlike Reed-Solomon codes, Hamming Codes focus on smaller-scale error correction, operating over individual bits rather than entire characters or symbols.

Hamming Codes are represented as (n,k), where n is the total number of bits in the code, and k is the number of data bits. The difference, n - k, represents the number of parity bits used for error correction. These parity bits are calculated and placed at positions that are powers of two, such as 1, 2, 4, etc. The redundancy introduced by parity bits allows for the detection and correction of single-bit errors by evaluating the parity of specific bit groups in the received data

The process of encoding involves adding these parity bits to a message, while decoding involves recalculating and checking the parity to identify errors. If an error is detected, the location of the erroneous bit can be determined by summing the indices of the incorrect parity checks, enabling the system to flip the bit and correct the error.

Hamming Codes are efficient for systems requiring basic error correction but are limited to single-bit errors. Despite their simplicity, they remain widely used in applications such as ECC (Error-Correcting Code) memory, where single-bit reliability is essential.


Reed Solomon

Introduced in 1960 by Irving S. Reed and Gustave Solomon, members of MIT Lincoln Library, Reed-Solomon codes are an alternative to error checking as compared to the Hamming Codes. They are block-based error correcting codes used in a wide variety of different applications. RS codes are primarily used for correcting errors in audio and video data stored on media such as CDs, DVDs or QR codes. They are able to help recover the missing or corrupted data if anything were to be damaged. Also, when transferring data over networks there is always the possibility of information or data being lost or corrupted. RS codes assist us in recovering corrupted data that are being transferred over a network. 

Instead of operating over only a few bits like the Hamming codes, the Reed-Solomon extends this further by operating over entire characters. It is defined as the following parameters. 
RS(n, k). S = the number of bits in a character or symbol. K = the number of s-bit characters comprising the data block. N = the number of bits in the code word. 

![alt text](https://github.com/ejnorman/CSB330-2025-MELT/blob/main/Week%201/Solomon%20codes.png)

The RS codes can be broken up into two parts. Encoding and decoding. What happens in encoding is when we have a message that we want to send the RS codes will add extra information to your message called parity symbols so that in the case part of the message is lost we are still able to figure out the original message. The extra words added to our message are able to give us clues. This process is accomplished by encoding the message as a polynomial p(x) and multiplied with a polynomial generator where g(x) = (x-a)(x-a^2)(x-a^3).


