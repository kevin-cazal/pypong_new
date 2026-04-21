# Using this repository as a GitHub template

`README.md` is **generated from `metadata.yaml`** (see CI). For **template** usage (creating new workshop repos), follow the steps below.

## Create a new workshop repository

1. On GitHub, open this template under **Manta-Epitech-Academy**.
2. Click **Use this template** → **Create a new repository**.
3. Clone your new repo and add or replace `.md` files; edit **`metadata.yaml`** (`project`, `runtime`, **`documents`**).
4. Install tooling and refresh generated files from the workshop root:
  ```bash
   git clone https://github.com/Manta-Epitech-Academy/workshop-metadata-tools.git
   pip install -r workshop-metadata-tools/requirements.txt
   export PYTHONPATH="$PWD/workshop-metadata-tools"
   python workshop-metadata-tools/sync_metadata_toc.py
   python workshop-metadata-tools/generate_readme.py
   python workshop-metadata-tools/check_toc.py
  ```
5. Commit **`metadata.yaml`**, **`README.md`**, and your `.md` sources, then push.

## Enable this repo as a template (maintainers)

```bash
gh repo edit Manta-Epitech-Academy/<repo-name> --template
```

## Layout


| File                                     | Role                                                                                                                           |
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| `metadata.yaml`                          | Source of truth; drives `README.md` and `toc` (JSON Schema is in **workshop-metadata-tools**, see `$schema` in the first line) |
| `README.md`                              | Generated — do not edit by hand                                                                                                |
| `.github/workflows/verify-metadata.yaml` | Calls **workshop-metadata-tools** CI                                                                                           |


Conceptual docs and diagrams: [**workshop-metadata-tools** `docs/STRUCTURE.md`](https://github.com/Manta-Epitech-Academy/workshop-metadata-tools/blob/main/docs/STRUCTURE.md).

## Quizzes in Markdown (optional)

Quizzes live in your workshop `.md` files. They **do not** appear in `metadata.yaml` or the generated `toc` (headings inside quiz blocks are ignored for the outline).

Full specification: [**docs/QUIZ.md**](https://github.com/Manta-Epitech-Academy/workshop-metadata-tools/blob/main/docs/QUIZ.md).

Extract JSON with:

```bash
python workshop-metadata-tools/parse_quiz.py WORKSHOP.md
```

### Examples (four types)

**Single answer** — list with `-` and `A.`, `B.`, …

> QUIZ.A1.1 La question
> Quelle est la réponse ?

- A. 10
- B. 42
- C. -8

**Multiple answers** — list with `*` and `A.`, `B.`, …

> QUIZ.A2.2 Une autre question
> Quelles sont les réponses à l'autre question ?

* A. 30+12
* B. 0x2a
* C. 84 / 2
* D. 67

**Match** — `-` with uppercase letters, then `-` with lowercase letters (pair `A` with `a`, etc.)

> QUIZ.B1.3 Encore une autre question
> Fait correspondre les différents éléments

- A. Gnou
- B. Manchot
- C. Démon
- a. FreeBSD
- b. Linux
- c. GNU

**Free form** — a **single** list row: `- [prompt]:` (the prompt can be any text inside the brackets)

> QUIZ.B1.4 La dernière question
> Quel est le nom du créateur et développeur principal de Linux ?

- [Ta réponse / your answer]:

### After the quiz examples

This paragraph is normal Markdown. Correct-answer markup will be defined in a later version of the spec.

