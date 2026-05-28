# InteractBind

InteractBind is a physically grounded protein-ligand interaction dataset for
interpretable and interaction-aware binding prediction.

The dataset is hosted on Hugging Face:
[Zhaohan-Meng/InteractBind](https://huggingface.co/datasets/Zhaohan-Meng/InteractBind).
This GitHub repository provides the project landing page, links, usage notes,
and future code/resources associated with the dataset.

## Overview

InteractBind is constructed from experimentally resolved protein-ligand
complexes and includes:

- Protein sequences in FASTA and structure-aware sequence formats
- Ligand representations in SMILES and SELFIES
- Binding labels and binding affinity annotations
- Token-level non-covalent interaction maps

The benchmark supports binding prediction, binding affinity prediction,
binding-site localisation, interaction-aware representation learning, and
explainable molecular modelling.

## Dataset Access

Install the Hugging Face datasets package:

```bash
pip install datasets
```

Load the main affinity split:

```python
from datasets import load_dataset

dataset = load_dataset("Zhaohan-Meng/InteractBind", "affinity")
print(dataset)
```

Protein out-of-distribution benchmark subsets are also available:

```python
from datasets import load_dataset

p_ood_25 = load_dataset("Zhaohan-Meng/InteractBind", "p_ood_25")
p_ood_28 = load_dataset("Zhaohan-Meng/InteractBind", "p_ood_28")
p_ood_31 = load_dataset("Zhaohan-Meng/InteractBind", "p_ood_31")
p_ood_33 = load_dataset("Zhaohan-Meng/InteractBind", "p_ood_33")
```

## Interaction Annotations

Each CSV includes residue-level binding-site fingerprint columns derived from
interaction maps:

- `Hydrogen bonding_binding_site`
- `Salt Bridges_binding_site`
- `π–π Stacking_binding_site`
- `Cation–π_binding_site`
- `Hydrophobic_binding_site`
- `Van der Waals_binding_site`
- `Overall_binding_site`

Each value is a binary list aligned to the protein FASTA sequence. For example,
`[0,0,1,0]` marks the third residue as a binding-site residue.

## Links

- Hugging Face dataset:
  [Zhaohan-Meng/InteractBind](https://huggingface.co/datasets/Zhaohan-Meng/InteractBind)
- Related demo:
  [Zhaohan-Meng/ExplainBind](https://huggingface.co/spaces/Zhaohan-Meng/ExplainBind)

## License

The Hugging Face dataset is released under the
[CC BY 4.0 license](https://creativecommons.org/licenses/by/4.0/).
