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
