# Testing the Accuracy of several English and Russian POS-teggers

Our goal here is to assess accuracy of three most popular POS-taggers for English and Russian languages each:
- Spacy, Flair, NLTK for English
- Natasha, Mystem, Pymorphy for Russian

We test them on two arbitrary texts:
- "Приходящие и уходящие из магазина покупатели охрану бесили неимоверно. Несмотря на то, что работали те спустя рукава и не смотря вокруг, у них было статус-кво и острое чувство справедливости! И дубинки. Их де-юре бессменное владение территорией де-факто ограничивалось кассой да пятачком у автоматиков. Тем не менее, им было где разгуляться, особенно утром – в гостиной отеля, хотя бы, хоть она и выходила за рамки магазинчика у ограды. Охранники туда выбирались, хоть ты тресни – кто им запретит? Разве что УК РФ, и то не факт. Книжицей законности им в наглые лица еще никто не натыкал, хотя горничные типа Ниночки и порывались. Сильно смелых в штате не нашлось ни тем утром, ни любым другим."
- "To put it mildly, all of that was weird. They were weirdos! All these insane shenanigans were frying my mind. No way this was happening. God damn. Oh, these people, they tried to help! They were my main source of inspiration, little softies. But the odds of me getting out were slim. I had to part from here, I really did. But what would that cost me?  At what cost would I manage? I put my sharpie away and stayed put. The light was light and soft. I was starting to doubt my silly doubts beyond all rational thought. There was no return, no safehouse. The end was closing in."

Here's how we tagged them to get the ground truth: you can see it in this file. Any and all suggestions are welcome! POS can be weird and ambiguous.

And here's the accuracies and mistakes for each tagger:
In English:
- Accuracy of Spacy is: 0.9090909090909091; as mistakes, it had:  [[{'слово': 'my', 'разбор': 'DET'}, {'слово': 'my', 'разбор': 'PRON'}], [{'слово': 'damn', 'разбор': 'INTJ'}, {'слово': 'damn', 'разбор': 'V'}], [{'слово': 'my', 'разбор': 'DET'}, {'слово': 'my', 'разбор': 'PRON'}], [{'слово': 'out', 'разбор': 'A'}, {'слово': 'out', 'разбор': 'PREP'}], [{'слово': 'part', 'разбор': 'V'}, {'слово': 'part', 'разбор': 'N'}], [{'слово': 'what', 'разбор': 'DET'}, {'слово': 'what', 'разбор': 'PRON'}], [{'слово': 'my', 'разбор': 'DET'}, {'слово': 'my', 'разбор': 'PRON'}], [{'слово': 'away', 'разбор': 'A'}, {'слово': 'away', 'разбор': 'PREP'}], [{'слово': 'my', 'разбор': 'DET'}, {'слово': 'my', 'разбор': 'PRON'}], [{'слово': 'There', 'разбор': 'PRON'}, {'слово': 'There', 'разбор': 'DET'}]]

- Accuracy of Flair is: 0.9; as mistakes, it had:  [[{'слово': 'that', 'разбор': 'PRON'}, {'слово': 'that', 'разбор': 'DET'}], [{'слово': 'this', 'разбор': 'PRON'}, {'слово': 'this', 'разбор': 'DET'}], [{'слово': 'damn', 'разбор': 'A'}, {'слово': 'damn', 'разбор': 'V'}], [{'слово': 'out', 'разбор': 'A'}, {'слово': 'out', 'разбор': 'PREP'}], [{'слово': 'part', 'разбор': 'V'}, {'слово': 'part', 'разбор': 'N'}], [{'слово': 'that', 'разбор': 'PRON'}, {'слово': 'that', 'разбор': 'DET'}], [{'слово': 'what', 'разбор': 'DET'}, {'слово': 'what', 'разбор': 'PRON'}], [{'слово': 'away', 'разбор': 'A'}, {'слово': 'away', 'разбор': 'PREP'}], [{'слово': 'put', 'разбор': 'A'}, {'слово': 'put', 'разбор': 'V'}], [{'слово': 'There', 'разбор': 'PRON'}, {'слово': 'There', 'разбор': 'DET'}], [{'слово': 'in', 'разбор': 'A'}, {'слово': 'in', 'разбор': 'PREP'}]]

- Accuracy of NLTK is: 0.9090909090909091; as mistakes, it had:  [[{'слово': 'To', 'разбор': 'PREP'}, {'слово': 'To', 'разбор': 'PART'}], [{'слово': 'weirdos', 'разбор': 'A'}, {'слово': 'weirdos', 'разбор': 'N'}], [{'слово': 'damn', 'разбор': 'N'}, {'слово': 'damn', 'разбор': 'V'}], [{'слово': 'to', 'разбор': 'PREP'}, {'слово': 'to', 'разбор': 'PART'}], [{'слово': 'out', 'разбор': 'PART'}, {'слово': 'out', 'разбор': 'PREP'}], [{'слово': 'to', 'разбор': 'PREP'}, {'слово': 'to', 'разбор': 'PART'}], [{'слово': 'away', 'разбор': 'A'}, {'слово': 'away', 'разбор': 'PREP'}], [{'слово': 'put', 'разбор': 'N'}, {'слово': 'put', 'разбор': 'V'}], [{'слово': 'to', 'разбор': 'PREP'}, {'слово': 'to', 'разбор': 'PART'}], [{'слово': 'There', 'разбор': 'PRON'}, {'слово': 'There', 'разбор': 'DET'}]]
 
In Russian:
- Accuracy of Natasha is: 0.8288288288288288; as mistakes, it had:  [[{'слово': 'несмотря', 'разбор': 'A'}, {'слово': 'несмотря', 'разбор': 'PREP'}], [{'слово': 'спустя', 'разбор': 'PREP'}, {'слово': 'спустя', 'разбор': 'V'}], [{'слово': 'бессменное', 'разбор': 'V'}, {'слово': 'бессменное', 'разбор': 'A'}], [{'слово': 'утром', 'разбор': 'N'}, {'слово': 'утром', 'разбор': 'A'}], [{'слово': 'хоть', 'разбор': 'CONJ'}, {'слово': 'хоть', 'разбор': 'PART'}], [{'слово': 'и', 'разбор': 'PART'}, {'слово': 'и', 'разбор': 'CONJ'}], [{'слово': 'рамки', 'разбор': 'N'}, {'слово': 'пределы', 'разбор': 'N'}], [{'слово': 'хоть', 'разбор': 'CONJ'}, {'слово': 'хоть', 'разбор': 'PART'}], [{'слово': 'кто', 'разбор': 'PRON'}, {'слово': 'кто', 'разбор': 'A'}], [{'слово': 'что', 'разбор': 'CONJ'}, {'слово': 'что', 'разбор': 'PART'}], [{'слово': 'еще', 'разбор': 'A'}, {'слово': 'еще', 'разбор': 'PART'}], [{'слово': 'никто', 'разбор': 'PRON'}, {'слово': 'никто', 'разбор': 'A'}], [{'слово': 'хотя', 'разбор': 'CONJ'}, {'слово': 'хотя', 'разбор': 'PART'}], [{'слово': 'типа', 'разбор': 'PREP'}, {'слово': 'типа', 'разбор': 'A'}], [{'слово': 'порывались', 'разбор': 'N'}, {'слово': 'порывались', 'разбор': 'V'}], [{'слово': 'ни', 'разбор': 'CONJ'}, {'слово': 'ни', 'разбор': 'PART'}], [{'слово': 'утром', 'разбор': 'N'}, {'слово': 'утром', 'разбор': 'A'}], [{'слово': 'ни', 'разбор': 'CONJ'}, {'слово': 'ни', 'разбор': 'PART'}], [{'слово': 'любым', 'разбор': 'PRON'}, {'слово': 'любым', 'разбор': 'A'}]]

- Accuracy of Mystem is: 0.8648648648648649; as mistakes, it had:  [[{'слово': 'несмотря', 'разбор': 'A'}, {'слово': 'несмотря', 'разбор': 'PREP'}], [{'слово': 'те', 'разбор': 'A'}, {'слово': 'те', 'разбор': 'PRON'}], [{'слово': 'спустя', 'разбор': 'PREP'}, {'слово': 'спустя', 'разбор': 'V'}], [{'слово': 'утром', 'разбор': 'N'}, {'слово': 'утром', 'разбор': 'A'}], [{'слово': 'рамки', 'разбор': 'N'}, {'слово': 'пределы', 'разбор': 'N'}], [{'слово': 'кто', 'разбор': 'PRON'}, {'слово': 'кто', 'разбор': 'A'}], [{'слово': 'что', 'разбор': 'CONJ'}, {'слово': 'что', 'разбор': 'PART'}], [{'слово': 'еще', 'разбор': 'A'}, {'слово': 'еще', 'разбор': 'PART'}], [{'слово': 'никто', 'разбор': 'PRON'}, {'слово': 'никто', 'разбор': 'A'}], [{'слово': 'хотя', 'разбор': 'CONJ'}, {'слово': 'хотя', 'разбор': 'PART'}], [{'слово': 'типа', 'разбор': 'N'}, {'слово': 'типа', 'разбор': 'A'}], [{'слово': 'ни', 'разбор': 'CONJ'}, {'слово': 'ни', 'разбор': 'PART'}], [{'слово': 'тем', 'разбор': 'A'}, {'слово': 'тем', 'разбор': 'PRON'}], [{'слово': 'утром', 'разбор': 'N'}, {'слово': 'утром', 'разбор': 'A'}], [{'слово': 'ни', 'разбор': 'CONJ'}, {'слово': 'ни', 'разбор': 'PART'}]]

- Accuracy of Pymorphy is: 0.7837837837837838; as mistakes, it had:  [[{'слово': 'приходящие', 'разбор': 'A'}, {'слово': 'приходящие', 'разбор': 'V'}], [{'слово': 'уходящие', 'разбор': 'A'}, {'слово': 'уходящие', 'разбор': 'V'}], [{'слово': 'то', 'разбор': 'CONJ'}, {'слово': 'то', 'разбор': 'PRON'}], [{'слово': 'те', 'разбор': 'A'}, {'слово': 'те', 'разбор': 'PRON'}], [{'слово': 'спустя', 'разбор': 'PREP'}, {'слово': 'спустя', 'разбор': 'V'}], [{'слово': 'да', 'разбор': 'PART'}, {'слово': 'да', 'разбор': 'CONJ'}], [{'слово': 'тем', 'разбор': 'CONJ'}, {'слово': 'тем', 'разбор': 'PRON'}], [{'слово': 'им', 'разбор': 'N'}, {'слово': 'им', 'разбор': 'PRON'}], [{'слово': 'гостиной', 'разбор': 'A'}, {'слово': 'гостиной', 'разбор': 'N'}], [{'слово': 'хотя', 'разбор': 'CONJ'}, {'слово': 'хотя', 'разбор': 'PART'}], [{'слово': 'хоть', 'разбор': 'CONJ'}, {'слово': 'хоть', 'разбор': 'PART'}], [{'слово': 'рамки', 'разбор': 'N'}, {'слово': 'пределы', 'разбор': 'N'}], [{'слово': 'хоть', 'разбор': 'CONJ'}, {'слово': 'хоть', 'разбор': 'PART'}], [{'слово': 'кто', 'разбор': 'PRON'}, {'слово': 'кто', 'разбор': 'A'}], [{'слово': 'им', 'разбор': 'N'}, {'слово': 'им', 'разбор': 'PRON'}], [{'слово': 'что', 'разбор': 'CONJ'}, {'слово': 'что', 'разбор': 'PART'}], [{'слово': 'то', 'разбор': 'CONJ'}, {'слово': 'то', 'разбор': 'PRON'}], [{'слово': 'им', 'разбор': 'N'}, {'слово': 'им', 'разбор': 'PRON'}], [{'слово': 'ещё', 'разбор': 'PART'}, {'слово': 'еще', 'разбор': 'PART'}], [{'слово': 'никто', 'разбор': 'PRON'}, {'слово': 'никто', 'разбор': 'A'}], [{'слово': 'хотя', 'разбор': 'CONJ'}, {'слово': 'хотя', 'разбор': 'PART'}], [{'слово': 'горничные', 'разбор': 'A'}, {'слово': 'горничные', 'разбор': 'N'}], [{'слово': 'типа', 'разбор': 'N'}, {'слово': 'типа', 'разбор': 'A'}], [{'слово': 'тем', 'разбор': 'CONJ'}, {'слово': 'тем', 'разбор': 'PRON'}]]
