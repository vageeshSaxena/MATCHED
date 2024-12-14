# MATCHED: Multimodal Authorship-Attribution To Combat Human Trafficking in Escort-Advertisement Data

**Abstract:** Human trafficking (HT) remains a critical issue, with traffickers exploiting digital platforms to advertise victims anonymously. Current detection methods, including Authorship Attribution (AA), focus on textual data but overlook the multimodal nature of online ads, which often pair text with images. This research introduces MATCHED, a multimodal dataset comprising 27,619 unique text descriptions and 55,115 unique images from seven U.S. cities across four geographical regions. Our study extensively benchmarks text-only, vision-only, and multimodal baselines for vendor identification and verification tasks, employing multitask training objectives that achieve superior performance on in-distribution and out-of-distribution datasets. This dual-objective approach enables law enforcement agencies (LEAs) to identify known vendors while linking emerging ones. Integrating multimodal features further enhances performance, capturing complementary patterns across text and images. While text remains the dominant modality, visual data adds stylistic cues that enrich model performance. Moreover, text-image alignment strategies like CLIP and BLIP2 struggle due to low semantic overlap and ineffective use of stylistic cues, with end-to-end multimodal training proving more robust. Our findings emphasize the potential of multimodal AA to combat HT, providing LEAs with robust tools to link ads and dismantle trafficking networks.

# IDTraffickers Dataset (will be made accessible through the Dataverse Portal)
The MATCHED dataset is a novel, multimodal collection of escort advertisements designed for Authorship Attribution (AA) tasks. It comprises 27,619 unique text descriptions and 55,115 associated images, sourced from the Backpage platform across seven U.S. cities and categorized into four geographical regions. The dataset spans December 2015 to April 2016, offering a rich blend of textual and visual data for vendor identification and verification tasks. To protect individual identities, all personally identifiable information has been meticulously removed using advanced masking techniques. While the raw dataset remains securely stored, only metadata is available on Dataverse. Interested parties can access the complete dataset under strict ethical guidelines by signing a Non-Disclosure Agreement (NDA) and Data Transfer Agreement with us.

<p align="center">
  <img src="/Images/Dataset.png" alt="Dataset" style="width:50%; max-width:500px;">
</p>

# Setup
This repository is tested on Python 3.10 and [conda](https://docs.conda.io/projects/miniconda/en/latest/). First, you should install a virtual environment:
```
conda create -n MATCHED python=3.10
```

To activate the conda environment, run:
```
conda activate MATCHED
```

Then, you can install all dependencies:
```
pip install -r requirements.txt
```

Additionally, to perform the authorship verification task, please install the FAISS package as suggested [here](https://github.com/facebookresearch/faiss/blob/main/INSTALL.md)

# Experiments

Our research establishes benchmarks for authorship identification by experimenting with various baselines across text-only, vision-only, and multimodal settings. Specifically, we utilize the DeCLUTR-small model as the backbone for text-only experiments and the ViT-base-patch16-224 model for vision-only experiments. We combine the DeCLUTR-small and ViT-base-patch16-224 models for our multimodal backbone through mean pooling to effectively capture textual and visual features. The performance results of all our authorship identification baselines are presented below.

<p align="center">
  <img src="/Images/classification.png" alt="Classification" style="width:55%; max-width:700px;">
</p>
