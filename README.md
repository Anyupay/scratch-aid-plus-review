# Scratch-AID+: Core Models and ICL Prompts

Minimal code companion for **Scratch-AID+: Cross-Laboratory Evaluation of
Supervised and Foundation Models for Mouse Scratching Detection**.

Each model has its own folder. The binary label convention is
`0 = nonscratching`, `1 = scratching`.

| Folder | Included content |
| --- | --- |
| [scratchaid_crnn](scratchaid_crnn/) | Original ResNet18 encoder and recurrent decoder |
| [resnet_transformer](resnet_transformer/) | CNNTransformer: ResNet18 with center-frame temporal readout |
| [internvideo_next](internvideo_next/) | Base classifier, attentive probe and LoRA implementation |
| [video_swin](video_swin/) | Standalone Swin-B model configuration for MMAction2 |
| [videomae](videomae/) | VideoMAE classifier core and ViT-B/16 / ViT-L/16 factories |
| [gemini](gemini/) | Gemini 3.1 Flash-Lite prompts and retrieval/request settings |
| [qwen3_vl](qwen3_vl/) | Exact zero-, two- and four-shot prompts and source settings |

## Scope and use

This repository contains core model definitions and ICL prompts. Data,
preprocessing, training and evaluation pipelines, checkpoints, logs and generated
results are outside its scope. Follow each folder's README for its input
contract, dependencies and a model-construction example. Use separate
environments where model dependencies differ. ICL prompt files can be read
without installing a model runtime.

Model construction initializes a network; it does not reproduce paper scores.
Task checkpoints and their matching settings are necessary for evaluation.
Model-specific architectures and input contracts are documented in each folder.

## Adding or updating a model

Keep one folder per model, containing only its core implementation or prompts,
minimal dependencies and a short README. Preserve the source computations and
prompt wording. Avoid author names, institutional paths, private repository
links, credentials, datasets and generated outputs. Retain applicable upstream
licenses and attribution. Optional supplementary methods/results should be
anonymous and clearly identify their evaluation protocol.

## Third-party components

Model backbones are supplied by their upstream libraries or pretrained model
repositories, under their respective licenses. See the model folders for the
relevant references. No new blanket license is assigned to the project code in
this initial review snapshot.
