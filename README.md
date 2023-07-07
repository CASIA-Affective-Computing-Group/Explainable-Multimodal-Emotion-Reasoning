# Explainable Multimodal Emotion Reasoning

Correspondence to: 
  - Zheng Lian (lianzheng2016@ia.ac.cn)



## Paper

[**Explainable Multimodal Emotion Reasoning**](https://arxiv.org/pdf/2306.15401.pdf)<br>
Zheng Lian, Licai Sun, Mingyu Xu, Haiyang Sun, Ke Xu, Zhuofan Wen, Shun Chen, Bin Liu, Jianhua Tao<br>
Arxiv, 2023

Please cite our paper if you find our work useful for your research:

```tex
@article{lian2023explainable,
  title={Explainable Multimodal Emotion Reasoning},
  author={Lian, Zheng and Sun, Licai and Xu, Mingyu and Sun, Haiyang and Xu, Ke and Wen, Zhuofan and Chen, Shun and Liu, Bin and Tao, Jianhua},
  journal={arXiv preprint arXiv:2306.15401},
  year={2023}
}
```



Meanwhile, samples are randomly selected from MER 2023. 

```tex
@article{lian2023mer,
  title={MER 2023: Multi-label Learning, Modality Robustness, and Semi-Supervised Learning},
  author={Lian, Zheng and Sun, Haiyang and Sun, Licai and Zhao, Jinming and Liu, Ye and Liu, Bin and Yi, Jiangyan and Wang, Meng and Cambria, Erik and Zhao, Guoying and others},
  journal={arXiv preprint arXiv:2304.08981},
  year={2023}
}
```



## Dataset

```
# info.csv: contains five columns: names, chiemos, engemos, chisubs, engsubs
names: video name
chiemos: emotion label (in Chinese) in MER 2023 dataset
engemos: emotion label (in English) in MER 2023 dataset
chisubs: subtitle (in Chinese)
engsubs: subtitle (in English)

# gt.csv: manually annotated explanation
names: video name
chi_reasons: reasoning process (in Chinese). We do not provide English version. You can generate such info via translation function in ChatGPT or other toolkits.
```



## Baselines

[**PandaGPT**](https://github.com/yxuansu/PandaGPT)

[**Valley**](https://github.com/RupertLuo/Valley)

[**VideoChat**](https://github.com/OpenGVLab/Ask-Anything)

[**Video-ChatGPT**](https://github.com/mbzuai-oryx/Video-ChatGPT)

[**Video-LLaMA**](https://github.com/DAMO-NLP-SG/Video-LLaMA)



Prediction results of different baselines:

```
# files
pandagpt.csv: prediction results of PandaGPT
valley.csv: prediction results of Valley
videochat(emb).csv: prediction results of VideoChat-Embed
videochat(text).csv: prediction results of VideoChat-Text
videochatgpt.csv: prediction results of Video-ChatGPT
videollama.csv: prediction results of Video-LLaMA

# columns:
names: video name
chi_reasons: reasoning process (in Chinese). We do not provide English version. You can generate such info via translation function in ChatGPT or other toolkits.
```



## Evaluation

We provide ChatGPT-based evaluation approaches. See eval_release.py for more details.

**Please ensure you have an OpenAI key and can access to ChatGPT.**

```
# evaluate for full datasets
python eval_release.py --data_root=[your data root] --openai_key=[your openai key]

# only run the code for debug
python eval_release.py --data_root=[your data root] --openai_key=[your openai key] --debug
```



