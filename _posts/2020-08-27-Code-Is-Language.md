---
layout: post
title: Code is language // Objectifying language
---

<figure class="float-right clearfix">
<div>
<img src="https://media.giphy.com/media/fyzODLrZORdUA/giphy.gif" alt="Math is worthless in real life">
<figcaption>Leslie Knope, you are an opalescent tree shark.</figcaption>
</div>
</figure>
What scared me about learning to code was thinking there was a lot of math involved. I muddled through Calc 2 in college, but I can’t say that any of it stuck. Calculus forwards is hard enough, now we're doing it backward? This fear came about because the operators and symbols used are also in math equations. When really, coding is more like writing logical instructions to computers with words. Coding is in a language after all.

Math teachers should not be the only ones teaching logic. English teachers should be too! Think about it: how often have you read a sentence that doesn’t make sense? Look in your texts and consider how little sense each of those texts makes as stand-alone sentences. Today we’re looking at coding as a language to express ideas. I’ll be using JavaScript as our programming language because I’m most comfortable with it.

## Parts of Speech


> **English**:
>
> noun, adjective, verb, conjunctions (and, but, or).
>
> **JavaScript**:
>
> object, properties, method, logical operators ( `&&, !, ||`).

What are objects? They’re nouns. A person, place, or thing. In JavaScript a String is just text, a value of the text that is accepted literally.  JavaScript Numbers are... well... how do we describe the idea of a number in real life? Consider how the concept of 42 can be written differently in Arabic numbers or Japanese characters. They both mean the concept of 42 without being the literal characters "42."

<figure class="float-right">
<div>
<img src="https://thekidshouldseethis.com/wp-content/uploads/2014/10/noun_schoolhouserock.jpg" alt="School House Rock, school is a noun">
<figcaption>One of my favorite albums in high school was <i> School House Rock Rocks!</i>
</figcaption>
</div>
</figure>Strings and Numbers are understood differently when read by the computer in the same way we understand Birds and Fish to be nouns that have type-specific ways of understanding them. Birds don't fly by flapping their fins for instance.

There are actions that each noun can inherently do because of their type. Let's look at Birds and Fish. Birds have available to them the action "fly," and Fish has the action "swim." In English, actions are called "verbs." Some verbs are inherent to the type of creature. Fish don't have the action "fly" available to them, but birds do (except adorable penguins and kiwis). In JavaScript, verbs are called methods. Usually, you'll know it's a method if it is attached to the noun with a `.` and is followed by `()`. Something like `String.trim()` is how the String calls the method "trim" to remove whitespace from the front and end of the String.

Adjectives in English befuddled me until junior high. I kept getting them confused with adverbs. Adjectives are words that describe the noun. JavaScript properties describe the object. `String.length` is used to describe a String by how many characters it's made of. So I could say to a person, "Tell me, what color is the fish?" They would reply, "blue." Likewise, we could ask a computer `Fish.color` and receive the response `"blue"`.

## Sentences and code aren't just strings of words
When we write a sentence in English, we're supposed to have a subject and predicate. A noun and verb. Same as in coding. "Fish" as a sentence means little and is pretty ambiguous. What about the fish? Are you telling someone to go fishing? Do you want a fish? "You, give me a fish," is clear and has a subject (you) and predicate (give). I could write that as `you.give(fish)` in JavaScript.


>**Let's say something else!**
>
>`you.say("it ain't so.")` is the instruction, "Say, 'it ain't so.' "
>
>`jay.eat(burrito)` is the command, "Jay, eat a burrito."
>
>`you.goChasingWaterfalls(false)` would be how I tell the computer, "don't go chasing waterfalls."

Notice it's all commands. Remember, it's not a real conversation with a computer. No banter, no back and forth. It's directions. I am telling a computer what to do and in what order. A computer will only do exactly what it is told. So if we give instructions correctly, things go right. Otherwise, they're like wishes to a naive genie: Something is always just a little wrong. Fortunately, you can test your code before having rippling effects across space-time. Not so much with the genie wishes.

## Let's recap:
- Coding isn't math, it's giving logical instructions
- Nouns are objects: people, places or things
- They have inherent actions: verbs/methods
- They also have attributes that describe it: adjectives/properties
- Don't be a weird communicator, what's the subject and what are - they doing?
- Computers are naive genii, be explicit and precise about what you say to them or the outcome is unpredictable.