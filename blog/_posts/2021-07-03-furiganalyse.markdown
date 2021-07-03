---
layout: post
title:  "Furiganalyse: adding furigana to Japanese ebooks"
date:   2021-07-03 16:41:17 +0200
comments: true
---

TL;DR: I've made a webapp to annotate Japanese EPUB books with furigana, [try it here][furiganalyse-demo]

Have you ever been frustrated when reading a Japanese book because you could not remember that word's reading ?
Even with an ereader with a build-in dictionary, popping up the dictionary just to get the reading can take up some time.
It would be much more convenient to have all the furigana written aside in the first place...

I've looked up projects to do this and only found [this one][furiganalyse-epub].
After managing to make run, I discovered that there was many bugs with the furigana generation and decide to create my own project.

[Furiganalyse][furiganalyse-github] is a webapp and command line program to annotate EPUB ebook with furigana.
I will add furigana for all kanjis, but will not override any existing one.
Since it is a pain to setup all the dependencies and dictionaries, I've deployed the app [here for you to try][furiganalyse-demo].

Under the hood, furiganalyse leverages [my fork of the "furigana" project][itsupera-furigana-github] to generate the furigana.
It is using the MeCab toolkit to segment the sentence into "words" and get their individual reading.
The more complex part was mapping each kana of the reading to each kanji of the original text.
There a few annoying cases to deal with, and though it will fail from time to time it is really usable at this point.

[furiganalyse-demo]: http://furiganalyse.eu-west-3.elasticbeanstalk.com
[furiganalyse-epub]: https://github.com/haoxuany/furiganalize-epub
[furiganalyse-github]: https://github.com/itsupera/furiganalyse
[itsupera-furigana-github]: https://github.com/itsupera/furigana