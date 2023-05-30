# TQP : An Efficient Video Quality Assessment Framework for Adaptive Bitrate Video Streaming
The study is focused on video quality assessment for adaptive bitrate videos commonly used in video streaming applications. The contribution of the study lies in an efficient architecture which can capture both spatial and temporal characeristics of a video stream. The proposed architecture has used Efficientnet with channel shifting to perform spatiotemporal learning with reduced computational complexity. A quality aware loss function is proposed for training the model for better predictive performance.
## Datasets used For Experiments
The study is based on streaming quality of experience datasets with adaptive bitrate. Two such datasets are used for model building and evaluation which are described further.
### LIVE-NFLX-II Subjective Video QoE Database
 The database includes 420 videos that were evaluated by 65 subjects which led into 9750 continuous-time and 9750 retrospective subjective opinion scores. Continuous-time scores capture the instantaneous Quality of Experience (QoE), while retrospective scores reflect the overall viewing experience. These videos were generated from 15 video contents streamed under 7 different network conditions and 4 client adaptation strategies. These 7 network conditions are actual network traces from the HSDPA dataset representing challenging 3G mobile networks. The 4 client adaptation strategies cover the most representative client adaptation algorithms, such as rate-based, buffer-based and quality-based. The selected video contents cover a diverse set of content genres (action, documentary, sports, animation and video games). The content characteristics span a large variety including natural and animation video content, fast/slow motion scenes, light/dark scenes and low and high texture scenes. 
![Depiction of Some Videos in the dataset](https://github.com/nisarahmedrana/TQP/blob/main/Live.JPG)
The dataset can be downloaded from the below link: 
[LIVE-NFLX-II Database](https://live.ece.utexas.edu/research/LIVE_NFLX_II/live_nflx_plus.html)
### The Waterloo Streaming Quality-of-Experience Database-III
The Waterloo Streaming Quality-of-Experience Database-III consists of 20 RAW HD reference videos and 450 simulated streaming videos, and of an average duration of 13 seconds. In order to generate meaningful and representative test videos, we conducted a set of DASH video streaming experiments, recorded the relevant streaming activities, and reconstructed the streaming session using video processing tools. The streaming sessions generated by 6 adaptive streaming algorithms including rate-based, BBA, AIMD, Elastic, QDASH, and FESTIVE under 13 wide-ranging bandwidth conditions are recorded and evaluated by 34 subjects. Subjects score the quality of each video sequence according to the 0-100 numerical quality scale.
![Depiction of Some Videos in the dataset](https://github.com/nisarahmedrana/TQP/blob/main/Waterloo.jpg)
The dataset can be downloaded from the below link: 
[Waterloo Streaming Quality-of-Experience Database-III](https://ieee-dataport.org/open-access/waterloo-streaming-quality-experience-database-iii)
## Synopsis of Research
The increasing popularity of video streaming services, facilitated by high-speed Internet, highlights the importance of providing affordable and seamless streaming experiences. However, shared Internet connections among users can lead to unpredictable speeds and negatively impact the Quality of Experience (QoE). To ensure smooth video transmission, rate adaptation techniques are employed by content delivery systems, however, overly optimistic rate adaptation may excessively reduce video stream size, hampering user experience. Objective video quality assessment plays a crucial role in estimating QoE and enabling efficient rate adaptation. In this study, we propose a method that introduce temporal channel shifting in Convolutional Neural Networks (CNN) and use them for video quality assessment with complexity of a 2D CNN model. Our approach make use of Efficientnet architecture which is pretrained on quality aware images and finetuned to datasets of rate adaptive videos. Two benchmarking datasets, namely "Waterloo sQoE III" and "LIVE Netflix II," containing rate-adaptive videos and annotated with subjective quality scores are used for model training and evaluation.  Experimental results include Pearson, Spearman, and Kendall's correlation coefficients and computational efficiency. The proposed approach has provided competitive scores of 0.795, 0.652, 0.772 and 0.216 for Live Netflix II dataset and 0.782, 0.713, 0.721 and 0.230 for Waterloo sQoE III dataset. Compared to 24 existing approaches, our proposed approach demonstrates the highest correlation score while maintaining near-real-time processing efficiency. These findings validate the effectiveness of our method in accurately predicting human judgment (QoE) while ensuring computational efficiency.
The overall framework of the proposed approach is provided below:
![Framework of the proposed approach](https://github.com/nisarahmedrana/TQP/blob/main/TQP.jpg)
### Comparison of Experimental Results
| Sr.  | Approach | SROCC | KROCC | PLCC | Time|
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
|1 | Yin2015 | 0.146 | 0.093 | 0.323 | 0.007 |
|2 | SQI | 0.152 0.110 0.223 0.500
|3 | MoK2012 | 0.169 | 0.129 | 0.216 | 0.001 |
|4 | FTW  | 0.184 | 0.134 | 0.323 | 0.001 |
|5 | Bentaleb20l6 | 0.198 | 0.139 | 0.341 | 0.500 |
|6 | Liu2012  | 0.253 | 0.172 | 0.242 | 0.001 |
|7 | Xue2014  | 0.341 | 0.225 | 0.308 | 0.003 |
|8 | VIIDEO | 0.395 | 0.265 | 0.490 | 8.050 |
|9 | NIQE |  0.402 | 0.273 | 0.449 | 1.030 |
|10 | PIQE  | 0.423 | 0.281 | 0.435 | 1.130 |
|11 | BRISQUE  | 0.496 | 0.347 | 0.469 | 1.940 |
|12 | TV-QoE  | 0.507 | 0.357 | 0.467 | 0.520 |
|13 | KSQI |  0.529 | 0.388 | 0.527 | 0.510 |
|14 | ResNet50  | 0.571 | 0.411 | 0.564 | 0.380 |
|15 | UGC-VQA  | 0.590 | 0.424 | 0.646 | 1.450 |
|16 | PIQI  | 0.495 | 0.365 | 0.590 | 0.920 |
|17 | VIDEVAL  | 0.686 | 0.465 | 0.652 | 0.730 |
|18 | DeepEns  | 0.696 | 0.547 | 0.669 | 0.620 |
|19 | VSFA  | 0.704 | 0.489 | 0.669 | 1.210 |
|20 | TLVQM  | 0.726 | 0.493 | 0.689 | 1.100 |
|21 | V-BLIINDS  | 0.739 | 0.546 | 0.724 | 45.63 |
|22 | FAST-VQA | 0.739 | 0.550 | 0.771 | 0.330 |
|23 | PVQ  | 0.749 | 0.551 | 0.727 | 2.070 |
|24 | StarVQA | 0.757 | 0.536 | 0.706 | 4.100 |
|25 | TQP | (Proposed) | 0.782 | 0.713 | 0.721 | 0.230 |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
