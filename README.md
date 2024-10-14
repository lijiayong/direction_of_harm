# Can AI detect the direction of harm?
### Building a model for message moderation on social media platforms

[Google's Jigsaw team](https://current.withgoogle.com/the-current/toxicity/) has worked on online harassment, and [Meta](https://about.fb.com/news/2024/09/preventing-suicide-and-self-harm-content-spreading-online/) has worked on suicide prevention. These two problems actually exist in the same problem space: harassment is harm directed from the user to others, and suicide ideation is harm directed from the user to themself. Only the direction is different. By expanding on this idea of the direction of harm, there are four cases: self harm, harming others, harmed by others, and reference of harm. By reference of harm I mean harm directed from others to others. Here are some example texts, all written from a first person perspective.

| | self_harm | harming_others | harmed_by_others | reference_to_harm |
| --- | --- | --- | --- | --- |
| I'm trash | 1 | 0 | 0 | 0 |
| John is trash | 0 | 1 | 0 | 0 |
| Mary told me I'm trash | 0 | 0 | 1 | 0 |
| Adam told Jane she's trash | 0 | 0 | 0 | 1 |

Once we have these labels, what can I do with them? From a moderation point of view, these four labels warrant distinct follow-up responses.

| | self_harm | harming_others | harmed_by_others | reference_to_harm |
| --- | --- | --- | --- | --- |
| response to author | suicide helpline | warning/block message | bully/abuse helpline | |
| response to others | trigger warning | prompt user to report | trigger warning | trigger warning |

I documented my process of building this model in the [blog post](https://lijiayong.github.io/posts/direction_of_harm/), and I uploaded the data as a [Kaggle data set](https://www.kaggle.com/datasets/jiayongli/direction-of-harm-detection).
