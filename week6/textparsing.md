# CISC 179 - Week 6
## Text Parsing

This assignment covers Python text parsing concepts 

## code and answers 
```python
import re
# Story
story = """
Once on a time and twice on a time, and all times together as ever I heard tell of, there was a tiny lassie who would weep all day to have the stars in the sky to play with; she wouldn’t have this, and she wouldn’t have that, but it was always the stars she would have. So one fine day off she went to find them. And she walked and she walked and she walked, till by-and-by she came to a mill-dam.

“Goode’en to ye,” says she, “I’m seeking the stars in the sky to play with. Have you seen any?”

“Oh, yes, my bonnie lassie,” said the mill-dam. “They shine in my own face o’ nights till I can’t sleep for them. Jump in and perhaps you’ll find one.”

So she jumped in, and swam about and swam about and swam about, but ne’er a one could she see. So she went on till she came to a brooklet.

“Goode’en to ye, Brooklet, Brooklet,” says she; “I’m seeking the stars in the sky to play with. Have you seen any?”

“Yes, indeed, my bonny lassie,” said the Brooklet. “They glint on my banks at night. Paddle about, and maybe you’ll find one.”

So she paddled and she paddled and she paddled, but ne’er a one did she find. So on she went till she came to the Good Folk.

“Goode’en to ye, Good Folk,” says she; “I’m looking for the stars in the sky to play with. Have ye seen e’er a one?”

“Why, yes, my bonny lassie,” said the Good Folk. “They shine on the grass here o’ night. Dance with us, and maybe you’ll find one.”

And she danced and she danced and she danced, but ne’er a one did she see. So down she sate; I suppose she wept.

“Oh dearie me, oh dearie me,” says she, “I’ve swam and I’ve paddled and I’ve danced, and if ye’ll not help me I shall never find the stars in the sky to play with.”

But the Good Folk whispered together, and one of them came up to her and took her by the hand and said, “If you won’t go home to your mother, go forward, go forward; mind you take the right road. Ask Four Feet to carry you to No Feet at all, and tell No Feet at all to carry you to the stairs without steps, and if you can climb that—”

“Oh, shall I be among the stars in the sky then?” cried the lassie.

“If you’ll not be, then you’ll be elsewhere,” said the Good Folk, and set to dancing again.

So on she went again with a light heart, and by-and-by she came to a saddled horse, tied to a tree.

“Goode’en to ye, Beast,” said she; “I’m seeking the stars in the sky to play with. Will you give me a lift, for all my bones are an-aching.”

“Nay,” said the horse, “I know nought of the stars in the sky, and I’m here to do the bidding of the Good Folk, and not my own will.”

“Well,” said she, “it’s from the Good Folk I come, and they bade me tell Four Feet to carry me to No Feet at all.”

“That’s another story,” said he; “jump up and ride with me.”

So they rode and they rode and they rode, till they got out of the forest and found themselves at the edge of the sea. And on the water in front of them was a wide glistening path running straight out towards a beautiful thing that rose out of the water and went up into the sky, and was all the colours in the world, blue and red and green, and wonderful to look at.

“Now get you down,” said the horse; “I’ve brought ye to the end of the land, and that’s as much as Four Feet can do. I must away home to my own folk.”

“But,” said the lassie, “where’s No Feet at all, and where’s the stair without steps?”

“I know not,” said the horse, “it’s none of my business neither. So goode’en to ye, my bonny lassie;” and off he went.

So the lassie stood still and looked at the water, till a strange kind of fish came swimming up to her feet.

“Goode’en to ye, big Fish,” says she, “I’m looking for the stars in the sky, and for the stairs that climb up to them. Will ye show me the way?”

“Nay,” said the Fish, “I can’t unless you bring me word from the Good Folk.”

“Yes, indeed,” said she. “They said Four Feet would bring me to No Feet at all, and No Feet at all would carry me to the stairs without steps.”

“Get on my back and hold fast.”
“Ah, well,” said the Fish; “that’s all right then. Get on my back and hold fast.”

And off he went—Kerplash!—into the water, along the silver path, towards the bright arch. And the nearer they came the brighter the sheen of it, till she had to shade her eyes from the light of it.

And as they came to the foot of it, she saw it was a broad bright road, sloping up and away into the sky, and at the far, far end of it she could see wee shining things dancing about.

“Now,” said the Fish, “here you are, and yon’s the stair; climb up, if you can, but hold on fast. I’ll warrant you find the stair easier at home than by such a way; ‘t was ne'er meant for lassies’ feet to travel;” and off he splashed through the water.

So she clomb and she clomb and she clomb, but ne’er a step higher did she get: the light was before her and around her, and the water behind her, and the more she struggled the more she was forced down into the dark and the cold, and the more she clomb the deeper she fell.

But she clomb and she clomb, till she got dizzy in the light and shivered with the cold, and dazed with the fear; but still she clomb, till at last, quite dazed and silly-like, she let clean go, and sank down—down—down.

And bang she came on to the hard boards, and found herself sitting, weeping and wailing, by the bedside at home all alone.

-----
The story is written by 
Roger Federer &
Serina Williams
You can connect with the author at [rfederer@tennis.com] and [swilliams@tennis.com]
Admin contact number: 1-888-111-2222
"""
```
#  1: Word and character count using lists
## Results 
Total Character Count: 5512
Total Word Count: 1091

Histogram (Top 10 most frequent words):

the        : ************************************************************************************* (85)

and        : *********************************************************************** (71)

she        : *************************************************** (51)

to         : **************************************** (40)

a          : ******************* (19)

said       : ***************** (17)

of         : *************** (15)

in         : *************** (15)

at         : *************** (15)

you        : ************** (14)

```python
total_characters = len(story)
words_list = story.split()
total_words = len(words_list)

print("--- Question 1  Answers ---")
print("Total Character Count:", total_characters)
print("Total Word Count:", total_words)

words_seen = []
word_counts = []

for word in words_list:
    clean_word = word.strip(".,;:!?“”'\"[]()-—").lower()
    if clean_word != "":
        if clean_word in words_seen:
            index = words_seen.index(clean_word)
            word_counts[index] += 1
        else:
            words_seen.append(clean_word)
            word_counts.append(1)

word_pairs = []
for i in range(len(words_seen)):
    word_pairs.append((word_counts[i], words_seen[i]))

word_pairs.sort(reverse=True)

print("\nHistogram (Top 10 most frequent words):")
for count, word in word_pairs[:10]:
    stars = "*" * count
    print(f"{word:10s} : {stars} ({count})")

```
# 2: Word frequency using a dictionary
## Results
Total Unique Words: 314

Sample Frequencies:

the: 85

and: 71

she: 51

```python
word_dict = {}

for word in words_list:
    clean_word = word.strip(".,;:!?“”'\"[]()-—").lower()
    if clean_word != "":
        if clean_word in word_dict:
            word_dict[clean_word] += 1
        else:
            word_dict[clean_word] = 1

print("\n--- Question 2 answers ---")
print("Total Unique Words:", len(word_dict))
print("Sample Frequencies:")
print("the:", word_dict.get("the"))
print("and:", word_dict.get("and"))
print("she:", word_dict.get("she"))
```
# 3: Extract phone numbers and emails using simple regular expressions
## Results
Extracted Phone Numbers: ['1-888-111-2222']
Extracted Email Addresses: ['rfederer@tennis.com', 'swilliams@tennis.com']
```python
extracted_phones = []
extracted_emails = []

for word in words_list:
    clean_word = word.strip("[](),;:\"'“”")
    if clean_word.endswith("."):
        clean_word = clean_word[:-1]

    if re.search("@", clean_word) and re.search(r"\.", clean_word):
        if clean_word not in extracted_emails:
            extracted_emails.append(clean_word)

    if re.search("-", clean_word) and clean_word[0].isdigit():
        if clean_word not in extracted_phones:
            extracted_phones.append(clean_word)

print("\n--- Question 3 answers ---")
print("Extracted Phone Numbers:", extracted_phones)
print("Extracted Email Addresses:", extracted_emails)
```
# 4: Process email usernames
## Results
Usernames: ['rfederer', 'swilliams']
Hotmail Emails: ['rfederer@hotmail.com', 'swilliams@hotmail.com']

Process finished with exit code 0
```python
usernames = []
hotmail_list = []

for email in extracted_emails:
    parts = email.split("@")
    user = parts[0]

    usernames.append(user)
    hotmail_list.append(f"{user}@hotmail.com")

print("\n--- Question 4 results ---")
print("Usernames:", usernames)
print("Hotmail Emails:", hotmail_list)

