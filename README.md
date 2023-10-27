# Fiction-Decimal-System

Almost twenty years ago, it occurred to me that it might be possible to formulate a Dewey-Decimal-like system for fictional works that would classify those stories, such that if two have similar codes, then the stories themselves would be similar in proportion to how much the codes matched. Additionally, these codes would encapsulate the ideas behind the story well enough to enable readers (or viewers) to determine one to be within their scope of interest *agnostic of genre*. In fits and starts, I Have worked on this ever since.

## The Basics

Genre is usually sufficient to know whether one might be interested in a story. Many people prefer romance, or science fiction, or westerns, or historical fiction. But within each of those genres the range is so vast (and ever changing), that it often doesn't guarantee a good match. I propose a better way of classifying fiction. In this system, any given story can be decomposed into at most three distinct values and each of those can be assigned a unique (semi-)numerical code. Two of these values represent the protagonist and antagonist (only one required), and the third value represents the overall plot. The format or convention for code will look like:

    p=123;a=456;s=789;

The order of prefixes must always be `p`, `a`, and `s`, even though only two of the three are required (at least one of `p` or `a`). The `=` punctuation is also required, and that punctuation mark is not used for any other meaning. The values are separated with semicolons, `;`, and that punctuation mark isn't used for any other meaning than to separate the (two or) three values.

Each numerical value is variable length and can start with the digits 0-9. Leading zero digits are significant and should not be dropped. Numerical values occasionally use punctuation marks for meaning. Multiple values can be concatenated together for group ensembles with commas, `,`. A show about a duo crime-fighting magicians who battle the forces of apathy might use a code like so:

    p=726,7284;a=7991671;s=533

While both are stage magicians, one performs lady-sawn-in-half tricks, and the other juggles chainsaws. Each therefor needs his own value, and both are equally the protagonist. Thus `p` is set to both values delimited by `,`. The values should always be arranged in order of least to greatest, as if a decimal point exists to the right of the first digit (7.26 is less than 7.284).

The identity of the protagonist and antagonist is somewhat subjective, but the story where there can be no general agreement on which is which should be rare. Software can account for this, and query for stories where these are swapped from what a searcher might want.

### Protagonists & Antagonists

Both protagonists and antagonists use the same list of values. The values for these are grouped into ten categories, [which can be browsed here](/codes/protag_antag/root.md).

    0 - 
    1 - Military
    2 - Law Enforcement
    3 - Criminals
    4 - Government
    5 - Royalty & Nobility
    6 - Religion
    7 - The Fantastic
    8 - Animals & Organisms
    9 - 

All stories that we are aware of have been written, told by, and conceived of by humans, thus almost all of these values represent some sort of human. Sometimes they describe lifestyles, other times occupations. They describe the relationships they belong to, the hobbies that the engage in, or some other aspect that someone would use to describe them if they were speaking about them to others. Two categories are (mostly) the exception here. `8x` is the category for a protag/antag who isn't human but rather some other type of animal (or organism). The bear cub in a semi-fictional Disney documentary, perhaps. The only entries that might refer to a human are the `89330x` values, which refer to Neanderthals and other ancient ancestors of humanity. The other is `7x`, and encompasses most or all of the protags/antags you'd find in fantasy, science fiction, weird fiction, mythological stories, and ghost stories. Elves and goblins, dragons, Vulcans, Odin, angels, robots, Frankenstein's monster, and many others.

These codes are nested hierarchially. It is not necessary to choose the most specific leaf node, if a more general branch node suffices. Values are arbitrary, a `70x` value is not necessarily more distant from `78x` than `79x` is, but all `7x` values are approximately the same distance from an arbitrary `8x` code.

Some of the names for these classes of protagonists and antagonists aren't popular terms. Where possible, names from [TV Tropes](tvtropes.com) are preferred over novel terminology.

### Plots (Stories)

Plots use a similar hierarchial structure for values. Each is variable length and can start with the digits 0-9. Leading zero digits are significant and should not be dropped. Numerical values occasionally use punctuation marks for meaning. Unlike with protag/antag, multiple values are discouraged. There may be some story formats where multiple, equally important plots are told simultaneously, and only in those cases should `,` be used to list multiple plots. The most familiar format that does this is broadcast television's A/B plot, usually relegated to sitcoms. As with protag/antag value lists, these should be ordered from least to greatst.

The values of these are grouped into ten categories, [which can be browsed here](/codes/story/root.md).

    0 - 
    1 - 
    2 - 
    3 - 
    4 - 
    5 - 
    6 - 
    7 - 
    8 - 
    9 - 

Some of the names for these classes of plots aren't popular terms. Where possible, names from [TV Tropes](tvtropes.com) are preferred over novel terminology.

   
## Protagonist/Antagonist Codes

Note: Everything described in this section applies equally to antagonists as well as protagonists.

There is a bit more complexity required to do some characters justice. While the introduction touches on how to describe mulitple protagonists when only describing one or the other, this doesn't really explain how to encode two characters who have the same description. When a character can't be described as just *one* thing, it doesn't explain how to combine two codes to indicate that both codes describe the same character. And finally, when a character is best described by what he or she *is* compared to what he or she *was*, this also requires two codes.

### Singular vs. Plural

The introduction has already sketched out how to indicate multiple protagonists (or antagonists), a comma-delimited list of codes is supplied. The list itself is plural and contrasts nicely with a singular code. However, occasionally it will be necessary to describe two or more protagonists who all use the same code. In *Butch Cassidy and the Sundance Kid* the two protagonists are both Wild West outlaws (train robbery mostly), and it's difficult to imagine how they might be substantially different. Rather than making the full code substantially longer by stringing together two of the same code, the single code can be given a suffix of `+`, like so:

`3045+`

This only indicates plurality and not exact quantity. The code would be equally correct for a movie about four train robbers as it would be for two train robbers.

Furthermore, it can be used with non-leaf nodes. A television show with an ensemble cast about NYPD police officers would use the following:

`213400061+`

A plural code can also be included in a list if necessary, like so:

`213400061+,405681`

### Multi-faceted Characters

Occasionally, a complex character can't be described very well with a single code. *Indiana Jones* need not be coded both as an archaeologist and an adventurer (though he is surely both), because the "adventurer" part is the conceit of the films. They do not show him doing boring field management work over a bunch of interns and grad students and surly porters. But, from the same era we have *Buckaroo Banzai* who is a brain surgeon, rock star, *and* theoretical physicist. (Note: This is a special case where a three-faceted code could be justified, normally only two should be permitted.)

The codes should be combined with an `&` mark. The order that these codes should appear in is from least to greatest. For example, this is correct:

`p=1234&256`

But this is incorrect

`p=256&1234`

### Transformed Characters

Let us start with examples. Our first is a story for a small child, perhaps as an illustrated reader. A butterfly lives a life where he speaks to others about how he was once a caterpillar. Our second story concerns a Buddha-like figure who was once ordinary, but at the time of the story has received epiphany and knows how to live life. (Note: Though this is very much not Buddha, because there's a code for him specifically, several in fact.) The details of his former life (or even his current), are less important to the story than that the change has occurred. A third story is a more modest version of a previous, an alcoholic has through sheer power of will made himself sober. Finally, the fourth story is that of a broken man, who has lost everything once dear to him.

The codes for these characters will look like the following:

*Butterfly-once-caterpillar* - `p=8123>>8456`  
*Spiritually-awakened-man* - `p=0789>>0246`  
*Former alcoholic* - `p=0357>>0999`  
*Broken man* - `p=0222>>0888`  

Each of these will use the double `>>` closing angle bracket (greater than) as punctuation that combines two codes to indicate a single code. In typeset print intended only for eyes using a double right-pointing arrow is also acceptible (`0222⇉0888`), though in digital systems the punctuation **MUST** be the closing angle bracket. The earlier code must always be to the left of the later code.

It is not recommended to use multiple transformations for a single code number. Very rarely would a story demand it, no obvious examples exist. Perhaps a "rags to riches to rags" character might, but fiction rarely depicts these double transformations except as cliched utterances, hardly stories themselves.

It should be noted that the character *already needs to be transformed* by the start of the story. Perhaps a brief passage or scene at the very beginning is acceptable so as to establish the transformation, but if the character only transforms by the last chapter of the book, or for that matter, in the middle of the book, then the transformation is not the best way to describe the character. As a soft limit, consider that the transformation should be established within the first 10% of the story (running time, word/page/chapter count, etc).

There are some other considerations you must also make. Some genres and archetype stories are above all else about the transformation the protagonist undergoes. Joseph Campbell's *Hero with a Thousand Faces* and its many, many derivatives. Nor should story-framing devices confuse the issue. If the movie starts out "You're probably wondering how I got here", then it may be true that at the point of the narration that the transformation is complete, but the narrator isn't the story. He is telling the audience this story, and he'll begin with the very-much-as-of-yet-untransformed protagonist.
