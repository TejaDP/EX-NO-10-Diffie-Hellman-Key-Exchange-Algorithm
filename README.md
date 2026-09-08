# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```
#include <stdio.h>

int main()
{
    int p, g;
    int a, b;
    int A, B;
    int key1, key2;

    printf("Enter prime number p: ");
    scanf("%d", &p);

    printf("Enter primitive root g: ");
    scanf("%d", &g);

    printf("Enter private key of Alice: ");
    scanf("%d", &a);

    printf("Enter private key of Bob: ");
    scanf("%d", &b);

    /* Alice's public key */
    A = 1;
    for(int i = 0; i < a; i++)
        A = (A * g) % p;

    /* Bob's public key */
    B = 1;
    for(int i = 0; i < b; i++)
        B = (B * g) % p;

    printf("\nAlice Public Key = %d", A);
    printf("\nBob Public Key   = %d", B);

    /* Shared secret key */
    key1 = 1;
    for(int i = 0; i < a; i++)
        key1 = (key1 * B) % p;

    key2 = 1;
    for(int i = 0; i < b; i++)
        key2 = (key2 * A) % p;

    printf("\n\nAlice Shared Key = %d", key1);
    printf("\nBob Shared Key   = %d\n", key2);

    return 0;
}
```


## Output:

<img width="851" height="388" alt="image" src="https://github.com/user-attachments/assets/0b5e8ee5-619e-4c3b-b8c2-ef5ffed29b89" />


## Result:
  The program is executed successfully

