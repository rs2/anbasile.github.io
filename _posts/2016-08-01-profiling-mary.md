---
layout: post
title: Profiling the Holy Mary
date: 2016-08-01
---

For those who do not know it, Medjugorje is a small village in the mountains of Bosnia. In 1981, in the communist &#x2014; and atheist &#x2014; Yugoslavia, the Holy Mary started popping out in this place saying stories to a bunch of locals. Since then the messages have been carefully[TODO meticolosamente] recorded; a few websites around the web regularly publish these messages. I have collected all of them and visualized the content. In this post I will explain you how I did it. In the meanwhile I will explain some basic concepts of natural language processing. After reading this post you should have a clear idea of the followings [TODO check grammar]:

1.  what is a corpus?
2.  how to create a corpus from a web page
3.  how to describe a corpus?
4.  how to outline the corpus's content

# Scraping the holy words<a id="sec-1" name="sec-1"></a>


First, I googled "medjugorie" and the first important result that came out is [medjugorje.ws](http://www.medjugorje.ws/)

![img](_posts/img/medju_hp.png "A screenshot of medjugorje.ws")

It seems that this site stores all the messages. We need to download the text of the message, the date &#x2014; if it's available &#x2014; and any additional information that we can get.

We could use firebug [TODO add footnote and link] to see how the web page is built and then use an html parsing tool to grab the elements we want. 

![img](_posts/img/medju_debug.png "An example of using firebug")

Setting up a scraper by hand it's a tedious process and it's for another story. I have recently discovered a great service, it is called [ import.io](http://import.io): we will use it to capture the data from our target web site.

![img](_posts/img/import_hp.png "import.io's homepage")

With import.io we can create a new dataset from a website in a few minutes (!) with no coding at all. So, I you haven't done it yet, create a free account so that we can start building our Holy corpus together.

[&#x2026;] 

[TODO insert screenshot collage]
We will create a new extractor called "holy data". After a few minutes spent browsing the page, I discovered that there is a single page containing all the messages, from 1981 to the last one: all together they add up to N [TODO fix number][fn :: Yes, these are all miracolous apparitions of the Virgin Mary.].

We can just insert this single url in our extractor and retrieve all the messages at once. Usually the data we want is spread across multiple pages of the same site. Not this time.

Once we insert the url, import.io will parse the page and it will show it to us along with a tool to annotate the data we want. We create a new column for every field we want in our dataset.

In this case we want the followings:

-   text
-   date
-   description
-   type of message

For the extractor to work it usually only needs two examples and it will figure out the rest thanks to some algorithms doing the work for us.

For example, to get the text, we select the first two message's text and import.io will correctly grab all the rest.

[TODO insert image]

After having performed the same operations for all the fields we will end up having a dataset like this:

[TODO insert screenshot]

A *collection of document* is what is called a **corpus**. Almost all modern language technology is somehow corpus based. Corpus may consist of written texts or spoken dialogues; [TODO completa lista e aggiungi citazione da Manning]

Let's download it as a csv and we are done. It still need some manual tuning, but it is already a clean and usable corpus.


As you may have noticed, I had to select the first letter of each message because it belongs to a different html block: this means that now we have to merge the column containing these first letters with the one containing the rest of the message.

# Some statistics<a id="sec-2" name="sec-2"></a>


We can now take a quick look at our corpus. 

[TODO insert token type t/t ratio and frequency plot]

The shape of the curve roughly follows Zipf's prediction [TODO add link to Zipf biography]. In order to plot this graphic we first have to count the words in the corpus. We do this by removing all the whitespace in the text and replacing it with `newline` characters. So we go from this [TODO insert normal text] to this [TODO insert tokenized text].

Good. So now we have N [TODO fix] word *tokens*. A token is an occurence of a word. This sentence has five tokens. And five *types*: five occurrences of five different words. This other sentence has N tokens; and has N types. [TODO write a better one].

This is the code that does the work.

    --- todo add code

Now, lets zoom in [TODO 1 or 2 *in* ?] the table and see which are the most frequent words occurring in the text of the Holy Mary.

[TODO add table and img of zoom]

And these are the so calleld *stop words*. [TODO find definition]

We can filter those words by frequency and separate them from *content words*.

    ---[TODO]  put code for filtering here

We want to know what these messages are about. Now that we have separated functional words from content words, we now sort the latters by frequency:

[TODO insert freq table]

Interesting. But one word alone is not enough. Let's try with word couples.

[TODO insert bigram freq table]

Better. [TODO comment results]. But there is something to point out here:

[TODO insert bigram freq table with non interestingn bigrams highlited]

So, we need to weigh [TODO check word] the results and promote the most interesting ones in the higher part of the list. The following equation will do the job. We will apply it first, take a look at the result and then I'll explain it.

[TODO insert pmi formula]

# Ascension in the (word) cloud<a id="sec-3" name="sec-3"></a>


Now that we have a way of finding the intersting words and word couples, we can build a word cloud.

Word clouds are a somehow naive but visually appealing tools for representing the content of a document in a succint way.

The idea is simple: we extract the words from the corpus, we somehow filter them and then we display each word in a differnt way depending on the role it plays in the corpus. For example, we could color in red all the nouns, and in blue all the verbs, and assign differnt font dimensions to each word depending on they frequency it occurs.

# tl;dr<a id="sec-4" name="sec-4"></a>

1.  registe for free on import.io
2.  create a  new extractor
3.  insert the following link: [TODO add link]
4.  create N columns: [TODO add ]
5.  for each coluns
6.  

# What else?<a id="sec-5" name="sec-5"></a>

1.  recap
2.  what could we do?
    -   parallel corpus
    -   author attribution (clustering)
        -
