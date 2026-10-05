# Simulation Lab 2: inference

Second simulation lab for **PSYC 201A** (UC San Diego), accompanying the
inference chapter of [Experimentology](https://experimentology.io/). You will
simulate a two-condition experiment many times over and use the simulations to
see what *p*-values, null distributions, and confidence intervals actually are.
When you are done you will have:

- Written a function that simulates one experiment, then run it 1,000 times
- Seen how sample size changes the spread of the estimated effect
- Built a null distribution two ways: simulating no effect, and shuffling labels
- Computed a permutation *p*-value and a confidence interval by hand
- Measured the false-positive rate when the null is true, and how often a real
  effect is missed

The running example is the "lady tasting tea": do people rate tea differently
when the milk goes in first?

> **Before you start:** finish
> [getting-started-with-r](https://github.com/psyc-201/getting-started-with-r)
> and [Data Simulation Lab 1](https://github.com/psyc-201/data_simulation_lab_1).
> This lab needs only the tidyverse, nothing else.

---

## Part 1. Make your own copy

Same steps as in getting-started-with-r:

1. At the top of [this repository's GitHub page](https://github.com/psyc-201/inference_simulations_lab_2),
   click the green **Use this template** button, then **Create a new repository**.
2. Owner: **your own account**. Name it `inference_simulations_lab_2`, leave
   it **Public**, and click **Create repository**.
3. On *your* copy, click **Code** → **Open with GitHub Desktop** → **Clone**.

Step-by-step version:
[github-desktop.md](https://github.com/psyc-201/getting-started-with-r/blob/main/docs/github-desktop.md).

## Part 2. Open the project

**Double-click `inference_simulations_lab_2.Rproj`** to open RStudio inside
the project, then open `ch6_tea_simulations.qmd` from the Files pane and put
your name in the `author:` line.

## Part 3. Work through the lab

Run one chunk at a time with the green arrow, top to bottom. Later chunks use
objects that you create earlier (`tea_data_highn`, `samps_highn`,
`null_model`), so if you skip one, the chunks after it fail.

| Part | What you do |
|---|---|
| 1. Simulating experimental data | Simulate one experiment at n = 18 and n = 48, run t-tests, then simulate 1,000 of each and plot the estimated effects |
| 2. Simulating the null distribution | Build the null distribution by simulating δ = 0, then by shuffling condition labels; compute a permutation *p*-value |
| 3. Confidence intervals | Compute a CI by hand, check it against `t.test()`, and plot CIs vs. standard errors |
| 4. *p*-values across experiments | Run a t-test on each of the 1,000 simulated experiments, with and without a true effect |

The lab marks two places to stop for group discussion. Parts 3 and 4 are
there for those who get further. Not finishing them in class is expected.

`error: true` is set at the top of the file, so **Render works even while
chunks are unfinished**: the unfinished chunks show their error in red.

`ch6_tea_simulations_solutions.qmd` is the answer key. Try each part first.

## Part 4. Commit, push, and submit

Commit as you go. When you are finished, render once more, commit with a
message like `Finish inference lab`, **Push origin**, and submit the link to
your repository however your instructor asks. Rendered `.html` files are
ignored by git, so only your `.qmd` is pushed.

## What is in this repository

```
inference_simulations_lab_2/
├── inference_simulations_lab_2.Rproj   open this to start work
├── ch6_tea_simulations.qmd             the lab
└── ch6_tea_simulations_solutions.qmd   answer key
```

## Stuck?

1. **Setup errors** (package not found, RStudio not in the project): see
   [troubleshooting.md](https://github.com/psyc-201/getting-started-with-r/blob/main/docs/troubleshooting.md).
2. **`object 'tea_data_highn' not found`** (or `samps_highn`, `null_model`):
   the lab asks you to create that object in an earlier chunk. Find the To do
   and write it, then rerun from there.
3. **Your numbers differ from the solutions:** expected, unless you render from
   scratch. Every rerun of a chunk draws new random numbers.
4. **The 1,000-experiment loops in Part 4 take a while**, usually a few
   seconds and up to a minute on older laptops. Let them finish.
5. Still stuck? Post the **exact** error message in the course forum.
