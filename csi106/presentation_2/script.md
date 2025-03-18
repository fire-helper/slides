# Part 1: Summary on Cryptography and Symmetric cryptography

## Introduction

> Ceremonial introduction here "Hello everyone" blah blah

We bring to you a short presentation about **asymmetric cryptography**.

## Cryptography?

But before that, we have to know what cryptography even *is*.

In **very** simple terms, *cryptography* is the field of research on
how to *conceal messages through ciphers*.

Here's a very simple cipher: the Caesar cipher. By applying the Caesar
cipher, the **plaintext** "Hello, world!" is converted into this
**ciphertext**.

Cryptography is broadly divided into 2 categories: **Symmetric
cryptography** and **Asymmetric cryptography**.

## Symmetric cryptography

Symmetric cryptography shares one common ***secret key***.

> Qua cái slide illustration plaintext document/encrypted document

For example, in the Caesar cipher above, the secret was "shift all
letters 3 positions forward".

In this system, both ***encrypting*** and ***decrypting*** use the same
secret, similar to a physical lock: you lock and unlock it with the
same key.

> Nên body language lên slide các kiểu 🐧

> Move to last slide of section

However, this poses a problem: how do you **share** this secret
***securely***?

The solution: you simply don't share any secrets at all!

This is achieved with ***asymmetric cryptography***.

# Part 2: Asymmetric cryptography

In contrast with **symmetric cryptography**, **asymmetric cryptography**
utilizes 2 keys instead of just 1.

These 2 keys ***always*** (stressed hard) come in a *pair*, called a
*key pair*.

There are many algorithms out there that allow you to generate
keypairs. The common thing between them is that they use a very large,
completely random number and generate keys from that number. Therefore,
unless an attacker can somehow know this random number, they cannot
generate the same keys.

In a *keypair*, the 2 keys are called the **private key** and the
**public key**.

True to their names, the **private key** must be kept secret at all
costs. The **public key** can be shared freely.

Now, the core of **asymmetric cryptography** is that: 1 key encrypt,
***only*** the other key can decrypt.

If the public key encrypt, only the corresponding private key can decrypt.

If the private key encrypt, only the corresponding public key can decrypt.

## Consequence

With this, **asymmetric cryptography** eliminates the need to share one common secret.

Each person has their own keypair, their own private and public keys. Only the public keys need to be shared, the private keys can be kept secret.

This has some extremely important applications.

# Part 3: Applications of asymmetric cryptography

## Digital signature (chữ ký số)

> Sử dụng slides cho dễ, phần này giải thích bằng lời hơi khó

One application is digital signature. Before Alice sends a message,
she **signs** her message using ***her own private key***.

When Bob receives the message, he can use ***Alice's public key*** to
verify the signature. If the signature match, the message really came
from Alice and not someone else.

This also proves that the message was NOT tampered by a third-party.

## Secure encryption

Bob wants to send Alice a message. Bob wants **ONLY** Alice to read the
message, no one else.

Before sending, Bob **encrypts** the message using **Alice's public key**.

When Alice receives it, she **decrypts** it using **her own private key**.

Remember, the keys come in a pair. Public key encrypts -> ONLY private
key can decrypt.

Since only Alice has her private key, no one else can decrypt it except
Alice herself.

## The Internet itself

This padlock icon you see on your browser means the connection between
you and the server is secure.

This security is provided by **asymmetric cryptography**. This ensures
that messages between you and the server are private.
