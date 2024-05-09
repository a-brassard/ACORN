<img src="/readme/ACORN.png" alt="A cute illustration of an acorn character." width="50">

Home repository for the dataset introduced in [ACORN: Aspect-wise Commonsense Reasoning Explanation Evaluation](https://arxiv.org/abs/2405.04818).
ACORN contains 3,500 human-written and LLM-generated explanations with aspect-wise quality ratings given by humans. 

Also available on 🤗HuggingFace [here](https://huggingface.co/datasets/anab/ACORN)!

![Five human raters evaluating an explanation of the answer for a commonsense reasoning question. Ratings for 3500 explanations are aggregated into a dataset.](/readme/Illustration.png)


# Data
The entire dataset is contained in `ACORN.jsonl`. Each row consists of an explanation, related information, aggregated (majority-voted) ratings, and the full set of individual worker ratings. 

Basic fields:
- `question` question text
- `choices` list of answer choices
- `label` correct answer index
- `explanation` explanation text
- `supports`, `overall`, `well_written`, `related`, `factual`, `new_info`, `unnecessary_info`, `contrastive` majority-voted ratings
- `worker_ratings` all worker ratings, saved as a dictionary of dictionaries (worker id → rating dict).

→ See [Additional fields](#additional-fields) for the full list of fields.

# Quality aspects
Explanation quality is subjective and can depend on the intended use. Our choice includes both a *general* rating and *fine-grained* aspects of explanation quality assuming an ideal of **fluent**, **sufficient**, **minimal**, and **contrastive** explanations.


![Rating criteria](/readme/Rating_criteria.png)


# Sources
ACORN contains a blend of explanations from several sources. See Section 2.2 in the [paper](https://arxiv.org/abs/2405.04818) for a more detailed overview.

![ACORN contains samples from ECQA, CoS-E, COPA-SSE, generated explanations for Commonsense QA, generated explanations for Balanced COPA, newly collected explanations for Balanced COPA, and GPT-3.5 edited versions of CoS-E and COPA-SSE. Each group has 500 samples, totaling 3500 samples.](/readme/Data_sources.png)

<!-- 
# Stats

Extra stats about the dataset. e.g. Average rating per source?

-->

# Additional fields
In addition to the fields listed in [Files](#files), the dataset contains the following information.

- `id` test sample ID
- `q_id` original question ID
- `e_id` original explanation ID
- `q_source` question source (Commonsense QA or Balanced COPA)
- `e_source` explanation source (→ [Sources](#sources))
- `triples` triple-form explanation (COPA-SSE only)
- `postivies`, `negatives` positive and negative statements (ECQA only)

# Citation
If you use this dataset, please consider citing the following work.

```
TBD
```
<!-- 
@article{brassard2024acorn,
    title={ACORN: Aspect-wise Commonsense Reasoning Explanation Evaluation}, 
    author={Ana Brassard and Benjamin Heinzerling and Keito Kudo and Keisuke Sakaguchi and Kentaro Inui},
    year={2024},
    url={...}
}
-->
