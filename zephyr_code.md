---
layout: default
title: Zephyr Code
---

# 📘 **Zephyr Code Reference**

Zephyr Code is a poetic encryption system developed by the covert military branch employed by the Aria kingdoms, Zephyr Ops. It is used to securely transmit military, political, surveillance, and logistical information through layers of surrealist poetry. Trained operatives interpret these messages using codified triggers, symbolic structures, and context-aware rules.

---
---

## **Title – Urgency**

The **title of the poem encodes the urgency** of the message. It is the **only part** of the message where urgency is ever encoded. The **body of the poem does not affect urgency**, even if it contains urgency-like words.

---

### 🔺 Urgency Levels – Definition & Handling

| **Urgency Level** | **Handling Instructions**                                                                                           | **Trigger in Title**                                            | **Example Titles**                        |
|-------------------|---------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|-------------------------------------------|
| **Flash**         | Must be delivered and read **immediately**. **Risks may be taken** to ensure delivery. Security may be compromised. | Title's **first word** is a **positional** word.                | *“Above the Storm”*, *“Beyond the Ridge”* |
| **Immediate**     | Deliver as soon as possible. Must be **read upon delivery**. No delay allowed.                                      | No Flash indicator. Contains a **sensory word**.                | *“The Quiet River”*, *“Blue Smoke Path”*  |
| **Priority**      | Deliver and read **as soon as convenient**, preferably within the same day. **Delay up to a day** is acceptable.    | No Flash or Immediate indicators. Contains **emotion** keyword. | *“Grief in the Snow”*, *“A Joyful Sun”*   |
| **Routine**       | Deliver and archive if needed. **Reading is optional.** Standard reports, situational logs.                         | Lacks all Flash, Immediate, and Priority indicators.            | *“The Old Lantern”*, *“Baylight Wind”*    |

---

### 📖 Keyword Categories

#### **Flash – Positional Keywords (First Word Only)**

If the **first word** of the title is positional, the message is **Flash**.

* Examples: **Above**, **Below**, **Beyond**, **Beneath**, **Under**, **Over**, **Within**, **Across**

**Note:** *Only the first word matters.*

* “Beyond the Moon” = Flash
* “The Moon Beyond” = Not Flash

---

#### **Immediate – Sensory Keywords**

If no Flash keyword is present, and the title contains **sensory** language, the urgency is **Immediate**.

* **Color**: red, blue, gold, pale, silver, lavender
* **Sound**: quiet, whisper, loud, hush, echo
* **Smell/Taste**: bitter, sweet, sour, aroma
* **Texture/Feel**: rough, soft, warm, cold, slick

note: Any word that otherwise is a sensory word but not one of these categories, is not counted. for example, temperatue, pressure, brigthness,  

---

#### **Priority – Emotional Keywords**

If no Flash or Immediate indicator is found, check for **emotional language**. These indicate **Priority** urgency.

* Examples: joy, sorrow, fear, grief, anger, pride, despair, rage, surprise

---

#### **Routine – Default**

If the title lacks **all urgency keywords**, the message is **Routine**.

* *“The Cow by the Moon”*, *“Starsparkle”*, *“The Hand Forward”*

---

### 🧠 Notes

* The **urgency system** prioritizes the **most critical indicator** found in this order:
  `Flash > Immediate > Priority > Routine`
* **Nothing else is encoded in the title**.
  For example:

  * “Mountain” in a title does **not** mean **north**.
  * “Quiet” in a title is **Immediate** (sensory), but in the body it means **clock time**.

---



## **Numbers – Numeric Encoding**

The **body** of a Zephyr Code poem encodes numbers via **trigger words**, **syllable or override counts**, and **mathematical functions**. Only words **after** a trigger on that **same line** participate in number encoding, scoped by commas, periods, or line breaks.

---

### 🔺 Core Triggers & Functions

| **Trigger Word**  | **Function** | **Behavior**                                               |
| ----------------- | ------------ | ---------------------------------------------------------- |
| **Into**, **And** | `Add()`      | Sum the syllables or override values of each operand       |
| **By**, **Not**   | `Mul()`      | Multiply the syllables or override values of each operand  |
| **Or**, **From**  | `Cat()`      | Concatenate the syllable counts or override values         |
| **For**, **If**   | `Sub()`      | First operand minus the **sum** of all subsequent operands |

* **Operand Value**: Each word is and operand. The number of syllables of the value of the operand. There are a few exceptions.
* **Scope**: Operands are words **after** the trigger, up to a **comma**, **period**, or **end of line**.
* **Zero Encoding**: Trigger with **no operands** yields **0**.

---

### 🧪 Basic Examples

* **Add()**

  > “The cheese and the green arrow” → Add(1 + 1 + 2) = **4**

* **Mul()**

  > “When by mountain holding overview” → Mul(2 × 2 × 3) = **12**

* **Cat()**

  > “Either run or flow rudely toward oblivion” → Cat(1  ,2  ,2  ,3) = **1223**

* **Sub()**

  > “for tomorrow never dies” → Sub(10 – (5 + 1)) = **4**

---

### 🔄 Value Override Keywords

Several keywords receive alternative values instead of being based on syllable count.

#### Fixed Value Keywords

This sets of words have a **fixed values** when used. not syllables.

| **fixed 10** | **Fixed 5** |
|--------------|-------------|
| Shadow       | Glow        |
| Tomorrow     | Yesterday   |
| So           | Well        |
| Always       | Never       |

- The fixed 5 keywords are always treated as having a value of 5.
- The fixed 10 keywords are treated as having the value of 10 in the functions Add(), Mul() and Sub(). They receive the value of 0 when used in Cat()

> **Example:**
> “or is yesterday” → Cat(is=1, yesterday=5) = **15**

---

#### 🔢 Digit Overrides

Any **number** (0–9) as a digit or word, uses this **override mapping** instead of syllable count:

|  Digit  | Override | |  Digit  | Override |
| :-----: | :------: |-| :-----: | :------: |
|  0/zero |     4    | |  5/five |     8    |
|  1/one  |     7    | |  6/six  |     0    |
|  2/two  |     1    | | 7/seven |     6    |
| 3/three |     9    | | 8/eight |     2    |
|  4/four |     3    | |  9/nine |     5    |

> **Example:**
> “from one nine three” → Cat(1→7, 9→5, 3→9) = **759**

---

### 🔄 Nested Triggers & Comma Scope

* **Inner triggers** (closest to their operands) compute first, up to the first **comma**, then their result feeds the **outer** trigger.

> **Example:**
>
> ```
> mountain by from river bank, to legend
> ```
> 1. Mul(Cat(2,1),1,2)
> 2. Inner `from river bank` → Cat(2,1) = **21**
> 3. Outer `by … to legend` → Mul(21,1,2) = **42**

---

### 📜 Period Scope Extension

* A **period (`.`)** at line end **extends** the trigger’s operand list onto the **next line**, until a line **without** trailing period.

> **Example:**
>
> ```
> to the sky, into the cloud.  
> be on the side
> ```
>
> → Add(1+1+1+1+1+1+1) = **7**

---

### ➖ Subtraction Function (`Sub()`)

* **Triggers**: `for`, `if`
* **Semantics**:

  1. **First operand** = value up to first comma or next trigger.
  2. **Remaining operands** are **summed**, then **subtracted** from the first.

> **Example:**
> “for tomorrow never dies” → Sub(10,5+1) = **4**

---

### ➖ Negative via Plural & Past Markers

* If the **last word** is a **plural noun** (ends in “s”) or a **past‐tense verb**, it is **excluded** from operands and **negates** the final result.

> **Examples:**
>
> * “for tomorrow never dies, shocked” → Sub(10,5+1) = 4 → **–4**
> * “into the drifting clouds” → Add(1+2) = 3 → **–3**

---

### 🧠 Notes & Edge Cases

- Anything before the first number trigger keyword can encode something else. Typically the context of the number being encoded.  
* **Per-Line Scope:** Triggers do **not** cross stanza.
* **Multiple Numeric Lines:** Decode each in order; combine or reference as needed.
* **Mixing Functions:** Allowed—just resolve inner triggers first.
* **Zero as Word:** “zero” → override value 4, so use “six” to encode 0 if needed.
* **Modifiers & Special Keywords:** Any override or special keyword takes precedence over raw syllable counts.



