## EX 10 : IMPLEMENTATION OF DIFFIE HELLMAN ALGORITHM

## AIM :
To implement key exchange between users using Diffie Hellman algorithm.

## ALGORITHM :
1.	Select a large prime number P and a primitive root G of P (publicly known).
2.	Alice selects a private key a and computes her public key x = (G^a) mod P.
3.	Bob selects a private key b and computes his public key y = (G^b) mod P.
4.	Alice and Bob exchange their public keys (x and y).
5.	Alice computes the secret key as ka = (y^a) mod P.
6.	Bob computes the secret key as kb = (x^b) mod P.
7.	Both ka and kb will be the same, forming a shared secret key for secure communication.


## PROGRAM :
```
#include <math.h>
#include <stdio.h>

long long int power(long long int a, long long int b, long long int P) {
    if (b == 1)
        return a;
    else
        return (((long long int)pow(a, b)) % P);
}

int main() {
    long long int P, G, x, a, y, b, ka, kb;

    printf("\n***** Diffie-Hellman Key Exchange Algorithm *****\n\n");

    printf("Enter the value of P: ");
    scanf("%lld", &P);
    printf("The value of P: %lld\n", P);

    printf("Enter the value of G (Primitive root of P): ");
    scanf("%lld", &G);
    printf("The value of G: %lld\n\n", G);

    a = 4;
    printf("The private key a for Alice: %lld\n", a);
    x = power(G, a, P);

    b = 3;
    printf("The private key b for Bob: %lld\n\n", b);
    y = power(G, b, P);

    ka = power(y, a, P);
    kb = power(x, b, P);

    printf("Secret key for Alice is : %lld\n", ka);
    printf("Secret key for Bob is   : %lld\n", kb);

    return 0;
}
```
## OUTPUT:

<img width="632" height="367" alt="image" src="https://github.com/user-attachments/assets/c9d2042a-aff9-4f1e-8429-10f4a25f8b5d" />

## RESULT :
The Diffie-Hellman key exchange algorithm has been successfully simulated, with correct execution	of	the	program	and	verification	of	the	results.
