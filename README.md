# DiabeTrack:A health app that keeps track of your diabetic measurements


[**Website/Glosses**]( ) |
[**Paper**]( ) |
[**Slides**]() |




# Introduction

DiabeTrack is a health app designed to keep track of diabetic measurements. This platform allows diabetic patients to enter their readings, enabling doctors to access their data and communicate in real-time.


# The Tasks

*   Primary tasks:
    *   **Data Entry and Storage:** Patients can enter their diabetic measurements through an intuitive interface.
Data is securely stored and accessible by authorized healthcare providers.
    *   **Real-Time Data Access:** Doctors can access patient data in real-time, providing timely feedback and adjustments to treatment plans.
*   Secondary task:
    *   **Communication** Real-time messaging between patients and doctors ensures continuous care and prompt responses to any concerns.

# Download the Dataset

Once you've chosen which task to work on (above), you can download the data at
the following URLs.



# Building a Baseline System


# Evaluation

## Primary Task Evaluation

The predictions can be evaluated using a command like the following:

```
python3 tydi_eval.py \
  --gold_path=tydiqa-v1.0-dev.jsonl.gz \
  --predictions_path=your_model_predictions.jsonl
```

This script computes language-wise F1 scores and then averages over languages,
excluding English. Spans are compared based on predicted byte positions and
partial credit is assigned within spans based on F1 positional overlap. See the
description of evaluation in the TACL article for details.

Please see the [evaluation script](tydi_eval.py) for a description of the
prediction format that your model should output.

## Gold Passage Task Evaluation

For the gold passage task, we re-use the existing SQuAD 1.1 evaluation code to
allow maximal re-use of existing pipelines. An example of calling the code for
evaluation is in
[gold_passage_baseline/eval_gold_passage_baseline.sh](gold_passage_baseline/eval_gold_passage_baseline.sh).

```
cd gold_passage_baseline
vim eval_gold_passage_baseline.sh  # Edit path to `TYDIQA_GOLDP_DIR`
./eval_gold_passage_baseline.sh predictions.jsonl /tmp
```

Note that for dev and test evaluation, each language is evaluated separately and
the overall score is the average over languages, excluding English.

# Leaderboard Submissions

In addition to reporting results on the dev set in your own research articles,
we also encourage you to submit to our
[public leaderboard](https://ai.google.com/research/tydiqa), to create a record
of your experiments. We believe leaderboard submissions serve two main purposes:

(a) to create an existence proof that such a result is **possible** under
carefully isolated conditions (i.e. cheating, intentional or accidental is
difficult) so that the community knows such a score is possible; and (b) to
inform the community **how** the result was obtained. Toward this latter goal,
we request that you submit a description (e.g. paper draft) of your submission
and also answer a few "repoducibility questions" that let the community know if
it will be possible to reproduce and build on your result. These include:

1.  Is there a research paper describing the system you are submitting? (The
    community benefits far more from knowing how to achieve a result than the
    fact that it exists.)
2.  Is the source code for the system you are submitting publicly available?
    (Your results will be replicated and trusted more if the community can
    quickly and reliably reproduce your results).
3.  Was the system you are submitting trained on any additional public data?
4.  Was the system you are submitting trained on any NON-public data? (The
    community cannot reproduce results on non-public data.)
5.  Was the system you are submitting trained with, or does it use, any external
    APIs, data labelers, or data transformations (e.g. a translation API)? (The
    use of public APIs is not reproducible and creates a black box effect since
    the community does not know the details of the underlying model and data it
    was built on.)

For step-by-step instructions on submitting, see
[leaderboard.md](leaderboard.md).

In addition to submitting to the leaderboard we encourage you to make both your
source code and your Docker images public so that others can easily run
inference with your system. This opens up the possibility of others (such as
MT-focused researchers) building on top of (and citing!) your QA system.

# Analyze Your Results

We encourage those working with the data to not only report numeric results, but
also analyze the results at a linguistic level. Consider partnering with
linguists and/or native speakers of these languages to create glosses that
explain how your model is interacting with language. See the TACL article for
examples of glossed examples with explanations (Figures 2 - 7).

# Source Data

DiabeTrack utilizes a secure and robust database to store patient information. All data is encrypted and adheres to HIPAA regulations to ensure patient privacy and security.


# Citation

Please cite DiabeTrack as follows:

```
@article{diabetrack,
title   = {DiabeTrack: A Health App for Tracking Diabetic Measurements},
author  = {Nelius and Keith },
year    = {2024},
journal = {Journal of Health Informatics}
}

```

# Contact us
DiabeTrack aims to empower diabetic patients by providing a comprehensive platform for managing their health. By enabling real-time data entry, access, and communication, DiabeTrack bridges the gap between patients and healthcare providers, fostering a collaborative approach to diabetes management.
