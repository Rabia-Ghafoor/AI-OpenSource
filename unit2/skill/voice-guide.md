# Voice guide: how I talk upstream

<!--
THIS IS THE PART YOU WRITE (new this week). Live mode reads this file
before any comment of yours goes out the door; eval mode ignores it
entirely, because your voice is yours and carries no gold labels.

This is not etiquette. "Be polite and concise" is advice for everyone
and therefore rules for no one. Write rules YOU need, in your own
words, each one concrete enough that the skill can hold a draft
against it and say which rule it breaks.

Three sections. Fill all three.
-->

## Who I am in threads

<!-- 2-3 lines. Who is talking when you comment on an issue: your
experience level stated plainly, what you are doing in this repo, what
readers can expect from you. This is the register your rules protect. -->

I'm a new open-source contributor, posting my first reproduction
reports as part of a course. I'm still learning this repo's norms, so
I say only what I actually checked, I ask instead of assuming when I'm
unsure, and I expect maintainers to see a careful beginner, not an
expert.

## Rules I write by

<!-- 3-5 rules, drafted from the lecture's slide-12 moment. Each rule
needs a wrong/right pair from your own hand: one line you might
actually have written that breaks the rule, and the line you would
post instead. The pair is what makes a rule executable; a rule without
one is a wish.

Format each rule like this:

### Rule: <short name>

<The rule, one or two sentences.>

- Wrong: "<a line that breaks it>"
- Right: "<the line to post instead>"
-->

### Rule: no manufactured confidence

State only what I actually verified. Don't round "it seemed to work"
up to "fixed" or "confirmed."

- Wrong: "This definitely fixes the issue."
- Right: "Running the steps above, the error no longer appears on my
  machine (Node 20.11, macOS 14). I haven't tested other
  environments."

### Rule: no vague hedging

If I'm not sure, I say exactly what I'm unsure about, not a generic
hedge that could apply to anything.

- Wrong: "This might be related, not totally sure."
- Right: "I couldn't reproduce the crash itself, but I saw the same
  warning in the console at line 42."

### Rule: no boilerplate openers

Skip stock phrases that carry no information about this specific
issue.

- Wrong: "Thanks for reporting this issue! I took a look and..."
- Right: "I reproduced this on v2.3.1 following the steps in the
  issue."

### Rule: no em dashes

Write sentences that don't lean on em dashes for structure. Use
periods, commas, or parentheses instead.

- Wrong: "The build fails - but only on Windows - because of a path
  separator bug."
- Right: "The build fails only on Windows, because of a path
  separator bug."

### Rule: no flattering tone

Don't compliment the maintainer or the project as a substitute for
content.

- Wrong: "Great project, love the work you all do! Anyway, found a
  bug..."
- Right: "Found a bug in the v2.3 release when running the steps
  below."

## Things I never post

<!-- A short list. Promises you cannot keep, tones you refuse,
shortcuts you know you reach for when tired. The skill quotes this
list back at you when a draft crosses it. -->

- Claiming "confirmed" or "fixed" without pasting the output that
  shows it.
- Presenting a step I did not personally run as if I ran it.
- Boilerplate praise ("great project," "thanks for all your hard
  work") used to pad a comment.
- An em dash, ever.
- A disclosure left half-filled because I ran out of time.

