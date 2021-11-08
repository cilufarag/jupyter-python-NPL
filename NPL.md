```python
import spacy
```


```python
nlp = spacy.load('en_core_web_sm')
```


```python
with open ('data/wiki_us.txt', 'r') as f:
    text = f.read()
```


```python
print(text)
```

    The United States of America (U.S.A. or USA), commonly known as the United States (U.S. or US) or America, is a country primarily located in North America. It consists of 50 states, a federal district, five major unincorporated territories, 326 Indian reservations, and some minor possessions.[j] At 3.8 million square miles (9.8 million square kilometers), it is the world's third- or fourth-largest country by total area.[d] The United States shares significant land borders with Canada to the north and Mexico to the south, as well as limited maritime borders with the Bahamas, Cuba, and Russia.[22] With a population of more than 331 million people, it is the third most populous country in the world. The national capital is Washington, D.C., and the most populous city is New York.
    
    Paleo-Indians migrated from Siberia to the North American mainland at least 12,000 years ago, and European colonization began in the 16th century. The United States emerged from the thirteen British colonies established along the East Coast. Disputes over taxation and political representation with Great Britain led to the American Revolutionary War (1775–1783), which established independence. In the late 18th century, the U.S. began expanding across North America, gradually obtaining new territories, sometimes through war, frequently displacing Native Americans, and admitting new states; by 1848, the United States spanned the continent. Slavery was legal in the southern United States until the second half of the 19th century when the American Civil War led to its abolition. The Spanish–American War and World War I established the U.S. as a world power, a status confirmed by the outcome of World War II.
    
    During the Cold War, the United States fought the Korean War and the Vietnam War but avoided direct military conflict with the Soviet Union. The two superpowers competed in the Space Race, culminating in the 1969 spaceflight that first landed humans on the Moon. The Soviet Union's dissolution in 1991 ended the Cold War, leaving the United States as the world's sole superpower.
    
    The United States is a federal republic and a representative democracy with three separate branches of government, including a bicameral legislature. It is a founding member of the United Nations, World Bank, International Monetary Fund, Organization of American States, NATO, and other international organizations. It is a permanent member of the United Nations Security Council. Considered a melting pot of cultures and ethnicities, its population has been profoundly shaped by centuries of immigration. The country ranks high in international measures of economic freedom, quality of life, education, and human rights, and has low levels of perceived corruption. However, the country has received criticism concerning inequality related to race, wealth and income, the use of capital punishment, high incarceration rates, and lack of universal health care.
    
    The United States is a highly developed country, accounts for approximately a quarter of global GDP, and is the world's largest economy. By value, the United States is the world's largest importer and the second-largest exporter of goods. Although its population is only 4.2% of the world's total, it holds 29.4% of the total wealth in the world, the largest share held by any country. Making up more than a third of global military spending, it is the foremost military power in the world; and it is a leading political, cultural, and scientific force internationally.[23]



```python
doc = nlp(text)
```


```python
print(doc)
```

    The United States of America (U.S.A. or USA), commonly known as the United States (U.S. or US) or America, is a country primarily located in North America. It consists of 50 states, a federal district, five major unincorporated territories, 326 Indian reservations, and some minor possessions.[j] At 3.8 million square miles (9.8 million square kilometers), it is the world's third- or fourth-largest country by total area.[d] The United States shares significant land borders with Canada to the north and Mexico to the south, as well as limited maritime borders with the Bahamas, Cuba, and Russia.[22] With a population of more than 331 million people, it is the third most populous country in the world. The national capital is Washington, D.C., and the most populous city is New York.
    
    Paleo-Indians migrated from Siberia to the North American mainland at least 12,000 years ago, and European colonization began in the 16th century. The United States emerged from the thirteen British colonies established along the East Coast. Disputes over taxation and political representation with Great Britain led to the American Revolutionary War (1775–1783), which established independence. In the late 18th century, the U.S. began expanding across North America, gradually obtaining new territories, sometimes through war, frequently displacing Native Americans, and admitting new states; by 1848, the United States spanned the continent. Slavery was legal in the southern United States until the second half of the 19th century when the American Civil War led to its abolition. The Spanish–American War and World War I established the U.S. as a world power, a status confirmed by the outcome of World War II.
    
    During the Cold War, the United States fought the Korean War and the Vietnam War but avoided direct military conflict with the Soviet Union. The two superpowers competed in the Space Race, culminating in the 1969 spaceflight that first landed humans on the Moon. The Soviet Union's dissolution in 1991 ended the Cold War, leaving the United States as the world's sole superpower.
    
    The United States is a federal republic and a representative democracy with three separate branches of government, including a bicameral legislature. It is a founding member of the United Nations, World Bank, International Monetary Fund, Organization of American States, NATO, and other international organizations. It is a permanent member of the United Nations Security Council. Considered a melting pot of cultures and ethnicities, its population has been profoundly shaped by centuries of immigration. The country ranks high in international measures of economic freedom, quality of life, education, and human rights, and has low levels of perceived corruption. However, the country has received criticism concerning inequality related to race, wealth and income, the use of capital punishment, high incarceration rates, and lack of universal health care.
    
    The United States is a highly developed country, accounts for approximately a quarter of global GDP, and is the world's largest economy. By value, the United States is the world's largest importer and the second-largest exporter of goods. Although its population is only 4.2% of the world's total, it holds 29.4% of the total wealth in the world, the largest share held by any country. Making up more than a third of global military spending, it is the foremost military power in the world; and it is a leading political, cultural, and scientific force internationally.[23]



```python
print(len(text))
print(len(doc))
```

    3521
    654



```python
for token in text[0:10]:
    print(token)
```

    T
    h
    e
     
    U
    n
    i
    t
    e
    d



```python
for token in doc[0:10]:
    print(token)
```

    The
    United
    States
    of
    America
    (
    U.S.A.
    or
    USA
    )



```python
for token in text.split()[:10]:
    print(token)
```

    The
    United
    States
    of
    America
    (U.S.A.
    or
    USA),
    commonly
    known



```python
for token in text.split(' ')[:10]:
    print(token)
```

    The
    United
    States
    of
    America
    (U.S.A.
    or
    USA),
    commonly
    known



```python
for sent in doc.sents:
    print(sent)
```

    The United States of America (U.S.A. or USA), commonly known as the United States (U.S. or US) or America, is a country primarily located in North America.
    It consists of 50 states, a federal district, five major unincorporated territories, 326 Indian reservations, and some minor possessions.[j]
    At 3.8 million square miles (9.8 million square kilometers), it is the world's third- or fourth-largest country by total area.[d] The United States shares significant land borders with Canada to the north and Mexico to the south, as well as limited maritime borders with the Bahamas, Cuba, and Russia.[22] With a population of more than 331 million people, it is the third most populous country in the world.
    The national capital is Washington, D.C., and the most populous city is New York.
    
    
    Paleo-Indians migrated from Siberia to the North American mainland at least 12,000 years ago, and European colonization began in the 16th century.
    The United States emerged from the thirteen British colonies established along the East Coast.
    Disputes over taxation and political representation with Great Britain led to the American Revolutionary War (1775–1783), which established independence.
    In the late 18th century, the U.S. began expanding across North America, gradually obtaining new territories, sometimes through war, frequently displacing Native Americans, and admitting new states; by 1848, the United States spanned the continent.
    Slavery was legal in the southern United States until the second half of the 19th century when the American Civil War led to its abolition.
    The Spanish–American War and World War I established the U.S. as a world power, a status confirmed by the outcome of World War II.
    
    
    
    During the Cold War, the United States fought the Korean War and the Vietnam War but avoided direct military conflict with the Soviet Union.
    The two superpowers competed in the Space Race, culminating in the 1969 spaceflight that first landed humans on the Moon.
    The Soviet Union's dissolution in 1991 ended the Cold War, leaving the United States as the world's sole superpower.
    
    
    
    The United States is a federal republic and a representative democracy with three separate branches of government, including a bicameral legislature.
    It is a founding member of the United Nations, World Bank, International Monetary Fund, Organization of American States, NATO, and other international organizations.
    It is a permanent member of the United Nations Security Council.
    Considered a melting pot of cultures and ethnicities, its population has been profoundly shaped by centuries of immigration.
    The country ranks high in international measures of economic freedom, quality of life, education, and human rights, and has low levels of perceived corruption.
    However, the country has received criticism concerning inequality related to race, wealth and income, the use of capital punishment, high incarceration rates, and lack of universal health care.
    
    
    
    The United States is a highly developed country, accounts for approximately a quarter of global GDP, and is the world's largest economy.
    By value, the United States is the world's largest importer and the second-largest exporter of goods.
    Although its population is only 4.2% of the world's total, it holds 29.4% of the total wealth in the world, the largest share held by any country.
    Making up more than a third of global military spending, it is the foremost military power in the world; and it is a leading political, cultural, and scientific force internationally.[23]



```python
sentence1 = doc.sents[0]
print(sentence1)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    /tmp/ipykernel_16522/2926092115.py in <module>
    ----> 1 sentence1 = doc.sents[0]
          2 print(sentence1)


    TypeError: 'generator' object is not subscriptable



```python
sentence1 = list(doc.sents)[0]
print(sentence1)
```

    The United States of America (U.S.A. or USA), commonly known as the United States (U.S. or US) or America, is a country primarily located in North America.



```python
for token in doc[:10]:
    print(token)
```

    The
    United
    States
    of
    America
    (
    U.S.A.
    or
    USA
    )



```python
token2 = sentence1[2]
print(token2)
```

    States



```python
token2.text
```




    'States'




```python
token2.left_edge
```




    The




```python
token2.right_edge
```




    America




```python
token2.ent_type
```




    384




```python
token2.ent_type_
```




    'GPE'




```python
token2.ent_iob_
```




    'I'




```python
token2.lemma_
```




    'States'




```python
sentence1[12].lemma_
```




    'know'




```python
print(sentence1[12])
```

    known



```python
token2.morph
```




    NounType=Prop|Number=Sing




```python
sentence1[12].morph
```




    Aspect=Perf|Tense=Past|VerbForm=Part




```python
token2.pos_
```




    'PROPN'




```python
token2.dep_
```




    'nsubj'




```python
token2.lang_
```




    'en'




```python
text = "Mike enjoys playing football."
doc2 = nlp(text)
print(doc2)
```

    Mike enjoys playing football.



```python
for token in doc2:
    print(token.text, token.pos_, token.dep_)
```

    Mike PROPN nsubj
    enjoys VERB ROOT
    playing VERB xcomp
    football NOUN dobj
    . PUNCT punct



```python
from spacy import displacy
displacy.render(doc2, style='dep')
```


<span class="tex2jax_ignore"><svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xml:lang="en" id="24b0e083cd4149c8b450ab2a01a515fc-0" class="displacy" width="750" height="224.5" direction="ltr" style="max-width: none; height: 224.5px; color: #000000; background: #ffffff; font-family: Arial; direction: ltr">
<text class="displacy-token" fill="currentColor" text-anchor="middle" y="134.5">
    <tspan class="displacy-word" fill="currentColor" x="50">Mike</tspan>
    <tspan class="displacy-tag" dy="2em" fill="currentColor" x="50">PROPN</tspan>
</text>

<text class="displacy-token" fill="currentColor" text-anchor="middle" y="134.5">
    <tspan class="displacy-word" fill="currentColor" x="225">enjoys</tspan>
    <tspan class="displacy-tag" dy="2em" fill="currentColor" x="225">VERB</tspan>
</text>

<text class="displacy-token" fill="currentColor" text-anchor="middle" y="134.5">
    <tspan class="displacy-word" fill="currentColor" x="400">playing</tspan>
    <tspan class="displacy-tag" dy="2em" fill="currentColor" x="400">VERB</tspan>
</text>

<text class="displacy-token" fill="currentColor" text-anchor="middle" y="134.5">
    <tspan class="displacy-word" fill="currentColor" x="575">football.</tspan>
    <tspan class="displacy-tag" dy="2em" fill="currentColor" x="575">NOUN</tspan>
</text>

<g class="displacy-arrow">
    <path class="displacy-arc" id="arrow-24b0e083cd4149c8b450ab2a01a515fc-0-0" stroke-width="2px" d="M70,89.5 C70,2.0 225.0,2.0 225.0,89.5" fill="none" stroke="currentColor"/>
    <text dy="1.25em" style="font-size: 0.8em; letter-spacing: 1px">
        <textPath xlink:href="#arrow-24b0e083cd4149c8b450ab2a01a515fc-0-0" class="displacy-label" startOffset="50%" side="left" fill="currentColor" text-anchor="middle">nsubj</textPath>
    </text>
    <path class="displacy-arrowhead" d="M70,91.5 L62,79.5 78,79.5" fill="currentColor"/>
</g>

<g class="displacy-arrow">
    <path class="displacy-arc" id="arrow-24b0e083cd4149c8b450ab2a01a515fc-0-1" stroke-width="2px" d="M245,89.5 C245,2.0 400.0,2.0 400.0,89.5" fill="none" stroke="currentColor"/>
    <text dy="1.25em" style="font-size: 0.8em; letter-spacing: 1px">
        <textPath xlink:href="#arrow-24b0e083cd4149c8b450ab2a01a515fc-0-1" class="displacy-label" startOffset="50%" side="left" fill="currentColor" text-anchor="middle">xcomp</textPath>
    </text>
    <path class="displacy-arrowhead" d="M400.0,91.5 L408.0,79.5 392.0,79.5" fill="currentColor"/>
</g>

<g class="displacy-arrow">
    <path class="displacy-arc" id="arrow-24b0e083cd4149c8b450ab2a01a515fc-0-2" stroke-width="2px" d="M420,89.5 C420,2.0 575.0,2.0 575.0,89.5" fill="none" stroke="currentColor"/>
    <text dy="1.25em" style="font-size: 0.8em; letter-spacing: 1px">
        <textPath xlink:href="#arrow-24b0e083cd4149c8b450ab2a01a515fc-0-2" class="displacy-label" startOffset="50%" side="left" fill="currentColor" text-anchor="middle">dobj</textPath>
    </text>
    <path class="displacy-arrowhead" d="M575.0,91.5 L583.0,79.5 567.0,79.5" fill="currentColor"/>
</g>
</svg></span>



```python
for ent in doc.ents:
    print(ent.text, ent.label_)
```

    The United States of America GPE
    U.S.A. GPE
    USA GPE
    the United States GPE
    U.S. GPE
    US GPE
    America GPE
    North America LOC
    50 CARDINAL
    five CARDINAL
    326 CARDINAL
    Indian NORP
    3.8 million square miles QUANTITY
    9.8 million square kilometers QUANTITY
    fourth ORDINAL
    The United States GPE
    Canada GPE
    Mexico GPE
    Bahamas GPE
    Cuba GPE
    more than 331 million CARDINAL
    third ORDINAL
    Washington GPE
    D.C. GPE
    New York GPE
    Paleo-Indians NORP
    Siberia LOC
    North American NORP
    at least 12,000 years ago DATE
    European NORP
    the 16th century DATE
    The United States GPE
    thirteen CARDINAL
    British NORP
    the East Coast LOC
    Great Britain GPE
    the American Revolutionary War ORG
    1775–1783 DATE
    the late 18th century DATE
    U.S. GPE
    North America LOC
    Native Americans NORP
    1848 DATE
    the United States GPE
    United States GPE
    the second half of the 19th century DATE
    the American Civil War EVENT
    Spanish NORP
    American War and EVENT
    World War EVENT
    U.S. GPE
    World War II EVENT
    the Cold War EVENT
    the United States GPE
    the Korean War EVENT
    the Vietnam War EVENT
    the Soviet Union GPE
    two CARDINAL
    the Space Race FAC
    1969 DATE
    first ORDINAL
    The Soviet Union's GPE
    1991 DATE
    the Cold War EVENT
    the United States GPE
    The United States GPE
    three CARDINAL
    the United Nations ORG
    World Bank ORG
    International Monetary Fund ORG
    Organization of American States ORG
    NATO ORG
    the United Nations Security Council ORG
    centuries DATE
    The United States GPE
    approximately a quarter DATE
    the United States GPE
    second ORDINAL
    only 4.2% PERCENT
    29.4% PERCENT
    more than a third CARDINAL



```python
displacy.render(doc, style='ent')
```


<span class="tex2jax_ignore"><div class="entities" style="line-height: 2.5; direction: ltr">
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The United States of America
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 (
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    U.S.A.
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 or 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    USA
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
), commonly known as 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 (
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    U.S.
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 or 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    US
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
) or 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    America
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
, is a country primarily located in 
<mark class="entity" style="background: #ff9561; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    North America
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">LOC</span>
</mark>
. It consists of 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    50
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 states, a federal district, 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    five
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 major unincorporated territories, 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    326
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>

<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Indian
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
 reservations, and some minor possessions.[j] At 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    3.8 million square miles
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">QUANTITY</span>
</mark>
 (
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    9.8 million square kilometers
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">QUANTITY</span>
</mark>
), it is the world's third- or 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    fourth
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORDINAL</span>
</mark>
-largest country by total area.[d] 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 shares significant land borders with 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Canada
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 to the north and 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Mexico
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 to the south, as well as limited maritime borders with the 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Bahamas
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
, 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Cuba
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
, and Russia.[22] With a population of 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    more than 331 million
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 people, it is the 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    third
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORDINAL</span>
</mark>
 most populous country in the world. The national capital is 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Washington
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
, 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    D.C.
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
, and the most populous city is 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    New York
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
.</br></br>
<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Paleo-Indians
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
 migrated from 
<mark class="entity" style="background: #ff9561; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Siberia
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">LOC</span>
</mark>
 to the 
<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    North American
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
 mainland 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    at least 12,000 years ago
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
, and 
<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    European
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
 colonization began in 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the 16th century
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
. 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 emerged from the 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    thirteen
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>

<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    British
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
 colonies established along 
<mark class="entity" style="background: #ff9561; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the East Coast
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">LOC</span>
</mark>
. Disputes over taxation and political representation with 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Great Britain
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 led to 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the American Revolutionary War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
 (
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    1775–1783
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
), which established independence. In 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the late 18th century
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
, the 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    U.S.
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 began expanding across 
<mark class="entity" style="background: #ff9561; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    North America
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">LOC</span>
</mark>
, gradually obtaining new territories, sometimes through war, frequently displacing 
<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Native Americans
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
, and admitting new states; by 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    1848
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
, 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 spanned the continent. Slavery was legal in the southern 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 until 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the second half of the 19th century
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
 when 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the American Civil War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
 led to its abolition. The 
<mark class="entity" style="background: #c887fb; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Spanish
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">NORP</span>
</mark>
–
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    American War and
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>

<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    World War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
 I established the 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    U.S.
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 as a world power, a status confirmed by the outcome of 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    World War II
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
.</br></br>During 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Cold War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
, 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 fought 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Korean War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
 and 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Vietnam War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
 but avoided direct military conflict with 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Soviet Union
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
. The 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    two
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 superpowers competed in 
<mark class="entity" style="background: #ddd; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Space Race
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">FAC</span>
</mark>
, culminating in the 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    1969
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
 spaceflight that 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    first
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORDINAL</span>
</mark>
 landed humans on the Moon. 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The Soviet Union's
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 dissolution in 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    1991
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
 ended 
<mark class="entity" style="background: #ffeb80; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the Cold War
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">EVENT</span>
</mark>
, leaving 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 as the world's sole superpower.</br></br>
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 is a federal republic and a representative democracy with 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    three
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 separate branches of government, including a bicameral legislature. It is a founding member of 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United Nations
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
, 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    World Bank
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
, 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    International Monetary Fund
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
, 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    Organization of American States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
, 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    NATO
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
, and other international organizations. It is a permanent member of 
<mark class="entity" style="background: #7aecec; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United Nations Security Council
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORG</span>
</mark>
. Considered a melting pot of cultures and ethnicities, its population has been profoundly shaped by 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    centuries
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
 of immigration. The country ranks high in international measures of economic freedom, quality of life, education, and human rights, and has low levels of perceived corruption. However, the country has received criticism concerning inequality related to race, wealth and income, the use of capital punishment, high incarceration rates, and lack of universal health care.</br></br>
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    The United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 is a highly developed country, accounts for 
<mark class="entity" style="background: #bfe1d9; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    approximately a quarter
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">DATE</span>
</mark>
 of global GDP, and is the world's largest economy. By value, 
<mark class="entity" style="background: #feca74; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    the United States
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">GPE</span>
</mark>
 is the world's largest importer and the 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    second
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">ORDINAL</span>
</mark>
-largest exporter of goods. Although its population is 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    only 4.2%
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">PERCENT</span>
</mark>
 of the world's total, it holds 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    29.4%
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">PERCENT</span>
</mark>
 of the total wealth in the world, the largest share held by any country. Making up 
<mark class="entity" style="background: #e4e7d2; padding: 0.45em 0.6em; margin: 0 0.25em; line-height: 1; border-radius: 0.35em;">
    more than a third
    <span style="font-size: 0.8em; font-weight: bold; line-height: 1; border-radius: 0.35em; vertical-align: middle; margin-left: 0.5rem">CARDINAL</span>
</mark>
 of global military spending, it is the foremost military power in the world; and it is a leading political, cultural, and scientific force internationally.[23]</div></span>



```python

```
