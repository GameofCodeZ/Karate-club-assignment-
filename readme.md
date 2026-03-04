# AES Avalanche Effect Analysis

## Introduction

Cryptographic algorithms are designed to ensure the confidentiality and security of digital information. One important property of a secure cipher is the **Avalanche Effect**, where a small change in the input (such as flipping a single bit in the plaintext) results in a significant and unpredictable change in the output ciphertext. This property ensures strong **diffusion**, making it extremely difficult for attackers to identify patterns or deduce relationships between plaintext and ciphertext. In this project, we experimentally analyze the avalanche effect in the **Advanced Encryption Standard (AES)** by encrypting plaintext messages, modifying a single bit of the input, and comparing the resulting ciphertexts at the bit level.

---

## Objective

The objective of this project is to experimentally evaluate the avalanche effect in AES encryption by measuring how many ciphertext bits change when a single bit in the plaintext is modified. A strong cryptographic algorithm should ideally produce approximately **50% change in output bits**, indicating strong diffusion properties.

---

## Methodology

The experiment follows these steps:

1. Generate a random AES encryption key.
2. Select a plaintext message of fixed block size.
3. Encrypt the plaintext using AES.
4. Flip a single bit in the plaintext.
5. Encrypt the modified plaintext.
6. Convert both ciphertext outputs into binary format.
7. Compare the ciphertexts bit-by-bit to count the number of differing bits.
8. Calculate the avalanche effect percentage.
9. Repeat the experiment across multiple trials to obtain reliable results.

---

## Avalanche Effect Formula

The avalanche effect percentage is calculated as:

Avalanche Effect (%) = (Number of Changed Bits / Total Bits) × 100

For AES, the ciphertext block size is **128 bits**, so an ideal avalanche effect would produce approximately **64 changed bits**.

---

## Results

Multiple trials are conducted to evaluate the avalanche effect of AES encryption. The experimental results typically show that approximately **45–55% of ciphertext bits change** when a single plaintext bit is modified. This confirms that AES exhibits strong diffusion properties.



## Visualization

A bar chart is generated to visualize the avalanche effect across different trials. The graph shows that the percentage of changed ciphertext bits consistently remains close to **50%**, indicating the strong diffusion property of AES.

---

## Technologies Used

- Python
- PyCryptodome (AES implementation)
- Matplotlib (data visualization)
- Google Colab / Jupyter Notebook

---

## Conclusion

The experimental analysis confirms that AES demonstrates a strong avalanche effect, where small changes in the input produce large changes in the ciphertext. This property is essential for resisting statistical and differential cryptanalysis attacks, making AES one of the most secure and widely used symmetric encryption algorithms.

---

## Future Work

Future extensions of this project could include:

- Comparing avalanche effects across different block ciphers
- Analyzing avalanche properties across AES rounds
- Implementing additional cryptographic security evaluation metrics
- Developing automated tools for cryptographic security analysis
