# Scratch-AID+ supplementary materials

These materials accompany the manuscript's Methods and Results. All metrics
describe the recorded experiments; no new training or test evaluation was run
to construct these tables.

| Material | Content | Download |
| --- | --- | --- |
| [Table S1](table_s1.md) | Accuracy and scratching-class F1 for all seven models, two protocols and six preprocessing configurations; configuration means corresponding to manuscript Table II | [Detailed CSV](table_s1.csv), [mean CSV](table_s1_configuration_means.csv) |
| [Implementation details](implementation_details.md) | Per-model input, training, checkpoint selection and ICL settings moved from the manuscript's implementation notes | Markdown |
| [Table S2](table_s2.md) | Curated-to-Realistic checkpoint transfer for VideoSwin and InternVideo-Next, with matched Realistic-trained comparisons | [CSV](table_s2.csv) |

Table S1 contains all **336 accuracy and F1 values** across 84 model, protocol
and preprocessing combinations. The supplied benchmark summary completes
Scratch-AID, CNNTransformer and VideoMAE. Higher-precision stored records
provide the other models. All 28 F1 configuration means reconcile with the
manuscript at the reported precision. Table S1 documents the one discrepancy
between the summary workbook and the archived VideoSwin accuracy record.

Trainable models use full test sets. Frozen MLLMs use four-shot ICL on three
repeated balanced subsamples per configuration. Their mean ± sample SD describes
the stored repeat estimates, not biological confidence intervals. Results from
these evaluation scopes should be compared with the differences in sample
membership and scratching prevalence in mind.

**Naming:** Realistic corresponds to legacy Sequential/`seq` source labels;
Curated corresponds to Primary/`primary`. `CNNTransformer` is the center-frame
model called ResNet-transformer in the manuscript's overview and result tables.

[Back to repository overview](../README.md).
