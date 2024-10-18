# Destination Repo with Jupyter Notebooks

This repo represents a destination for copying Jupyter Notebooks used as
companions for the [MongoDB Vector Search documentation](https://www.mongodb.com/docs/atlas/atlas-vector-search/vector-search-overview/).

The source repo is at: https://github.com/dacharyc/notebook-source

## Why a separate repo?

This destination repository represents _only_ the Jupyter Notebooks from the
source repository. The source repository will contain additional code examples
and infrastructure to run GitHub workflows, test suites, etc. That infrastructure
may be confusing to developers who just want to see the notebooks.

We can easily automate copying the source files that are relevant to a given
developer audience to the appropriate destination. In this proof-of-concept,
the source files live in a `notebooks` directory in the `notebook-source` repo.
The files in that directory are copied to the root of this repository, so you
see the structure here that is more intuitive for developers to parse:

```
├── create-embeddings
│   ├── ...notebooks
├── integrations
│   ├── ...notebooks
├── manage-indexes
│   ├── ...notebooks
├── rag
│   ├── ...notebooks
├── run-queries
│   ├── ...notebooks
├── quick-start.ipynb
└── README.md
```

Any source files that are _outside_ of the `notebooks` directory in the
`notebook-source` repository are _not_ copied to this destination repository.

## Workflow

Any updates to the Jupyter Notebooks in this repository would occur in the
`notebooks-source` repository. A GitHub workflow in that repository automatically
copies updated files over to this repository in the appropriate directory structure.
This lets us single-source _all_ of our code examples from the source repository,
while showing only the relevant (but always up-to-date and maintained) example
code in the destination repository.
