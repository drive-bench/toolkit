<p align="right">English | <a href="./README_CN.md">简体中文</a></p>  


<p align="center">
  <h3 align="center">  
    <img src="docs/figs/icons/human.png" align="center" width="5%">
    <strong>Are VLMs Ready for Autonomous Driving?<br>An Empirical Study from the Reliability, Data, and Metric Perspectives</strong>
  </h3>

  <p align="center">
      <a href="https://daniel-xsy.github.io/" target='_blank'>Shaoyuan Xie</a><sup>1</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://ldkong.com/" target='_blank'>Lingdong Kong</a><sup>2,3</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://scholar.google.com/citations?user=kMui170AAAAJJ&hl=en" target='_blank'>Yuhao Dong</a><sup>2,4</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://scholar.google.com/citations?user=dgYJ6esAAAAJJ&hl=en" target='_blank'>Chonghao Sima</a><sup>2,6</sup>&nbsp;&nbsp;&nbsp;<br>
      <a href="https://scholar.google.com/citations?user=QDXADSEAAAAJJ&hl=en" target='_blank'>Wenwei Zhang</a><sup>2</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://ics.uci.edu/~alfchen/" target='_blank'>Qi Alfred Chen</a><sup>1</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://liuziwei7.github.io/" target='_blank'>Ziwei Liu</a><sup>4</sup>&nbsp;&nbsp;&nbsp;
      <a href="https://scholar.google.com/citations?user=lSDISOcAAAAJJ&hl=en" target='_blank'>Liang Pan</a><sup>2</sup>
    </br></br>
  <sup>1</sup>University of California, Irvine&nbsp;&nbsp;&nbsp;
  <sup>2</sup>Shanghai AI Laboratory&nbsp;&nbsp;&nbsp;
  <sup>3</sup>National University of Singapore&nbsp;&nbsp;&nbsp;
  <sup>4</sup>S-Lab, Nanyang Technological University&nbsp;&nbsp;&nbsp;
  <sup>5</sup>The University of Hong Kong
  </p>
</p>

<p align="center">
  <a href="" target='_blank'>
    <img src="https://img.shields.io/badge/Paper-%F0%9F%93%83-lightblue">
  </a>&nbsp;
  <a href="https://drive-bench.github.io/" target='_blank'>
    <img src="https://img.shields.io/badge/Project-%F0%9F%94%97-blue">
  </a>&nbsp;
  <a href="https://huggingface.co/datasets/drive-bench/arena" target='_blank'>
    <img src="https://img.shields.io/badge/Dataset-%F0%9F%8E%AC-pink">
  </a>&nbsp;
  <a >
    <img src="https://img.shields.io/badge/%E4%B8%AD%E8%AF%91%E7%89%88-%F0%9F%90%BC-red">
  </a>&nbsp;
  <a href="https://hits.seeyoufarm.com">
    <img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fdrive-bench%2Ftoolkit&count_bg=%2300B48B&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=Visitors&edge_flat=false"/>
  </a>
</p>


## About

| ![drivebench](./docs/figs/bench.png) |
|:-|
| - We introduce :blue_car: **DriveBench**, a benchmark dataset designed to evaluate VLM reliability across **17 settings** (clean, corrupted, and text-only inputs), encompassing **19,200 frames**, **20,498 question-answer pairs**, **three question types**, **four mainstream driving tasks**, and **a total of 12 popular VLMs**. 
| - Our findings reveal that VLMs often generate plausible responses derived from general knowledge or textual cues rather than true visual grounding, especially under degraded or missing visual inputs. This behavior, concealed by dataset imbalances and insufficient evaluation metrics, poses significant risks in safety-critical scenarios like autonomous driving. 
| - We further observe that VLMs struggle with multi-modal reasoning and display heightened sensitivity to input corruptions, leading to inconsistencies in performance. To address these challenges, we propose refined evaluation metrics that prioritize robust visual grounding and multi-modal understanding. Additionally, we highlight the potential of leveraging VLMs’ awareness of corruptions to enhance their reliability, offering a roadmap for developing more trustworthy and interpretable decision-making systems in real-world autonomous driving contexts. 



## :memo: Updates
- \[2025.01\] The evaluation data can be accessible at our [HuggingFace Dataset Card](https://huggingface.co/datasets/drive-bench/arena). :hugs:
- \[2025.01\] Introducing the :blue_car: **DriveBench** project! For more details, kindly refer to our [Project Page](https://drive-bench.github.io/) and [Preprint](). :rocket:


# Table of Content
- [Installation](#gear-installation)
- [Benchmark Comparison](#bar_chart-benchmark-comparison)
- [Data Preparation](#hotsprings-data-preparation)
- [Getting Started](#rocket-getting-started)
- [Benchmark Results](#aerial_tramway-benchmark-results)
- [Citation](#citation)
- [License](#license)
- [Acknowledgements](#acknowledgements)


## :gear: Installation

For details related to installation and environment setups, kindly refer to [INSTALL.md](./docs/INSTALL.md).


## :bar_chart: Benchmark Comparison

<table>
<thead>
<tr>
<th rowspan="2">Benchmark</th>
<th rowspan="2"><img src="./docs/figs/icons/perception.png" style="width: 40px; height: 40px; vertical-align: top;"><span>Perception</span></th>
<th rowspan="2"><img src="./docs/figs/icons/prediction.png" style="width: 40px; height: 40px; vertical-align: top;"><span>Prediction</span></th>
<th rowspan="2"><img src="./docs/figs/icons/behavior.png" style="width: 40px; height: 40px; vertical-align: top;"><span>Behavior</span></th>
<th rowspan="2"><img src="./docs/figs/icons/planning.png" style="width: 40px; height: 40px; vertical-align: top;"><span>Planning</span></th>
<th rowspan="2"><img src="./docs/figs/icons/robustness.png" style="width: 40px; height: 40px; vertical-align: top;"><span>Robustness</span></th>
<th>Frames</th>
<th>QA</th>
<th rowspan="2">Logic</th>
<th rowspan="2">Evaluation Metrics</th>
</tr>
<tr>
<th>(Test)</th>
<th>(Test)</th>
</tr>
</thead>
<tbody>
<tr>
<td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td>
</tr>
<tr>
<td>BDD-X</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>-</td>
<td>-</td>
<td>None</td>
<td>Language</td>
</tr>
<tr>
<td>BDD-OIA</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>-</td>
<td>-</td>
<td>None</td>
<td>F1 Score</td>
</tr>
<tr>
<td>nuScenes-QA</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>36,114</td>
<td>83,337</td>
<td>None</td>
<td>Acc</td>
</tr>
<tr>
<td>Talk2Car</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>~1.8k</td>
<td>2,447</td>
<td>None</td>
<td>-</td>
</tr>
<tr>
<td>nuPrompt</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>~36k</td>
<td>~6k</td>
<td>None</td>
<td>AMOTA</td>
</tr>
<tr>
<td>DRAMA</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>-</td>
<td>~14k</td>
<td>Chain</td>
<td>Language</td>
</tr>
<tr>
<td>Rank2Tel</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>-</td>
<td>-</td>
<td>Chain</td>
<td>Accuracy, Language</td>
</tr>
<tr>
<td>DirveMLLM</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>880</td>
<td>-</td>
<td>None</td>
<td>Acc</td>
</tr>
<tr>
<td>DriveVLM</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>-</td>
<td>-</td>
<td>None</td>
<td>GPT<sub>ctx</sub></td>
</tr>
<tr>
<td>DriveLM</td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(192, 0, 0);">✘</span></td>
<td>4,794</td>
<td>15,480</td>
<td>Graph</td>
<td>Language, GPT</td>
</tr>
<tr>
<td><strong><span style="font-family: 'Nunito', sans-serif; color: rgb(66, 133, 244);">Drive</span><span style="font-family: 'Nunito', sans-serif; color: rgb(192, 0, 0);">Bench</span> (Ours)</strong></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><span style="color: rgb(0, 176, 80);">✔</span></td>
<td><b>19,200</b></td>
<td><b>20,498</b></td>
<td><b>Graph</b></td>
<td><b>Acc, Language, GPT, GPT<sub>ctx</sub></b></td>
</tr>
</tbody>     
</table>


## :hotsprings: Data Preparation

Kindly refer to [DATA_PREPAER.md](./docs/DATA_PREPAER.md) for the details to prepare the datasets.



## :rocket: Getting Started

To learn more usage about this codebase, kindly refer to [GET_STARTED.md](./docs/GET_STARTED.md).



## :aerial_tramway: Benchmark Results

### Benchmark Configuration

<details open>
<summary>&nbsp<b>Vision-Language Model (VLMs)</b></summary>

> - [x] **[GPT4-o]()**
> - [x] **[LLaVA-1.5]()** <sup>[**`[Code]`**](https://github.com/xuanyuzhou98/SqueezeSegV2)</sup>
> - [x] **[LLaVA-NeXT]().** <sup>[**`[Code]`**](https://github.com/NVIDIA/MinkowskiEngine)</sup>

</details>


### Benchmark Study

<table>
<thead>
<tr>
<th>Model</th>
<th>Size</th>
<th>Type</th>
<th><img src="./docs/figs/icons/perception.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Perception</span> (<span style="color: rgb(0, 176, 80);">Clean</span>)</th>
<th><img src="./docs/figs/icons/perception.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Perception</span> (<span style="color: rgb(192, 0, 0);">Corr.</span>)</th>
<th><img src="./docs/figs/icons/perception.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Perception</span> (<span style="color: rgb(66, 133, 244);">T.O.</span>)</th>
<th><img src="./docs/figs/icons/prediction.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Prediction</span> (<span style="color: rgb(0, 176, 80);">Clean</span>)</th>
<th><img src="./docs/figs/icons/prediction.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Prediction</span> (<span style="color: rgb(192, 0, 0);">Corr.</span>)</th>
<th><img src="./docs/figs/icons/prediction.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Prediction</span> (<span style="color: rgb(66, 133, 244);">T.O.</span>)</th>
<th><img src="./docs/figs/icons/planning.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Planning</span> (<span style="color: rgb(0, 176, 80);">Clean</span>)</th>
<th><img src="./docs/figs/icons/planning.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Planning</span> (<span style="color: rgb(192, 0, 0);">Corr.</span>)</th>
<th><img src="./docs/figs/icons/planning.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Planning</span> (<span style="color: rgb(66, 133, 244);">T.O.</span>)</th>
<th><img src="./docs/figs/icons/behavior.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Behavior</span> (<span style="color: rgb(0, 176, 80);">Clean</span>)</th>
<th><img src="./docs/figs/icons/behavior.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Behavior</span> (<span style="color: rgb(192, 0, 0);">Corr.</span>)</th>
<th><img src="./docs/figs/icons/behavior.png" style="width: 37px; height: 37px; vertical-align: top;"><span>Behavior</span> (<span style="color: rgb(66, 133, 244);">T.O.</span>)</th>
</tr>
</thead>
<tbody>
<tr>
<td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td>
</tr>
<tr>
<td><span style="color: rgb(0, 176, 80);"><b>Human</b></span></td>
<td>-</td>
<td>-</td>
<td><span style="color: rgb(0, 176, 80);">47.67</span></td>
<td><span style="color: rgb(0, 176, 80);">38.32</span></td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td>-</td>
<td><span style="color: rgb(0, 176, 80);">69.51</span></td>
<td><span style="color: rgb(0, 176, 80);">54.09</span></td>
<td>-</td>
</tr>
<tr>
<td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td>
</tr>
<tr>
<td><a>GPT-4o</a></td>
<td>-</td>
<td>Commercial</td>
<td>35.37</td>
<td>35.25</td>
<td>36.48</td>
<td>51.30</td>
<td>49.94</td>
<td>49.05</td>
<td>75.75</td>
<td>75.36</td>
<td>73.21</td>
<td>45.40</td>
<td>44.33</td>
<td>50.03</td>
</tr>
<tr>
<td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td>
</tr>
<tr>
<td><a>LLaVA-1.5</a></td>
<td>7B</td>
<td>Open</td>
<td>23.22</td>
<td>22.95</td>
<td>22.31</td>
<td>22.02</td>
<td>17.54</td>
<td>14.64</td>
<td>29.15</td>
<td>31.51</td>
<td>32.45</td>
<td>13.60</td>
<td>13.62</td>
<td>14.91</td>
</tr>
<tr>
<td><a>LLaVA-1.5</a></td>
<td>13B</td>
<td>Open</td>
<td>23.35</td>
<td>23.37</td>
<td>22.37</td>
<td>36.98</td>
<td>37.78</td>
<td>23.98</td>
<td>34.26</td>
<td>34.99</td>
<td>38.85</td>
<td>32.99</td>
<td>32.43</td>
<td>32.79</td>
</tr>
<tr>
<td><a>LLaVA-NeXT</a></td>
<td>7B</td>
<td>Open</td>
<td>24.15</td>
<td>19.62</td>
<td>13.86</td>
<td>35.07</td>
<td>35.89</td>
<td>28.36</td>
<td>45.27</td>
<td>44.36</td>
<td>27.58</td>
<td>48.16</td>
<td>39.44</td>
<td>11.92</td>
</tr>
<tr>
<td><a>InternVL2</a></td>
<td>8B</td>
<td>Open</td>
<td>32.36</td>
<td>32.68</td>
<td>33.60</td>
<td>45.52</td>
<td>37.93</td>
<td>48.89</td>
<td>53.27</td>
<td>55.25</td>
<td>34.56</td>
<td>54.58</td>
<td>40.78</td>
<td>20.14</td>
</tr>
<tr>
<td><a>Phi-3</a></td>
<td>4.2B</td>
<td>Open</td>
<td>22.88</td>
<td>23.93</td>
<td>28.26</td>
<td>40.11</td>
<td>37.27</td>
<td>22.61</td>
<td>60.03</td>
<td>61.31</td>
<td>46.88</td>
<td>45.20</td>
<td>44.57</td>
<td>28.22</td>
</tr>
<tr>
<td><a>Phi-3.5</a></td>
<td>4.2B</td>
<td>Open</td>
<td>27.52</td>
<td>27.51</td>
<td>28.26</td>
<td>45.13</td>
<td>38.21</td>
<td>4.92</td>
<td>31.91</td>
<td>28.36</td>
<td>46.30</td>
<td>37.89</td>
<td>49.13</td>
<td>39.16</td>
</tr>
<tr>
<td><a>Oryx</a></td>
<td>7B</td>
<td>Open</td>
<td>17.02</td>
<td>15.97</td>
<td>18.47</td>
<td>48.13</td>
<td>46.63</td>
<td>12.77</td>
<td>53.57</td>
<td>55.76</td>
<td>48.26</td>
<td>33.92</td>
<td>33.81</td>
<td>23.94</td>
</tr>
<tr>
<td><a>Qwen2-VL</a></td>
<td>7B</td>
<td>Open</td>
<td>28.99</td>
<td>27.85</td>
<td>35.16</td>
<td>37.89</td>
<td>39.55</td>
<td>37.77</td>
<td>57.04</td>
<td>54.78</td>
<td>41.66</td>
<td>49.07</td>
<td>47.68</td>
<td>54.48</td>
</tr>
<tr>
<td><a>Qwen2-VL</a></td>
<td>72B</td>
<td>Open</td>
<td>30.13</td>
<td>26.92</td>
<td>17.70</td>
<td>49.35</td>
<td>43.49</td>
<td>5.57</td>
<td>61.30</td>
<td>63.07</td>
<td>53.35</td>
<td>51.26</td>
<td>49.78</td>
<td>39.46</td>
</tr>
<tr>
<td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td><td></td>
</tr>
<tr>
<td><a>DriveLM</a></td>
<td>7B</td>
<td>Specialist</td>
<td>16.85</td>
<td>16.00</td>
<td>8.75</td>
<td>44.33</td>
<td>39.71</td>
<td>4.70</td>
<td>68.71</td>
<td>67.60</td>
<td>65.24</td>
<td>42.78</td>
<td>40.37</td>
<td>27.83</td>
</tr>
<tr>
<td><a>Dolphins</a></td>
<td>7B</td>
<td>Specialist</td>
<td>9.59</td>
<td>10.84</td>
<td>11.01</td>
<td>32.66</td>
<td>29.88</td>
<td>39.98</td>
<td>52.91</td>
<td>53.77</td>
<td>60.98</td>
<td>8.81</td>
<td>8.25</td>
<td>11.92</td>
</tr>
</tbody>
</table>
          


## Citation
If you find this work helpful, please kindly consider citing our paper:
```bibtex
@article{xie2025drivebench,
  author  = {Xie, Shaoyuan and Kong, Lingdong and Dong, Yuhao and Sima, Chonghao and Zhang, Wenwei and Chen, Qi Alfred and Liu, Ziwei and Pan, Liang},
  title   = {Are VLMs Ready for Autonomous Driving? An Empirical Study from the Reliability, Data, and Metric Perspectives},
  journal = {arXiv preprint arXiv:2501.},
  year    = {2025},
}
```


## License

This work is under the [Apache License Version 2.0](https://www.apache.org/licenses/LICENSE-2.0), while some specific implementations in this codebase might be with other licenses. Kindly refer to [LICENSE.md]() for a more careful check, if you are using our code for commercial matters.


## Acknowledgements

To be updated.


