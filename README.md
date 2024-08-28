# GRAMMAR DEVELOPMENT: FINAL PROJECT


## Why I chose this pheonemon?
<div align="justify">
The grammar developed for the project is aimed at parsing two phenomena in the Dutch language: (1) negation and (2) adjective-noun agreement. The main focus was on implementing negation, however, in order to create more sentences, it was necessary to tackle adjective-noun agreement as well.
</p>
<p align="justify">
	To begin with, the basic concept of negation seems quite straightforward: we want to change the truth value of a sentence or a statement. For example, the sentences “De vrouw loopt snel.” (The woman walks fast.”) and “De vrouw loopt niet snel.” (“The woman does not walk fast.”) mean two different things. In this case, we have made use of the word “niet” (“not”) to negate the sentence. However, there are also other ways of negating a sentence. In this project I have focused on the following ways for negating a sentence: “niet” (“not”), geen (in English “no”, but more like the German “kein”), and niemand (“nobody”). In general, one can say that “niet” is used for negating verb phrases and “geen” is used for negating noun phrases, while “niemand” is a pronoun and can be used at the beginning of a sentence “Niemand eet de koekjes.” (“Nobody ate the cookies.”) or as an object in a verb phrase “Marie zag niemand.” (“Marie saw nobody/no one.”). 
</p>
<p align="justify">
	The second phenomenon is about adjective-noun agreement. In Dutch, the adjective can appear in two forms, e.g. “smakkelijk” (“tasty”) and “smakkelijke”. The form of the adjective depends on two things: (1) the gender of the noun and (2) the number of the noun. In Dutch there are three genders, feminine, masculine, and neuter. There are two definite articles “de” (for both genders feminine and masculine) and “het” (for neuter), and one indefinite article “een”. To illustrate, if we use the definite article and the number is singular, we always add an -e to the adjective, such as “het grote huis” (“the big house”) or “de grote vrouw” (“the tall woman”). If the number is plural, we always use the definite article “de”, “het grote huis” (singular) and “de grote huizen” (plural). The only time we don’t add the -e is for neuter nouns with the indefinite article, “een groot huis” and “een grote vrouw”. 
</p>
<p align="justify">
	With the rise of Language Models (LM), rule-based applications are moer and more on the decline. However, there are some aspects of language which remain challenging for LMs, such as negation. Studies (Kassner & Schütze 2020) have shown that LMs, such as BERT, oversee or misinterpret negation. Therefore, I think it is interesting to approach negation from a rule-based perspective and, consequently, I haven chosen this topic for my project.
</p>


## Implementation approach and design
<div align="justify">
The approach for implenting negation into the grammar is by defining a new category NEG. Words that are categorized as NEG are words that negate a sentence. First, we define the entries in the lexicon. For example, niet NEG* (^NEG) = + (^NEGTYPE) = verb. Here, we first define (^NEG) + which will be shown in the f-structure to know that the sentence is negated. Then, we define that "niet" is of the (^NEGTYPE) verb. This is done because we want to restrict the usage of "niet". We have the same entry for "geen", but here the (^NEGTYPE) is noun. For "niemand", we do not characterize it as NEG because it is a pronoun. In the lexicon we add (^NEG) = + and define its (^NEGTYPE) as pronoun. 
</p>
