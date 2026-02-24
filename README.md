## User Prompting Strategies and Prompt Enhancement Methods for Open-Set Object Detection in XR Environments Dataset
This repository accompanies the workshop paper [_"User Prompting Strategies and Prompt Enhancement Methods for Open-Set Object Detection in XR Environments"_](https://arxiv.org/abs/2601.23281), published in GenAI-XR 2026. It introduces a curated dataset of 264 real-world augmented reality(AR) images with manually labeled annotated bounding boxes. These images were selected from the DiverseAR and DiverseAR+ dataset, which consist of AR images captured via AR headsets and Android devices in various real world in door environments such as offices, study spaces, living rooms and bedrooms.

### 1. Motivation and Collection Process
To evaluate prompt-conditioned robustness in realistic XR settings, we curated a dataset specifically designed to capture the variability of user interactions. The dataset consists of 264 real-world augmented reality (AR) images selected from the DiverseAR and DiverseAR+ collections. These images were captured using AR headsets and Android devices across a variety of indoor environments, including offices, study spaces, living rooms, and bedrooms. The dataset reflects practical XR usage challenges such as cluttered backgrounds, viewpoint variations, and occlusion from virtual overlays. For each image, we manually designated target objects and annotated them with bounding boxes to serve as the ground truth for evaluating detection accuracy.

### 2. Evaluation Methods & Prompt Enchancement Strategies
We established a comprehensive pipeline to measure prompt-conditioned robustness, the stability of Open-Set Object Detection (OSOD) models when the visual scene is fixed but the linguistic input varies. \
Models Evaluated: We tested two state-of-the-art OSOD systems: GroundingDINO (GD) and YOLO-E. \
Prompt Simulation: To mimic realistic user behavior at scale, we used a Vision-Language Model (VLM), specifically GPT-5, to generate four distinct types of prompts:
* Underdetailed: Short or incomplete inputs
* Standard: Well-formed, explicit descriptions
* Overdetailed: Excessive visual attributes that can introduce redundant constraints
* Pragmatically Ambiguous: Indirect, intent-driven instructions that lack explicit visual descriptors
\
### 3. Evaluation Metrics
* Mean Intersection over Union (mIoU): To measure localization quality.
* Confidence Scores: To measure prediction reliability.

### 4. Hierarchical Structure of the Datasets
```text
Evaluation.dataset.coco/
├── README.dataset.txt
├── README.roboflow.txt
└── train/
    ├── images/
    │   ├── ar_img_001.jpg
    │   ├── ar_img_002.jpg
    │   └── ...
    └── _annotations.coco.json
```
### 5. Dataset Download
* The full OSOD-XR dataset can be downloaded here: [https://huggingface.co/datasets/Linjfeng/OSOD-XR-Dataset/tree/main](url)
### 6. Citation
If you use the OSOD-XR dataset in an academic work, please cite: 
```text
@misc{lin2026userpromptingstrategiesprompt,
      title={User Prompting Strategies and Prompt Enhancement Methods for Open-Set Object Detection in XR Environments}, 
      author={Junfeng Lin and Yanming Xiu and Maria Gorlatova},
      year={2026},
      eprint={2601.23281},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2601.23281}, 
}
```
### 7. Acknowledgements
The authors of this repository are Junfeng Lin, Yanming Xiu and Maria Gorlatova. Contact information of the authors:
* Junfeng Lin (junfeng.lin AT duke.edu)
* Yanming Xiu (yanming.xiu AT duke.edu)
* Maria Gorlatova (maria.gorlatova AT duke.edu)

\
This work was supported in part by NSF grants CSR-2312760, CNS2112562, and IIS-2231975, NSF CAREER Award IIS-2046072,
NSF NAIAD Award 2332744, a Cisco Research Award, a Meta Research Award, Defense Advanced Research Projects Agency Young
Faculty Award HR0011-24-1-0001, and the Army Research Laboratory under Cooperative Agreement Number W911NF-23-2-0224. The views and conclusions contained in this document are those of the authors and should not be interpreted as representing the official policies, either expressed or implied, of the Defense Advanced Research Projects Agency, the Army Research Laboratory, or the U.S.Government. This paper has been approved for public release; distribution is unlimited. No official endorsement should be inferred. The U.S. Government is authorized to reproduce and distribute reprints for Government purposes notwithstanding any copyright notation herein.
