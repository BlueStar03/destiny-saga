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

- Examples: **Above**, **Below**, **Beyond**, **Beneath**, **Under**, **Over**, **Within**, **Across**

**Note:** *Only the first word matters.*

- “Beyond the Moon” = Flash
- “The Moon Beyond” = Not Flash

---

#### **Immediate – Sensory Keywords**

If no Flash keyword is present, and the title contains **sensory** language, the urgency is **Immediate**.

- **Color**: red, blue, gold, pale, silver, lavender
- **Sound**: quiet, whisper, loud, hush, echo
- **Smell/Taste**: bitter, sweet, sour, aroma
- **Texture/Feel**: rough, soft, warm, cold, slick

note: Any word that otherwise is a sensory word but not one of these categories, is not counted. for example, temperatue, pressure, brigthness,  

---

#### **Priority – Emotional Keywords**

If no Flash or Immediate indicator is found, check for **emotional language**. These indicate **Priority** urgency.

- Examples: joy, sorrow, fear, grief, anger, pride, despair, rage, surprise

---

#### **Routine – Default**

If the title lacks **all urgency keywords**, the message is **Routine**.

- *“The Cow by the Moon”*, *“Starsparkle”*, *“The Hand Forward”*

---

### 🧠 Notes

- The **urgency system** prioritizes the **most critical indicator** found in this order:
  `Flash > Immediate > Priority > Routine`
- **Nothing else is encoded in the title**.
  For example:

  - “Mountain” in a title does **not** mean **north**.
  - “Quiet” in a title is **Immediate** (sensory), but in the body it means **clock time**.

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

- **Operand Value**: Each word is and operand. The number of syllables of the value of the operand. There are a few exceptions.
- **Scope**: Operands are words **after** the trigger, up to a **comma**, **period**, or **end of line**.
- **Zero Encoding**: Trigger with **no operands** yields **0**.

---

### 🧪 Basic Examples

- **Add()**

  > “The cheese and the green arrow” → Add(1 + 1 + 2) = **4**

- **Mul()**

  > “When by mountain holding overview” → Mul(2 × 2 × 3) = **12**

- **Cat()**

  > “Either run or flow rudely toward oblivion” → Cat(1  ,2  ,2  ,3) = **1223**

- **Sub()**

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

- **Inner triggers** (closest to their operands) compute first, up to the first **comma**, then their result feeds the **outer** trigger.

> **Example:**
>
> ```text
> mountain by from river bank, to legend
> ```
>
> 1. Mul(Cat(2,1),1,2)
> 2. Inner `from river bank` → Cat(2,1) = **21**
> 3. Outer `by … to legend` → Mul(21,1,2) = **42**

---

### 📜 Period Scope Extension

- A **period (`.`)** at line end **extends** the trigger’s operand list onto the **next line**, until a line **without** trailing period.

> **Example:**
>
> ```text
> to the sky, into the cloud.  
> be on the side
> ```
>
> → Add(1+1+1+1+1+1+1) = **7**

---

### ➖ Subtraction Function (`Sub()`)

- **Triggers**: `for`, `if`
- **Semantics**:

  1. **First operand** = value up to first comma or next trigger.
  2. **Remaining operands** are **summed**, then **subtracted** from the first.

> **Example:**
> “for tomorrow never dies” → Sub(10,5+1) = **4**

---

### ➖ Negative via Plural & Past Markers

- If the **last word** is a **plural noun** (ends in “s”) or a **past‐tense verb**, it is **excluded** from operands and **negates** the final result.

> **Examples:**
>
> - “for tomorrow never dies, shocked” → Sub(10,5+1) = 4 → **–4**
> - “into the drifting clouds” → Add(1+2) = 3 → **–3**

---

### 🧠 Notes & Edge Cases

- Anything before the first number trigger keyword can encode something else. Typically the context of the number being encoded.  
- **Per-Line Scope:** Triggers do **not** cross stanza.
- **Multiple Numeric Lines:** Decode each in order; combine or reference as needed.
- **Mixing Functions:** Allowed—just resolve inner triggers first.
- **Zero as Word:** “zero” → override value 4, so use “six” to encode 0 if needed.
- **Modifiers & Special Keywords:** Any override or special keyword takes precedence over raw syllable counts.

---

---

## 🧭 **Directions – Spatial Encoding**

Zephyr Code embeds **directional information** in the poem’s body via terrain keywords and optional anchors. Directions may be expressed as **cardinal**, **intercardinal**, or **by-direction** bearings relative to either the **reader’s** or **writer’s** position.

---

### 🔹 1. Cardinal Directions

| **Keyword**  | **Meaning** |
| ------------ | ----------- |
| **Mountain** | North       |
| **Canyon**   | East        |
| **Swamp**    | South       |
| **Bay**      | West        |

> *Example:*
> “The mountain cave is shallow” → **North** (reader’s perspective)

---

### 🔸 2. Reference Origin

- **Implicit (Default):** No anchor → direction **from the reader’s location**
- **Explicit “Here” (Writer):**

  - **Road**, **Way**, **Trail** → “Here” = writer’s location
- **Explicit “There” (Reader):**

  - **Bank**, **Edge**, **Brink** → “There” = reader’s location

| **Anchor**        | **Meaning**               |
| ----------------- | ------------------------- |
| Bank, Edge, Brink | There (reader’s location) |
| Road, Way, Trail  | Here (writer’s location)  |

> *Examples:*
>
> - “Mountain bank” → North from the **reader’s** position
> - “Canyon way”   → East from the **writer’s** position

---

### 🔹 3. Intercardinal (Diagonal) Directions

#### a. **Compound Keywords** (Simple Diagonals)

Concatenate two cardinal keywords:

| Compound    | Direction |
| ----------- | --------- |
| Mountainbay | Northwest |
| Swampcanyon | Southeast |
| Canyonbay   | Northeast |
| Bayswamp    | Southwest |

> *Example:*
> “In the mountainbay glade” → Northwest

#### b. **By-Direction Bearings** (Dominant + Adjacent)

```text
[PrimaryDirection]side [SecondaryDirection]
```

- **“side”** attaches to the **dominant** axis.

| Phrase           | Meaning            |
| ---------------- | ------------------ |
| Canyonside swamp | East by Southeast  |
| Swampside canyon | South by Southeast |
| Bayside mountain | West by Northwest  |
| Mountainside bay | North by Northwest |

> *Example:*
> “Canyonside swamp the banners fall” → East by Southeast

---

### 🧠 Notes

- **No anchor** → reader’s perspective (implicit).
- **Bank/Edge/Brink** → reader’s perspective (explicit).
- **Road/Way/Trail** → writer’s perspective (explicit).
- Avoid mixing cardinal and intercardinal on the same line to prevent ambiguity.

---

---

## 🗓️ **Date & Day – Month & Day-of-Month**

This section covers **month** and **day** encoding in Zephyr Code. Use the **date trigger** to mark the next line as a **month**, and **base + offset** keywords to encode the **day**.

---

### 🔺 1. Month Encoding

#### a. **Date Trigger**

If a line **ends** with **any** of these phrases **including the comma**, **ignore** all other encodings on that line and treat the **next line** as the month specifier:

> “by and by,”
> “Over there,”
> “Here and there,”
> “Soon enough,”
> “All around,”

---

#### b. **Baseline by Creature**

On the following line, the **first creature** mentioned sets a **baseline month** (the 2nd month of its season):

| **Creature Type**         | **Season** | **Baseline Month** |
| ------------------------- | ---------- | ------------------ |
| **Legless** (or > 4 legs) | Spring     | April (4th)        |
| **Biped** (2 legs)        | Summer     | July (7th)         |
| **Quadruped** (4 legs)    | Autumn     | October (10th)     |
| **Winged**                | Winter     | January (1st)      |

---

#### c. **Verb-Tense Shift**

A **verb** immediately after the creature shifts the month by **±1**:

- **Present/Future-tense** → **+1 month**
- **Past-tense** → **–1 month**
- **No verb** → **baseline**

> **Examples:**
>
> ```text
> Soon enough,
> the robin eats
> ```
>
> – Winged → January
> – “eats” (present) → **February**
>
> ```text
> Here and there,
> the butterfly swooped
> ```
>
> – Winged → January
> – “swooped” (past) → **December**

---

### 🔺 2. Day-of-Month Encoding

#### a. **Base Keywords**

First word picks which block of 8 days:

| **Keyword** | **Covers Days** | **Base Value** |
| ----------- | --------------- | -------------- |
| **heart**   | 1 – 8           | 1              |
| **mind**    | 9 – 16          | 9              |
| **breath**  | 17 – 24         | 17             |
| **song**    | 25 – 32         | 25             |

> **Example:** “mind” → Day **9**

---

#### b. **Offset Keywords**

Second word adds 0 – 7 days to the base. Use **either** height or fullness lists—only the **first** offset word counts per phrase:

| **Offset** | **Height Word** | **Fullness Word** | **Value** |
| ---------- | --------------- | ----------------- | --------- |
| +0         | flat            | empty             | 0         |
| +1         | low             | trace             | 1         |
| +2         | lift            | bit               | 2         |
| +3         | rise            | some              | 3         |
| +4         | climb           | half              | 4         |
| +5         | high            | brim              | 5         |
| +6         | peak            | spill             | 6         |
| +7         | summit          | burst             | 7         |

> **Examples:**
>
> - “empty heart” → 1 + 0 = **1**
> - “with half breath ran” → 17 + 4 = **21**
> - “be mindful of the rise” → 9 + 3 = **12**

---

#### c. **Standalone Keywords**

- **Base alone** → its **base day**

  - “breath” → **17**
- **Offset alone** → **days ahead** (0–7) by default

  - “some” → **in 3 days**

##### Trend Modifiers for Past vs. Future

Attach a **trend** keyword to specify direction explicitly:

| **Trend**    | **Keywords**                    | **Effect**     |
| ------------ | ------------------------------- | -------------- |
| **Positive** | harsh, bask, laze, savor, dream | Future (ahead) |
| **Negative** | hush, cover, toil, shun, dread  | Past (ago)     |

> **Examples:**
>
> - “and some while ago” → +3 days → **3 days ago**
> - “a trace dream of tomorrow” → +1 day → **in 1 day**
> - “on the cover of the peak” → +6 days → **6 days ago**

---

### 🧠 **Integration Notes**

1. **Date trigger lines** (`Soon enough,` etc.) are **single-use**: they ignore other encodings.
2. **Month line** must immediately follow trigger.
3. **Day phrases** may appear anywhere in the body; treat each independently.
4. **No cross-stanza** or **literal-block** escapes unless nullified.

---

---

## ☁️ **Weather – Conditions & Severity**

Zephyr Code conveys **weather conditions** and their **intensity** via spatial keywords and trend modifiers, all within the poem’s body.

---

### 🔹 1. Weather Condition Keywords

| **Keyword** | **Condition** |
| ----------- | ------------- |
| **up**      | Clear         |
| **above**   | Clear snow    |
| **under**   | Storm         |
| **below**   | Snowstorm     |
| **front**   | Rain          |
| **forward** | Snow          |
| **back**    | Windy         |
| **behind**  | Foggy         |

> **Examples:**
>
> - “up the mountain way” → **Clear skies** north of here
> - “below the star chaser’s way” → **Snowstorm** here
> - “in front of the rusted bucket” → **Rain** at the palace

---

### 🔸 2. Intensity Modifiers

Apply **trend keywords** to adjust **temperature** (with clear skies) or **severity** (with other conditions). Multiple modifiers (same or mixed) **stack** to increase effect.

| **Trend**    | **Keywords**                    |
| ------------ | ------------------------------- |
| **Positive** | harsh, bask, laze, savor, dream |
| **Negative** | hush, cover, toil, shun, dread  |

#### a. Temperature (Clear or Snow-Clear)

- **Positive** → warm → hot → scorching
- **Negative** → cool → cold → freezing

> **Examples:**
>
> - “Up the harsh mountain way” → clear & **warm**
> - “Dream up the harsh mountain way” → clear & **hot**
> - “cover above the cloudplain” → light snowfall (clear snow & mild)

#### b. Severity (Storm, Rain, Wind, Fog)

- **Positive** → **strong** → **severe**
- **Negative** → **mild** → **light**

> **Examples:**
>
> - “laze under the oak” → **strong storm**
> - “cover beneath the oak” → **mild storm**
> - “back the summit” → **windy** & default severity
> - “dread back the summit” → **light wind**

---

### 🧠 Notes & Edge Cases

- **Adjacency:** Trend keywords must be **directly adjacent** to the condition keyword (before or after) to apply.
- **Stacking:** When multiple trend words flank the condition, the **total count** determines intensity (e.g., two positives = one level above hot → maybe “scorching”).
- **No modifier:** Condition is reported at base intensity (e.g., “under the valley” → storm at normal strength).
- **Line scope:** Does not cross stanza (`//`) or literal-block boundaries without nullifiers.

---

With this, Zephyr operatives can poetically report **what** the sky does and **how strongly**—all hidden in their verses.

---

Understood—let’s remove the “Object alone” entry. Here’s the revised **Identities** snippet:

---

## 👤 **Identities – People, Places & Roles**

### 🔹 1. Individual & Group Encoding

| **Form**                                                                       | **Meaning**                                                                                                |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------- |
| **Colored Object**<br>*(red stone, blue leaf, lavender sand)*                  | An **unimportant** individual                                                                              |
| **Plural Object**<br>*(red leaves, turquoise bells)*                           | A **group** of unimportant individuals                                                                     |
| **Action-Adjective + Object**<br>*(ringing bell, trailing leaf)*               | An **important** individual                                                                                |
| **Color + Object + Verb**<br>*(the red leaf trails, the turquoise bell rings)* | An unimportant person **becoming important**<br>—subsequent mentions drop the color (e.g. “trailing leaf”) |

> **Examples:**
>
> - **Red lamp** → Store keeper
> - **Falling stone** → General Lan
> - **Falling stones** → General Lan’s army
> - **Blue bridge** → A random person under surveillance
> - **Blue bridge laughs** → That person is now important (Captain of the Guard)
> - **Laughing bridge** → Captain of the Guard
>
> *Note: Pure object words (e.g. “leaf”, “stone”) carry no identifier on their own—they’re just poetic padding unless modified.*
> *Note: Actual “who” each symbol refers to is shared through a separate secure channel.*

---

### 🔸 2. Place Encoding

| **Form**                                                                             | **Meaning**             |
| ------------------------------------------------------------------------------------ | ----------------------- |
| **Material/Texture + Object**<br>*(wooden lamp, tin candle, smooth rock, spiny cup)* | A specific **location** |

> **Examples:**
>
> - **Wooden lamp** → Town center
> - **Tin candle** → Guard barracks
> - **Smooth rock** → Palace
> - **Spiny cup** → Kelly Hill

---

### ✴️ 3. Participant Roles

| **Keyword** | **Role**                                      |
| ----------- | --------------------------------------------- |
| **moon**    | Writer of the message (*Zephyr Murmur*)       |
| **sun**     | Intended recipient (*Zephyr Whisper/Silence*) |
| **star**    | Spy (*Zephyr Rumor*)                          |
| **twinkle** | Assassin (*Zephyr Hush*)                      |
| **comet**   | Courier (*Echo*)                              |
| **aurora**  | Thunder Ops member                            |
| **nova**    | The Queen                                     |
| **meteor**  | Enemy                                         |

> **Usage Examples:**
>
> - *“Moon flows into canyon road”* → Writer is moving east.
> - *“Star hues the trailing leaf”* → Spy assigns a new ID to that important person.
> - *“Meteor strikes behind the smooth rock”* → Enemy attacked the palace under foggy conditions.

---

With these patterns, Zephyr Code can reference anyone or anywhere in your world—**all through the poetry itself**.

---

---

## ⚔️ **Movement – Advance, Stationary & Retreat**

Zephyr Code conveys **agent movement** via **action verbs** applied to established **identifiers**. Verbs themselves **cannot** double as identifiers—this avoids ambiguity. Destination or direction may be given via location anchors or cardinal keywords.

---

### 🔹 1. Forward Movement Verbs

| **Verbs**                     | **Meaning**                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------- |
| **fail**, **flow**, **swing** | The subject is **moving** in the specified direction or toward the specified location |

- **Syntax:**

  ```text
  <Identifier> <verb> [to/into/…] <Destination or Direction>
  ```

- **If no direction given:** movement is understood but undirected.

> **Examples:**
>
> - “Red sand fails” → *Red Sand* is moving (direction unspecified)
> - “Blue grass flows to rocky boot” → Lt. Dan is moving **toward West Town**
> - “Falling stones swing far from the mountain” → Gen. Lan’s army is moving **north**

---

### 🔸 2. Stationary Verbs

| **Verbs**                      | **Meaning**                                           |
| ------------------------------ | ----------------------------------------------------- |
| **float**, **shift**, **rise** | The subject is **holding position**, staying in place |

> **Examples:**
>
> - “Blue grasses float” → Lt. Dan’s army remains in place
> - “Falling stone shifts on the bay road” → Gen. Lan is stationary **west** from here

---

### 🔹 3. Retreat (Reverse Movement) Verbs

| **Verbs**                      | **Meaning**                                                                         |
| ------------------------------ | ----------------------------------------------------------------------------------- |
| **calm**, **rush**, **strike** | The subject is **retreating**, moving **away** from the given direction or location |

- When a retreat verb pairs with a direction keyword, **invert** that direction:

  - *mountain rush* → retreating **south**
  - *canyonside calm* → retreating **west by west-southwest**

> **Examples:**
>
> - “Mountain rush” → retreating **south**
> - “Blue grass calms to rocky boot” → Lt. Dan is **retreating away from West Town**
> - “Falling stones strike far from the mountain” → Gen. Lan’s army retreats **southward**

---

### 🧠 Notes & Edge Cases

1. **Identifier Requirement:** Verbs must attach to a **valid identifier** (e.g., *trailing leaf*, *blue bridge*).
2. **No-verb Adjectives:** Phrases like *floating grass* or *swinging grass* do **not** encode movement.
3. **Compound Directions:** Combine with the full **Directions** syntax:

   - “Flow into canyonside swamp” → move **east by southeast**
4. **Chaining:** Multiple movement verbs in one poem are read sequentially—good for multi-phase operations.
5. **Ambiguity Safeguard:** Use **padding** around movement lines if interception risk is high.

---

---

## 🛟 **Resources & Help – Aid Requests & Resource Status**

Zephyr Code lets operatives **call for assistance**, report **resource availability**, and signal **supply trends**—all hidden in poetic verse.

---

### 🔹 1. Help Requests

| **Help Marker**                                                                        | **Meaning: Send Help** |
| -------------------------------------------------------------------------------------- | ---------------------- |
| **cloud**, **smoke**, **flag**, **banner**, **river**, **valley**, **field**, **hill** | “Send help”            |

- **Location Anchor Required:**
  Must appear on the same line as a **location anchor** (`road`, `way`, `trail`).
  Without an anchor, it does **not** request help.

| **Anchor**       | **Interpretation**          |
| ---------------- | --------------------------- |
| road, way, trail | “Here” = where to send help |

- **Aid Type via Animal Class:**
  Immediately follow the help marker (and anchor) with an **animal** to specify the kind of aid:

  | **Animal Class** | **Aid Type**      |
  | ---------------- | ----------------- |
  | Furred           | Personnel support |
  | Feathered        | Food & supplies   |
  | Scaled           | Armaments         |
  | Aquatic          | Medical aid       |

> **Examples:**
>
> - *“down the valley road, a snake slithers by”*
>   – valley + road → send help here
>   – snake (scaled) → **send weapons**
> - *“the clouded mountain nests eagles flight”*
>   – cloud → send help
>   – mountain (north) → north from here
>   – eagle (feathered) → **send food**

---

### 🔸 2. Resource Availability & Status

#### a. **Resource Presence at Locations**

When an **animal** appears **with a place identifier** (e.g., `wooden lamp`, `smooth rock`), it signals that resource is available **there**:

| **Place ID, Animal**                  | **Meaning**                    |
| ------------------------------------- | ------------------------------ |
| *“On the metal lamp, the bird sings”* | Food & supplies at town center |
| *“At the smooth rock, fish gather”*   | Medical aid at the palace      |

#### b. **Resource Status for Individuals**

When an **animal** appears **with a person identifier** (e.g., `trailing leaf`, `blue bridge`), it signals that person’s resource status:

| **Person ID Animal**                    | **Meaning**                                |
| --------------------------------------- | ------------------------------------------ |
| *“Trailing lamp burns the harsh fish”*  | That person’s health has **improved**      |
| *“Blue bridge shrinks the dull lizard”* | That person’s armaments have **decreased** |

#### c. **Trend Modifiers**

Use **trend keywords** adjacent to the animal to indicate **increase** or **decrease**:

| **Trend**    | **Keywords**                    | **Effect**   |
| ------------ | ------------------------------- | ------------ |
| **Positive** | harsh, bask, laze, savor, dream | **Increase** |
| **Negative** | hush, cover, toil, shun, dread  | **Decrease** |

> **Examples:**
>
> - *“bayside lizard basks in the sun”*
>   – bayside → west from here
>   – lizard (scaled) → armaments
>   – basks → **increased**
>   → **Armaments west of here have increased**
> - *“blue bridge hushes the fish”*
>   – blue bridge → person under surveillance
>   – fish (aquatic) → medical aid
>   – hush → **decreased**
>   → **That person’s health has declined**

---

### 🧠 Notes

- **Help vs. Resource:** A **help marker** + anchor always **trumps** a resource reading.
- **Line Scope:** All keywords must appear on the **same line** (or within a period‐extended scope).
- **Padding & Nullifiers:** You can pad help/resource lines with neutral verse or nullifiers to conceal true intent.

---

---

## 🕵️ **Surveillance – Status Markers**

Zephyr Code lets operatives track the **observation status** of any identifier (person or place) through dedicated **surveillance verbs**. These markers report initial contact, loss, reacquisition, long-term absence, reassignment, errors, and corrections.

---

### 🔺 Status Verbs & Meanings

| **Verb(s)**               | **Meaning**                                                             |
| ------------------------- | ----------------------------------------------------------------------- |
| **Hues**                  | **First assignment** of this identifier (or reassignment after release) |
| **Whitens**, **Lightens** | Surveillance **reacquired**—target has been spotted again               |
| **Blackens**, **Darkens** | Surveillance **lost**—target is no longer observed                      |
| **Greys**, **Dulls**      | **6+ months** unobserved—ID is nearing expiration                       |
| **Shade**                 | **Release** the identifier—no longer linked to the original target      |
| **Tints**                 | **Possible error** or protocol breach—observation may be incorrect      |
| **Tones**                 | **Correction** or **confirmation** of previous report                   |

---

### 🧪 Examples

1. **Assignment & Reacquisition**

   - “The rolling hammer hues the flame” → *Rolling Hammer* is now the prince
   - “The rolling hammer lightens on the fire” → Prince has been spotted again

2. **Loss & Expiration Warning**

   - “The rolling hammer darkens in frost” → Surveillance on prince is lost
   - “The rolling hammer dulls with time” → No sighting for 6 months; ID will expire soon

3. **Release & Reuse**

   - “The rolling hammer shades the waves” → *Rolling Hammer* is released from the prince
   - “The red flower hues in clouds” → *Red Flower* becomes a new ID

4. **Error & Correction**

   - “The rolling hammer tints in stardust swirls” → Observation uncertain or protocol error
   - “In rolling hammer tones falling stone moss” → Correction: it was *Falling Stone* (General Lan)

---

### 🧠 Notes & Workflow

1. **Lifecycle Flow:**

   1. **Hues** → first assignment
   2. **Whitens/Lightens** → positive sighting
   3. **Blackens/Darkens** → lost sighting
   4. **Greys/Dulls** → 6+ months lost
   5. **Shade** → release ID
   6. **Tints** → flag possible error
   7. **Tones** → confirm or correct

2. **Protocol Enforcement:**

   - Use **Tints** whenever unsure or protocol may have been violated.
   - Follow with **Tones** to affirm or correct that doubt.

3. **Verb Position:**

   - These verbs function as **action markers**—they should be the **main verb** of a line.
   - Do **not** use them inside literal blocks unless nullified.

---

---

## 🛑 **Literal Overrides – Bypass & Block Modes**

Zephyr Code normally encodes every line symbolically, but there are clear mechanisms to **suspend** encoding and read content **literally** when clarity or alternate encryption is required.

---

### 🔹 1. Single-Line Literal (“of”)

- **Trigger:** A line beginning with **`of`** (alone, in lowercase)
- **Effect:** The **entire line** is read **literally**—no keywords, triggers, or functions apply.

> **Examples:**
>
> ```text
> of north of the valley  
> ```
>
> → Exactly “north of the valley.”
>
> ```text
> of thirteen dead  
> ```
>
> → Exactly “thirteen dead.”

**Notes:**

- Only counts if **`of`** is the **first word**.
- Does **not** apply to the **title**.
- Any other occurrence of “of” in a line is processed normally.

---

### 🔸 2. Multi-Line Literal Blocks (“of this” … “that”)

#### a. **Start Block**

- **Triggers:**

  - **`of this`** (routine/priority flash not recommended)
  - **`flash of this`**, **`immediate of this`**, **`flash of that`** (urgency applied literally)
- Must appear as the **very first words** of a line.
- **Everything** after that line—across **multiple lines**—is read **literally** until the block is closed.

#### b. **End Block**

- A line whose **last word** is exactly **`that`**, with **no trailing text**, terminates the literal block.
- **Only** a standalone final-word `that` counts. Mid-line `that` is part of the literal text.

> **Example:**
>
> ```text
> flash of this
> 12 dead, 30 injured
> Immediate evacuation requested
> Enemy sighted at southern pass that
> Mountain road flows with ash
> ```
>
> – Lines 1–3 are literal.
> – Line 4 ends in `that` → block closes.
> – Line 5 resumes normal encoding.

**Notes:**

- If **no** terminating `that` is ever found, the **rest of the message** remains literal.
- **Flash** or **Immediate** urgency blocks unencoded content are acceptable; **Routine** or **Priority** blocks are discouraged or flagged for review.
- Within literal blocks, **other encodings** (e.g., acrostics, steganography) may still be used.

---

### 🔹 3. Nullifiers Inside Literal Blocks

- **Nullifier keywords** (`ain’t`, `yonder`, `reckon`, `holler`, `y’all`) placed **anywhere** on a **literal-block** line **reactivate** Zephyr encoding **for that line** only.
- This allows a **single coded line** to be planted inside an otherwise literal section (often used for misinformation or hidden signals).

> **Example:**
>
> ```text
> of this
> All engines ready
> The red leaf ain’t in the bay
> The blue bridge holler in canyon way
> that
> ```
>
> – Line 2: literal.
> – Line 3: nullifier on literal-start line → ignore (literal).
> – Line 4: `holler` nullifies literal mode → standard encoding applies (blue bridge → east).

---

### 🧠 Key Takeaways

1. **`of`** = single-line literal override.
2. **`of this` … `that`** = multi-line literal block.
3. **Nullifiers** within a literal block flip that line back to code.
4. **Use judiciously**: literal overrides trade security for clarity or alternative encoding.

---

---

## 🚫 **Padding & Nullifiers**

In Zephyr Code, **padding lines** and **nullifier keywords** are essential for **misdirection** and **security**, making encoded lines harder to detect and providing a way to **cancel** encoding when needed.

---

### 🔹 1. Padding Lines

- **Definition:** Lines that contain **no trigger words**, **no special keywords**, and thus encode **nothing**.
- **Purpose:**

  - **Break up** patterns of encoded content
  - **Blend** intelligence into ordinary verse
  - **Delay** or **confuse** interceptors
- **Best Practice:**

  - Include **at least one** padding line **every 2–3 lines** of encoded content
  - Vary placement: opening, middle, or closing of stanzas
  - Write them as **natural poetic imagery**

> *Example Padding Line:*
> “The grass grows green upon the summit”

---

### 🔸 2. Nullifier Keywords

| **Keyword** | **Effect**                        |
| ----------- | --------------------------------- |
| ain’t       | Cancels all encoding on that line |
| yonder      | Cancels all encoding on that line |
| reckon      | Cancels all encoding on that line |
| holler      | Cancels all encoding on that line |
| y’all       | Cancels all encoding on that line |

- **Mechanism:** If **any** nullifier appears **anywhere** on the line, **ignore** all other code triggers on that line.
- **Strategic Uses:**

  - **Misinformation:** Plant decoy lines to mislead interceptors
  - **Shielding:** Make real encoded lines look similar so they’re skipped
  - **Conditional activation:** Only use when interception risk is high

> *Example:*
>
> - “The running mouse ain’t in the swamp” → **No encoding** (nullified)
> - Interceptor might skip: “The trailing leaf ain’t in the bay” (also nullified) → **Misses** real “trailing leaf” west message

---

### 🔹 3. Nullifiers Inside Literal Blocks

- Within an **`of this … that`** block, a nullifier on a line **reactivates** standard Zephyr encoding **for that line only**.
- **Use Case:** Embed a hidden code line amid literal text (e.g., a fallback signal or a trap).

> *Example:*
>
> ```text
> of this
> All is calm and still
> The blue bridge holler in canyon way
> That
> ```
>
> – Line 2: literal (no nullifier)
> – Line 3: `holler` cancels literal-block → standard encoding applies (blue bridge → east)

---

### 🧠 Key Takeaways

- **Padding** hides patterns; use it liberally.
- **Nullifiers** cancel encoding on demand; use sparingly for decoys or high-risk scenarios.
- **Inside literal blocks**, nullifiers flip that line back to code, enabling nuanced misinformation or hidden instructions.

## ⚔️ **Outcomes – Casualties & Recovery**

Zephyr operatives use **poetic modifiers** to report **losses**, **destruction**, and **new gains**—all concealed within existing numeric triggers.

---

### 🔹 1. Negative Outcomes (Casualties & Destruction)

- **Modifiers:**

  - **glint**, **lit**, **light**, **spark**, **shine**
- **Paired with:** **’till’** (or **’till**\`)
- **Effect:** Indicates **death** (for people/groups) or **destruction** (for places).
- **Numeric encoding:**

  - If used with a **numeric trigger** (e.g. `from`, `and`, etc.), the line encodes the **number of dead** or **units destroyed** via the trigger’s function.
  - If used alone with a **location** (no trigger), it simply reports the place’s destruction.

> **Examples:**
>
> - *“Glint ’till dawn from cold drops”*
>   – Trigger: `from` → Cat(cold=1, drops=1) = **11** → **11 dead**
> - *“Blue grass lit ’till the swamp way”*
>   – “lit ’till” + “swamp way” → Lt. Dan is **dead**, last seen **south**.
> - *“Rocky boot shine ’till dawn”*
>   – No trigger → West Town is **destroyed**.

---

### 🔸 2. Positive Outcomes (New & Rebuilt)

- **Modifiers:**

  - **glint**, **lit**, **light**, **spark**, **shine**
- **Paired with:** **’yet’**
- **Effect:** Indicates something **new**, **found**, **created**, or **rebuilt**.
- **Numeric encoding:**

  - With a **numeric trigger**, yields the **quantity** of new individuals or items.
  - Standalone at a **place**, reports the place has been **rebuilt** or **restocked**.

> **Examples:**
>
> - *“from rainbow so / spark yet tonight”*
>   – Line 1: `from rainbow so` → Cat(2,0) = **20**
>   – Line 2: “spark yet” → **20 new individuals here**
> - *“Rocky boot shine yet thru”*
>   – No trigger → **West Town has been rebuilt**.

---

### 🧠 Notes & Edge Cases

- **Line breaks matter:** For two‐line examples, use `/` or a period to scope triggers correctly.
- **Modifiers before triggers** retain numeric functions; **after triggers**, they count by syllable/override like any other operand.
- **Casualty vs. Destruction:** When paired with a **person/group identifier**, “’till” always signals death; when paired with a **place identifier**, it signals destruction.
- **Recovery vs. Arrival:** Similarly, “’yet” with a place = rebuilt; with a person/group = new arrivals or reinforcements.

This section completes the reporting of **negative and positive outcomes** in Zephyr Code. Let me know if you’d like sample verses or further elaboration!
