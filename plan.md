This is an excellent topic choice. RSA is arguably the most famous practical application of the **Algebraic Structures** module of your discrete math course. It allows you to demonstrate a deep understanding of modular arithmetic, prime numbers, and Euler's Theorem without needing to force connections to unrelated topics like Graph Theory.

Here is a comprehensive outline tailored for a group of three, designed to meet your course requirements for theoretical depth and proof.

### **Essay Title Suggestion**

- **Formal:** *The Algebraic Structures of Public-Key Cryptography: A Theoretical Analysis of RSA*
- **Descriptive:** *From Euler to Encryption: Proving the Mathematical Correctness of the RSA Algorithm*

---

### **Section 1: Introduction**

- **Context:** Briefly introduce the concept of Public-Key Infrastructure (PKI) versus Symmetric Key cryptography.
- **Problem Statement:** How can two parties communicate securely without exchanging a secret key beforehand?
- **Course Connection:** State clearly that this essay focuses on **Algebraic Structures** (specifically Number Theory and Group Theory) to solve this problem.

### **Section 2: Mathematical Preliminaries (Algebraic Structures)**

- *Goal: Define the "tools" you will use, referencing specific course concepts.*
- **Modular Arithmetic:** Definition of congruence ($a \equiv b \pmod n$) and basic properties.
- **The Multiplicative Group of Integers Modulo $n$ ($\mathbb{Z}_n^*$):**
- Explain that RSA operates within this specific algebraic structure.
- Definition of Coprime/GCD.
- **The Extended Euclidean Algorithm:**
- Explain its use in finding modular inverses (essential for calculating the private key).
- **Euler's Totient Function $\phi(n)$:**
- Definition: The count of positive integers less than $n$ that are relatively prime to $n$.
- Property: For distinct primes [^1]$p$ and [^2]$q$, [^3]$\phi(pq) = (p-1)(q-1)$.[^4]

### **Section 3: The Core Theorems (The "Theoretical Analysis")**

- *Goal: Prove the underlying theorems before applying them.*
- **Fermat’s Little Theorem:** State the theorem as a special case.
- **Euler’s Theorem:**
- **Statement:** If [^5]$gcd(a, n) = 1$, then [^6]$a^{\phi(n)} \equiv 1 \pmod n$.[^7]
- **Proof:** Provide a formal proof here. This satisfies the course requirement to "perform theoretical analysis and proof." This is the mathematical "heart" of RSA.

### **Section 4: The RSA Algorithm & Proof of Correctness**

- *Goal: Apply the theory to the concrete problem.*
- **Key Generation Process:**
1. Select primes $p, q$.
2. Compute $n = pq$ and $\phi(n)$.
3. Choose public exponent $e$ such that $gcd(e, \phi(n)) = 1$.
4. Compute private exponent $d$ such that $de \equiv 1 \pmod{\phi(n)}$.
- **Encryption and Decryption Functions:**
- Encryption: $C \equiv M^e \pmod n$
- Decryption: $M \equiv C^d \pmod n$
- **Proof of Decryption (The "Deep Dive"):**
- Show mathematically why determining $M$ from $C$ works.
- You must prove that $(M^e)^d \equiv M \pmod n$.
- Use Euler’s Theorem to show that $M^{ed} = M^{k\phi(n) + 1} \equiv (M^{\phi(n)})^k \cdot M \equiv 1^k \cdot M \equiv M \pmod n$.

### **Section 5: Security & Complexity Analysis**

- **The Trapdoor Function:** Explain that multiplication is easy, but factorization (finding $p$ and $q$ given $n$) is computationally infeasible for large numbers.
- **Implications:** Briefly discuss why "brute forcing" the private key $d$ is impossible without factoring $n$.

### **Section 6: Conclusion**

- Summarize how the algebraic properties of $\mathbb{Z}_n^*$ enable secure digital communication.
- Reiterate that the security of RSA rests entirely on the difficulty of the mathematical problem of integer factorization.

---

### **Suggested Work Distribution (For 3 Members)**

Since you are working in a team of three, here is a logical way to split the work so everyone deals with "math," but in different ways:

**Member 1: The Theorist (Sections 2 & 3)**

- **Focus:** Algebraic Structures and Theorems.
- **Task:** Write the definitions of groups, modular arithmetic, and write the formal proof for Euler’s Theorem.
- **Course Connection:** Heavily tied to the *Algebraic Structure* and *Set Theory* parts of the course.

**Member 2: The Architect (Section 4)**

- **Focus:** The Algorithm and Correctness Proof.
- **Task:** Detail the Key Gen/Encrypt/Decrypt steps and perform the algebraic proof that Decryption actually recovers the message (linking back to Member 1's Euler's Theorem proof).
- **Course Connection:** Direct application of *Propositional Logic* (proof steps) and *Algebraic Structure*.

**Member 3: The Analyst (Section 5 & Example)**

- **Focus:** Complexity and Concrete Example.
- **Task:** Create a "Toy Example" with small numbers (e.g., $p=61, q=53$) to walk the reader through the math numerically. Write the section on why factorization is hard (Computational Complexity).
- **Course Connection:** *Logic* (reasoning about algorithmic complexity) and concrete application.

### **Next Step**

Would you like me to generate the **"Toy Example"** with specific numbers for Member 3, or would you like a detailed walkthrough of the **Euler's Theorem proof** for Member 1?