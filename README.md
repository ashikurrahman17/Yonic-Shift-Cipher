<p align="center">
  <img src="./HSTU_Logo.png" alt="HSTU Logo" width="150">
</p>

<h2 align="center"><strong>Hajee Mohammad Danesh Science and Technology University</strong></h2>

<h3 align="center">Dinajpur-5200</h3>

---

<p align="center">
  <img src="https://img.shields.io/badge/Assignment-Mathematical%20Analysis%20for%20CS-16a085?style=for-the-badge&logo=codeforces&logoColor=white">
  <img src="https://img.shields.io/badge/Course-CSE%20361-2980b9?style=for-the-badge&logo=codesignal&logoColor=white">
  <img src="https://img.shields.io/badge/Algorithm-Yonic%20Shift%20Cipher-8e44ad?style=for-the-badge&logo=tryhackme&logoColor=white">
</p>

---

<h2 align="center" style="color:#2980b9;"><strong>🔐 Algorithm Name</strong></h2>

<h1 align="center" style="color:#8e44ad;"><strong>Yonic Shift Cipher</strong></h1>

---

<h2 align="center" style="color:#16a085;"><strong>🧑‍💻 Submitted By</strong></h2>

<p align="center">
  <strong>Name:</strong> Ashikur Rahman  
  <br>
  <strong>Student ID:</strong> 2102028  
  <br>
  <strong>Level:</strong> 3  
  <br>
  <strong>Semester:</strong> II  
  <br>
  <strong>Department:</strong> Computer Science and Engineering  
</p>

---

<h2 align="center" style="color:#16a085;"><strong>👨‍🏫 Submitted To</strong></h2>

<p align="center">
  <strong>Name:</strong> Pankaj Bhowmik  
  <br>
  <strong>Designation:</strong> Lecturer  
  <br>
  <strong>Department:</strong> Computer Science and Engineering  
</p>

---

# 📝 Assignment Report

---

## 📑 Table of Contents
- [1️⃣ Introduction](#1️⃣-introduction)
- [2️⃣ Algorithm and Pseudocode](#2️⃣-algorithm-and-pseudocode)
  - [2.1 Conceptual Overview](#🔥-21-conceptual-overview)
  - [2.2 Pseudocode](#💻-22-pseudocode)
- [3️⃣ Flowchart of the Algorithm](#3️⃣-🧠-flowchart-of-the-algorithm)
- [4️⃣ Experimental Example](#4️⃣-🌟-experimental-example)
- [5️⃣ Source Code Implementation](#5️⃣-💻-source-code-implementation)
- [🌸 Why the Name “Yonic Shift Cipher”?](#🌸-why-the-name-yonic-shift-cipher)
- [6️⃣ Conclusion](#6️⃣-📌-conclusion)

---

## 1️⃣ Introduction

The **Yonic Shift Cipher** is a modified substitution cipher designed to manipulate vowels and consonants separately within a text. Unlike traditional shift ciphers, this approach keeps vowels within the vowel set and consonants within the consonant set, shifting their positions internally by specified keys. This method preserves the letter's case and skips over the other set, providing an interesting variation on classical encryption techniques.  

---

## 2️⃣ Algorithm and Pseudocode

### 🔥 2.1 Conceptual Overview

- ✅ The alphabet is divided into two ordered lists:
  - **Vowels:** [A, E, I, O, U, Y]
  - **Consonants:** All other alphabet letters, excluding vowels.
- 🔐 **During encryption:**
  - Vowels are shifted within the vowel list by `v_key`.
  - Consonants are shifted within the consonant list by `c_key`.
- 🔄 All shifts wrap around circularly.
- 🔡 Case is preserved.
- 🛡 Non-alphabet characters remain unchanged.
- 🔓 Decryption shifts backward using the same keys.

---

### 💻 2.2 Pseudocode

```plaintext
Vowels = ['A', 'E', 'I', 'O', 'U', 'Y']
Consonants = ['B', 'C', 'D', 'F', 'G', 'H', 'J', 'K', 'L', 'M', 
              'N', 'P', 'Q', 'R', 'S', 'T', 'V', 'W', 'X', 'Z']

function encrypt(text, v_key, c_key):
    output = ""
    for each character ch in text:
        if ch is a letter:
            uppercase_ch = ch.upper()
            if uppercase_ch in Vowels:
                index = position of uppercase_ch in Vowels
                new_index = (index + v_key) mod length(Vowels)
                new_char = Vowels[new_index]
            else:
                index = position of uppercase_ch in Consonants
                new_index = (index + c_key) mod length(Consonants)
                new_char = Consonants[new_index]
            if ch is lowercase:
                new_char = new_char.lower()
            output += new_char
        else:
            output += ch
    return output

function decrypt(text, v_key, c_key):
    output = ""
    for each character ch in text:
        if ch is a letter:
            uppercase_ch = ch.upper()
            if uppercase_ch in Vowels:
                index = position of uppercase_ch in Vowels
                new_index = (index - v_key) mod length(Vowels)
                new_char = Vowels[new_index]
            else:
                index = position of uppercase_ch in Consonants
                new_index = (index - c_key) mod length(Consonants)
                new_char = Consonants[new_index]
            if ch is lowercase:
                new_char = new_char.lower()
            output += new_char
        else:
            output += ch
    return output
````

---

## 3️⃣ 🧠 Flowchart of the Algorithm

<p align="center">
  <img src="./flowchart.png" alt="Algorithm Flowchart" width="600">
</p>

---

## 4️⃣ 🌟 Experimental Example

### ✨ Input:

* Plaintext: `"Ashik"`
* Vowel Key: `2`
* Consonant Key: `3`

---

### ⚙️ Processing:

* Vowels in `"Ashik"`: `A`, `i`
* Consonants in `"Ashik"`: `s`, `h`, `k`

---

### 🔒 Encryption:

| Character | Type      | Index | New Index    | Encrypted Char |
| --------- | --------- | ----- | ------------ | -------------- |
| A         | Vowel     | 0     | (0+2)%6=2    | I              |
| s         | Consonant | 14    | (14+3)%20=17 | w              |
| h         | Consonant | 5     | (5+3)%20=8   | l              |
| i         | Vowel     | 2     | (2+2)%6=4    | u              |
| k         | Consonant | 7     | (7+3)%20=10  | n              |

**🔐 Encrypted Result:** `"Iwlun"`

---

### 🔓 Decryption:

| Character | Type      | Index | New Index    | Decrypted Char |
| --------- | --------- | ----- | ------------ | -------------- |
| I         | Vowel     | 2     | (2-2)%6=0    | A              |
| w         | Consonant | 17    | (17-3)%20=14 | s              |
| l         | Consonant | 8     | (8-3)%20=5   | h              |
| u         | Vowel     | 4     | (4-2)%6=2    | i              |
| n         | Consonant | 10    | (10-3)%20=7  | k              |

**✅ Recovered Plaintext:** `"Ashik"`

---

## 5️⃣ 💻 Source Code Implementation

### 🚀 Implementation in C++

```cpp
#include <bits/stdc++.h>
using namespace std;

const string vowels = "aeiouy";
const string consonants = "bcdfghjklmnpqrstvwxz";

map<char, int> v_map, c_map;

void initialize() {
    for (int i = 0; i < (int)vowels.size(); i++) {
        v_map[vowels[i]] = i;
        v_map[toupper(vowels[i])] = i; // handle uppercase vowels
    }
    for (int i = 0; i < (int)consonants.size(); i++) {
        c_map[consonants[i]] = i;
        c_map[toupper(consonants[i])] = i; // handle uppercase consonants
    }
}

int checkChar(char c) {
    if (v_map.find(c) != v_map.end()) return 0;
    if (c_map.find(c) != c_map.end()) return 1;
    return -1; // neither vowel nor consonant
}

string encrypt(string s, int v_key, int c_key){
    string temp;
    for(int i=0; i<s.size(); i++){
        char c = s[i];
        if(checkChar(c)==-1) {
            temp.push_back(c);
        } else {
            bool huh = isupper(c);
            if(huh) c = tolower(c);

            if(checkChar(c)==0){
                int pos = v_map[c];
                pos = (pos + v_key) % 6;
                c = vowels[pos];
            } else {
                int pos = c_map[c];
                pos = (pos + c_key) % 20;
                c = consonants[pos];
            }

            if(huh) c = toupper(c);
            temp.push_back(c);
        } 
    }
    return temp;
}

string decrypt(string s, int v_key, int c_key){
    string temp;
    for(int i=0; i<s.size(); i++){
        char c = s[i];
        if(checkChar(c)==-1) {
            temp.push_back(c);
        } else {
            bool huh = isupper(c);
            if(huh) c = tolower(c);

            if(checkChar(c)==0){
                int pos = v_map[c];
                pos = ((pos - v_key) % 6 + 6) % 6; // safe modulo
                c = vowels[pos];
            } else {
                int pos = c_map[c];
                pos = ((pos - c_key) % 20 + 20) % 20; // safe modulo
                c = consonants[pos];
            }

            if(huh) c = toupper(c);
            temp.push_back(c);
        }
    }
    return temp;
}

int main() {
    initialize();

    cout << "Enter the plain-text: ";
    string s; getline(cin, s);
    cout << "Enter the keys (vowel shift c, consonant shift c): ";
    int v_key, c_key; cin >> v_key >> c_key;

    string enc = encrypt(s, v_key, c_key);
    cout << "The encrypted text is: " << enc << endl;

    string dec = decrypt(enc, v_key, c_key);
    cout << "The decrypted text is: " << dec << endl;

    return 0;
}
```
 ## Sample Input-Output:
<p align="center">
  <img src="./test.png" alt="Test Case" width="90%">
</p>
---

## 🌸 Why the Name “Yonic Shift Cipher”?

The name **“Yonic Shift Cipher”** reflects the unique design and symbolism:

* 🌟 **“Y” as a Vowel:**
  In this cipher, **Y** is treated as a vowel—a rare and essential design choice that impacts the shifting mechanism.

* 🌱 **Symbolism of Origin/Core:**
  The term **“Yonic”** metaphorically suggests a **source or central element**, just like vowels and consonants form the core of language.

* 🎨 **Memorable & Elegant:**
  This poetic branding gives the cipher its own identity, making it stand out from typical classical ciphers.

---

## 6️⃣ 📌 Conclusion

The **Yonic Shift Cipher** provides an engaging variation of classical substitution ciphers by shifting vowels and consonants within their respective sets using simple keys. This technique preserves the natural structure of the text while enhancing encryption complexity, making it perfect for understanding core cryptographic concepts.

---
