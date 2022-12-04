# ADRs

ADRs (Architecture/Architectural Decision Records) are a useful tool for recording decisions related to a software project for future reference.

Read more about them at [adr.github.io](https://adr.github.io/).

My personal preference is to use the template from Michael Nygard's article [Documenting Architecture Decisions](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html) (status/context/decision/consequences) for its simplicity and tendency to push me towards being unbiased by avoiding pros and cons. Much of my advice below is also drawn from or inspired by this article.

That said, there are many popular templates, with varying levels of structure. See https://github.com/joelparkerhenderson/architecture-decision-record for examples.

Below, I have captured my thoughts on ADRs and how best to write them.

## Aim
The goal of an ADR is to clearly depict the situation at the time a decision was made, so that someone in the same situation with the same context would draw the same conclusions.

Put yourself into the mindset of a person from the future, who may be thinking:
- "This choice doesn't seem optimal today - what was the business or team's situation that led to it?"
- "We think that X is a better option but want to make sure there's nothing we're missing"
- "This decision is now having consequence Y - was this considered at the time?"

A reader should be able to evaluate the reasons behind a decision given a new context and know objectively if they are still true. If they are not, they should be able to confidently supersede the decision.

## Tips

### Be specific 💯
Drill down into the precise problem you are trying to solve. List assumptions about the future, and the particulars of _your_ situation. Provide concrete examples.

- ❌ "We are building an API that needs to scale"
- ✅ "We are building a GraphQL API for internal users [link to previous ADR]. We anticipate needing X performance requirements, based on current figures observed here: [link]. Based on current growth rate, request volumes would hit Y in 1 year's time"

### Stay relevant 🔗
General pros and cons do not help future readers understand why you chose a particular option for your situation.

Feel free to omit generic discussion and stick to the facts that are directly relevant to your specific situation.

Ask yourself "so what?" when reading your points.
- ❌ "X is the most popular database provider”"
- ✅ "The team has concerns around finding new developers with experience in Y"
- ✅ "The team expects an initial drop in productivity if they were to move to Y"

### Be comprehensive 🤓
If there is anything at all that is relevant to the decision, include it, even if it feels minor.

Paint a rich picture of the business context to allow for full recall and understanding in the future.

An exhaustive list of drivers means a future reader can supersede the decision, confident that they aren't missing anything.

### Stick to factual statements ✅
Try to avoid opinions. If opinions _were_ what led to the decision, call them out as such.

Every piece of context should be written so that it is impossible to disagree with, even by someone who disagrees with the decision.

Eliminate any degree of subjectivity. Opinions can be subtle, and masquerade as facts if cleverly stated - be on an eye out for these and rephrase them.

- ❌ "The developer experience of language X is better"
- ✅ "Having worked in both language X and language Y, it is the team's opinion that language X was more enjoyable to work with"
- ✅ "This annual developer happiness survey of 3000 developers has language X ranked top"

### Keep to one topic 1️⃣
If you find yourself answering a whole other question in the context of your ADR, it could be time for a separate ADR.

### Keep context value-neutral 😐
It's possible that things that are negatives in the current context could be positives in a different context. List facts and allow readers to decide if they are pros or cons.

This tip is more flexible; pros and cons lists can be okay if sticking to objective truths, but question your assumptions. Is something "bad" because of commonly held best practices that could change in the future? If so, say so!

- ❌ "Pro: tool X covers a broad range of other use cases"
- ✅ "Tool X covers a broad range of use cases. We currently anticipate the need for 2 of these, but this could be greater in the future"

### Cite your sources 🧐
If stating facts about options, link to supporting evidence.

If an article was useful to you, provide it - the age of the article or newer articles from the same author could be useful context when revisiting the decision.

Provide numbers if you can.

### Avoid passive voice 🗣️
Things don't happen by themselves - they're decisions made by a person or team, so list them as such and be clear.

If the decision is driven by opinions or rulings of a specific person/people external to the team, name them. This allows for a change of direction in the future if this person changes their mind or leaves the company.

Don't make it personal - keep it factual and check with the person that you have accurately represented their stance.

Avoid nebulous concepts such as "the business" - be specific about the team or person to allow a future reader to return to them with questions in a new context.

- ❌ "It was deemed unacceptable to have response times over 300ms"
- ✅ "The team wish to keep response times under 300ms"
- ✅ "There is a requirement from X person in product to keep response times under 300ms"

### Keep emotion out 😡
Even if you feel passionately about the topic, keep your writing dispassionate and stick to the facts.

Avoid being inflammatory or accusatory, even in undertone.

Do not apportion blame for how your context came to be; ideally, previous decisions have their own ADRs that provide explanation, but if they do not, assume all previous decisions were made in good faith given their respective contexts.

### Reference other ADRs 📝
Decisions from other ADRs can form assumptions for following ADRs, so make sure you refer back to them to provide full context.

### Don't assume anything is obvious 🤷‍
Different readers could have different experience or expertise that could lead them to a different conclusion.

Anticipate that someone could be reading your ADR in 5-10 years when industry standards are completely different.

### Ask "5 whys" 🤔
Interrogate your context/decision drivers. Dig down into the real underlying reasons and replace broader statements with the heart of the issue.

### Be honest 🤥
Avoid retrospectively painting a picture to explain a decision - put the real reasons, no matter what they are.

Don't shy away from recording "political" decisions accurately. Include business context, external pressures, personal preferences - whatever the _actual_ reason is for the decision being made.

This may force the team to confront uncomfortable truths or biases - but this is healthy and important to include as part of the reasons for a decision.

### Be concise 🤏
Nobody wants to read a wall of text. Be economical with words. Don't be afraid of coming across as blunt.

Don't feel the need to pad things out - short and to the point ADRs with only a couple of bullet points are fine (as long as you're comprehensive!)

### Use full sentences 🖋️
Despite the previous point, favour full sentences, good grammar and organised paragraphs. Writing in shorthand can leave statements open to interpretation and cause confusion.

### Expand on vague statements 🤗
Imprecise facts can belie the true behind-the-scenes story. Don't be afraid to really spell things out for the user, one point per bullet.

- ❌ "Using approach X would mean we couldn't hit our delivery commitments."
- ✅
  - "No team members have used approach X before."
  - "The team estimates they would take at least 2 weeks for them to get up to speed with approach X."
  - "We have a deadline in 3 weeks time."
  - "Negotiation to shift the 3-week deadline with marketing has been unsuccessful as social media content has already been posted."

Favour being explicit over expecting readers to read between the lines.

### Preempt questions or consequences 🔮
Aim for your ADR to read the reader's mind. Brainstorm potential "what about?"s and "have you considered?"s and head them off. A reader is ideally left without any remaining questions or concerns.

### Keep an open mind 🧘
Don't get attached to your ideas or a decision. You may find the process of writing the ADR itself changes your mind.

### Avoid bias 🙅
Try not to push the reader towards your conclusion, even through presentation of facts. The factual statements should paint a picture that lead the reader naturally towards the same conclusion as you. If they do not, use the tips above to make things more obvious - be specific, precise, honest, spell things out, etc.

### Use the power of editing ✏️
Refactor your ADR like you would your code. Writing is a skill and documentation is no different.

Reread after a break, remove words, reduce duplication, condense to a point where each sentence and word has impact and relevance.

Be ruthless and remove content if it doesn't add value, even if it took you time to write, or you're particularly proud of it.

### Write your ADR at the time of the decision ⏱️
Aim to write it up before making the decision, or if not possible, as soon as possible afterwards.

The ADR itself can be a useful way to summarise thoughts and come to an unbiased outcome.

Writing an ADR for a decision that has already been made will make it harder work to avoid pushing a reader towards a foregone conclusion.

Writing up what happened a long time after the decision has been made can lead to misremembered context. Actual consequences can be unconsciously written as predicted consequences, making the ADR seem prophetic and inaccurately portraying why a decision was made at the time.

### Enjoy! 😄
If ADRs feel like a chore, you could be doing it wrong. Start with a few bullet points; don't write an essay. Chip away at the superfluous and revel in radical candor. In a few months' time, you'll experience the joy of wondering why something is the way it is, and then finding a beautifully-written ADR that answers your question exactly.
