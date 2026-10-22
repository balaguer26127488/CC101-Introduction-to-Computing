# Activity 6: Introduction to Computing

* **Name:** Mark Joseph A. Balaguer
* **Block:** 1-1
* **Computer Unit Used:** Windows 11 Laptop (simulated)
* **Date:** 2026-10-20

> **Note:** This is a completed sample using imagined computer and GitHub details. Replace personal fields, peer-review information, and GitHub upload results with your actual information. The worksheet itself requires you to create and upload `README.md`.

---

## V. Data and Findings

### Table 1. Problem Analysis for Problem 1 (Part A)

| Item | Your Answer |
| :--- | :--- |
| **Restated problem (your own words)** | Create a program that accepts a whole decimal number 0 or greater and converts it into binary. |
| **Input** | A whole number in decimal (base 10), 0 or greater. |
| **Output** | The binary (base 2) representation of the input number. |
| **Processes (operations)** | Find the remainder using $n \text{ MOD } 2$; divide using $n \text{ DIV } 2$; put each remainder at the left of the binary string. |
| **Loop condition (when the loop stops)** | Repeat while $n > 0$; stop when $n = 0$. |
| **Variables needed** | `n`, `remainder`, `binary` |
| **13 and 25 in binary (computed by hand)** | $13 = 1101$, $25 = 11001$ |

---

### Box 1. Pseudocode for Problem 1 (Part B)

```text
START
INPUT n
SET binary = ""
IF n = 0 THEN
    SET binary = "0"
ELSE
    WHILE n > 0 DO
        SET remainder = n MOD 2
        SET binary = remainder + binary
        SET n = n DIV 2
    ENDWHILE
ENDIF
DISPLAY binary
END
```

---

### Figure 1. Flowchart for Problem 1 (Part C)

```text
(START)
   |
/ Input n /
   |
< n = 0? > -- Yes --> [ binary = "0" ] --------+
   |                                          |
  No                                          |
   |                                          |
[ binary = "" ]                               |
   |                                          |
   +<-----------------------+                 |
   |                        |                 |
< n > 0? > -- No --> / Display binary /       |
   |                        |                 |
  Yes                       |                 v
   |                        |               (END)
[ remainder = n MOD 2 ]     |
[ binary = remainder + binary ]
[ n = n DIV 2 ]             |
   |                        |
   +------------------------+
```

---

### Table 2. Trace of Problem 1 with Input 13 (Part C)

| Pass | `n` (before) | `n MOD 2` (remainder) | `n DIV 2` (new `n`) | `binary` (so far) |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 13 | 1 | 6 | `1` |
| **2** | 6 | 0 | 3 | `01` |
| **3** | 3 | 1 | 1 | `101` |
| **4** | 1 | 1 | 0 | `1101` |

**Value displayed at the end:** `1101`

---

### Table 3. Test Cases for Problem 1 (Part C)

| Case | Decimal Input | Binary (by hand) | Binary from pseudocode | Match? |
| :---: | :---: | :---: | :---: | :---: |
| **1** | 0 | `0` | `0` | Y |
| **2** | 5 | `101` | `101` | Y |
| **3** | 13 | `1101` | `1101` | Y |
| **4** | 25 | `11001` | `11001` | Y |
| **5** | 255 | `11111111` | `11111111` | Y |

---

### Box 2. Pseudocode for Problem 2 (Part D)

```text
START
INPUT binary
SET decimal = 0
SET place = 1
WHILE binary > 0 DO
    SET digit = binary MOD 10
    IF digit != 0 AND digit != 1 THEN
        DISPLAY "Invalid binary number"
        END
    ENDIF
    SET decimal = decimal + (digit * place)
    SET place = place * 2
    SET binary = binary DIV 10
ENDWHILE
DISPLAY decimal
END
```

---

### Figure 2. Flowchart for Problem 2 (Part D)

```text
(START)
   |
/ Input binary /
   |
[ decimal = 0; place = 1 ]
   |
   +<------------------------------------+
   |                                     |
< binary > 0? > -- No --> / Display decimal / --> (END)
   |
  Yes
   |
[ digit = binary MOD 10 ]
   |
< digit is 0 or 1? > -- No --> / Display invalid / --> (END)
   |
  Yes
   |
[ decimal = decimal + (digit * place) ]
[ place = place * 2 ]
[ binary = binary DIV 10 ]
   |
   +-------------------------------------+
```

---

### Table 4. Test Cases for Problem 2 (Part D)

| Case | Binary Input | Decimal (by hand) | Decimal from pseudocode | Match? |
| :---: | :---: | :---: | :---: | :---: |
| **1** | `1101` | 13 | 13 | Y |
| **2** | `101010` | 42 | 42 | Y |
| **3** | `11111111` | 255 | 255 | Y |
| **4** | `10000000` | 128 | 128 | Y |

---

### Bonus Box. Extended Pseudocode: Decimal to Base 2, 8, or 16

```text
START
INPUT n
INPUT base
IF n < 0 OR (base != 2 AND base != 8 AND base != 16) THEN
    DISPLAY "Invalid input or base"
    END
ENDIF

IF n = 0 THEN
    DISPLAY "0"
    END
ENDIF

SET digits = "0123456789ABCDEF"
SET result = ""
WHILE n > 0 DO
    SET remainder = n MOD base
    SET character = character at position remainder in digits
    SET result = character + result
    SET n = n DIV base
ENDWHILE
DISPLAY result
END
```

---

### README.md Content (Part E)

```markdown
# CC 101 Computing Portfolio

This repository contains my laboratory outputs and documentation for **CC 101 Introduction to Computing** at **Sorsogon State University Bulan Campus**.

## About Me

- **Name:** Mark Joseph A. Balaguer
- **Program and Section:** BSCS 1-1
- **Interests:** Learning technology, solving problems, and playing games
- **Goal:** My goal is to improve my programming and problem-solving skills and become a capable computing professional.

## Course Information

| Item | Details |
| :--- | :--- |
| **Course** | CC 101 Introduction to Computing |
| **Instructor** | [Instructor's name] |
| **Academic Year** | 2026-2027 |

## Portfolio Contents

1. [Week 7 - Pseudocode and Flowcharts](week07-algorithms/)
2. More activities will be added each week.

## Sample Pseudocode: Decimal to Binary

```text
START
INPUT n
SET binary = ""
IF n = 0 THEN
    SET binary = "0"
ELSE
    WHILE n > 0 DO
        SET remainder = n MOD 2
        SET binary = remainder + binary
        SET n = n DIV 2
    ENDWHILE
ENDIF
DISPLAY binary
END
```

## My Workspace

![My laboratory computer](images/my-pc.jpg)

*Last updated: 2026-10-20*
```

---

### Table 5. README.md File Check (Part E)

| Item | Your Findings |
| :--- | :--- |
| **Full folder path of `cc101-portfolio`** | `C:\Users\Student\Documents\cc101-portfolio` *(simulated)* |
| **File name shown in File Explorer** | `README.md` |
| **Type shown in File Explorer (Details view)** | Markdown File / MD file *(may show a text document depending on Windows settings)* |
| **Size of `README.md` shown by `dir` (bytes)** | Sample estimate: about 900 bytes; exact size depends on saved content and encoding. |
| **Does `type README.md` show your Markdown text? (Y/N)** | Y |
| **Notepad formatted view available? (Y/N)** | Y, assuming the Markdown view is available in this Notepad version. |
| **Elements that appeared formatted in Notepad** | Headings, bold and italic text, lists, and horizontal rule if Markdown view is supported; tables, images, and code blocks may appear as plain text. |

---

### Table 6. Peer Review Checklist (Part F)

**Owner of the README:** Mark Joseph A. Balaguer  
**Reviewer's name:** ____________________

| Element | Markdown Used | Present and Correct? (sample) |
| :--- | :--- | :---: |
| **Level-1 heading** | `#` | Y |
| **Level-2 headings** | `##` | Y |
| **Paragraph** | Text with blank line before and after | Y |
| **Bold and italic text** | `**bold**` `*italic*` | Y |
| **Bulleted list** | `- item` | Y |
| **Numbered list** | `1. item` | Y |
| **Table** | `|---|` header separator | Y |
| **Link** | `[text](url)` | Y |
| **Image** | `![alt](path)` | Y *(image file must be uploaded to display)* |
| **Code block** | Lines between three backticks | Y |
| **Horizontal rule** | `---` | Y |
| **File saved as `README.md` (not `.txt`)** | — | Y |

---

### Table 7. GitHub Submission (Part G, Take-Home)

| Item | Your Answer |
| :--- | :--- |
| **GitHub username** | Not created / to be filled after registration |
| **Repository URL** | To be filled after creating and uploading to GitHub |
| **Date uploaded (YYYY-MM-DD)** | Not uploaded yet |
| **Does the README display formatted on GitHub? (Y/N)** | To be checked after upload |
| **Elements that did not display as expected, and why** | The image may not appear until `images/my-pc.jpg` is uploaded, and the `week07-algorithms` link needs files in that folder. |

---

## VI. Realization (Reflection)

1. **Which was easier for you to create, the pseudocode or the flowchart? Why?**  
   The pseudocode was easier for me because I could write the steps in order using simple words and commands. The flowchart took more planning because I had to choose the correct symbols and connect them with arrows.

2. **Did tracing and testing reveal any errors in your pseudocode or flowcharts? Describe what you found and how you corrected it.**  
   Testing reminded me to handle the input 0 separately in the decimal-to-binary converter. Without that condition, the program could display an empty result. I corrected it by displaying 0 when the input is 0 and then checked the other test cases.

3. **How is writing a README in Markdown different from typing a document in Microsoft Word?**  
   Markdown is written as plain text using symbols such as `#`, `**`, and hyphens to create headings, emphasis, and lists. Microsoft Word uses a visual toolbar to format a document, while Markdown can be viewed in a formatted way by platforms such as GitHub.

4. **How can a GitHub portfolio help you as a future computing professional?**  
   A GitHub portfolio can organize my activities, projects, and documentation in one place. It can help me track my progress, share my work with instructors or employers, and demonstrate my programming and problem-solving skills.

---

> **Submission Reminder:** The algorithm answers and README example are completed samples. The real folder path, exact file size, peer review, GitHub username, repository URL, and upload status cannot be known without performing those steps, so they are clearly marked as simulated or pending.
