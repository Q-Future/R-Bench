<div align="center">
    
    
 <div>
  <a href="https://github.com/lcysyzxdxc/"><img src="https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2FQ-Future%2FR-Bench&count_bg=%23E97EBA&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=visitors&edge_flat=false"/></a>
  <a href="https://github.com/Q-Future/R-Bench"><img src="https://img.shields.io/github/stars/lcysyzxdxc/R-Bench"/></a>
  <a href="https://huggingface.co/datasets/lcysyzxdxc/R-Bench"><img src="https://img.shields.io/badge/Data-Release-green"></a>
 </div>

 <h1>R-Bench: Are your Large Multimodal Model Robust to Real-world Corruption?</h1>

 _a benchmark focused on the Real-world Robustness of LMMs_

 <div>
      <a href="https://lcysyzxdxc.github.io" target="_blank">Chunyi Li</a><sup>1</sup>,
      Jianbo Zhang<sup>1</sup>,
      <a href="https://zzc-1998.github.io/" target="_blank">Zicheng Zhang</a><sup>1</sup>,
      <a href="https://teowu.github.io/" target="_blank">Haoning Wu</a><sup>2</sup>,
      <a href="https://scholar.google.com/citations?user=Kzd0qtsAAAAJ&hl/" target="_blank">Yuan Tian</a><sup>1</sup>,
      <a href="https://scholar.google.com/citations?user=nDlEBJ8AAAAJ&hl/" target="_blank">Wei Sun</a><sup>1</sup>,
 </div>

 <div>
      <a href="https://guolusjtu.github.io/guoluhomepage/" target="_blank">Guo Lu</a><sup>1</sup>,
      <a href="https://jhc.sjtu.edu.cn/~xiaohongliu/" target="_blank">Xiaohong Liu</a><sup>1</sup>,
      <a href="https://minxiongkuo.github.io/" target="_blank">Xiongkuo Min</a><sup>1</sup>,
      <a href="https://personal.ntu.edu.sg/wslin/Home.html" target="_blank">Weisi Lin</a><sup>3</sup>,
      <a href="https://ee.sjtu.edu.cn/en/FacultyDetail.aspx?id=24&infoid=153&flag=153" target="_blank">Guangtao Zhai</a><sup>1</sup>
 </div>
 <div>
  <sup>1</sup>Shanghai Jiaotong University,  <sup>2</sup>01 AI,  <sup>3</sup>Nanyang Technological University
 </div> 
 <a href="https://github.com/Q-Future/R-Bench/blob/main/R_Bench_Preview.pdf"><strong>Paper</strong></a> |
 <a href="https://github.com/Q-Future/R-Bench"><strong>Project Page</strong></a> |
 <a href="https://huggingface.co/datasets/lcysyzxdxc/R-Bench"><strong>Data</strong></a> 
</div>

<div style="width: 100%; text-align: center; margin:auto;">
      <img style="width:100%" src="figs/spotlight.png">
</div>

**Why are LMMs excellent in benchmarks but limited in the real-world?**** Robustness is a crucial factor. In experiments, LMMs usually receive high-quality images, but in real-world scenarios that includes numerous corruption, such as object motion, lens blur, etc. If the robustness issue of LMMs can be solved, it may become as widly-used as single modality LLM, thus will bring tenfold convenience to daily human life. Therefore, we have established **R-Bench** to evaluate the robustness of LMMs in the real-world. R-Bench aims to test the resistance of different LMMs to corruptions and to identify the most significant corruptions affecting LMMs' performance, thereby pointing out optimization directions for future LMMs and helping them adapt to real-world images.

## Release
<!-- - [2024/10/10] 🔥 Release the [technical report](https://www.arxiv.org/abs/2410.00000) for **R-Bench**.  -->
<!-- - [2024/10/9] 🔥 Add support for [OpenCompass](https://github.com/open-compass/VLMEvalKit). Test your LMM robustness on MCQ task with one command. -->
- [2024/10/9] 🔥 [Github repo](https://github.com/Q-Future/R-Bench) for **R-Bench** is online!! [Dataset Download](https://huggingface.co/datasets/lcysyzxdxc/R-Bench)

## Construction

<div style="width: 80%; text-align: center; margin:auto;">
      <img style="width:100%" src="figs/DataVis.png">
</div>

**Reference Image：** To comprehensively characterize image data from the real world, we collect high-quality reference data and then add corruption to obtain distorted images. The selection of references is based on three principles: (1) Diversity: The data must contain different subjects, backgrounds, styles, etc. (2) Reality: The images must come from natural scenes, such as UGC taken by average users. (3) Quality: As high-quality reference information, the images must not already be distorted.

**Distorted Image：** We considered **33 common corruption** scenarios in the real world as dimensions for our benchmark. Into:
(1) 7 steps from capturing to receiving: Environment Interference (EI), Camera Interference (CI), Analog-to-Digital (AD), Source Encoding (SE), Channel Transmission (CT), Receiver Decoding (RD), and Enhancement Postprocess (EP). (2) 7 groups from low level vision: Blur, Luminance, Chrominance, Spatial, Noise, Compression, and the in-the-wild corruption. (3) 3 levels from corruption strength: low, mid, high.


<div align="left">
