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

## Benchmark Infomation

### Construction Criteria

<div style="width: 80%; text-align: center; margin:auto;">
      <img style="width:80%" src="figs/DataVis.png">
</div>

**Reference Image：** The selection of references is based on three principles: (1) Diversity: The data must contain different subjects, backgrounds, styles, etc. (2) Reality: The images must come from natural scenes, such as UGC taken by average users. (3) Quality: As high-quality reference information, the images must not already be distorted.

**Distorted Image：** We considered 33 common corruption scenarios in the real world as dimensions for our benchmark. Into: (1) 7 steps from capturing to receiving. (2) 7 groups from low level vision. (3) 3 levels from corruption strength.

### Evaluate Criteria

Robustness can be categorized into absolute and relative aspects. **Absolute Robustness** refers to the performance that LMMs exhibit only on distorted images; while **Relative Robustness** is whether the outputs of LMMs are stable between reference/distorted images.

## Benchmark Result

<div style="width: 100%; text-align: center; margin:auto;">
      <img style="width:100%" src="figs/resultRadar.png">
</div>

GPT4o is fully superior to other models in each distortion step, with an overwhelming advantage in absolute robustness and a slight lead in relative robustness. The open-source LMMs InternLM-XComposer2 and InternVL2 perform relatively well and can surpass proprietary LMMs (except GPT4o) in some dimensions. Most LMMs score lower in the first two steps, and relatively higher in the last five.

| Absolute | MCQ low | MCQ mid | MCQ high | VQA low | VQA mid | VQA high | CAP low | CAP mid | CAP high | Overall |
|--------------------|---------|---------|----------|---------|---------|----------|---------|---------|----------|---------|
| GPT4o              | <span style="color: blue;">0.8176</span>  | <span style="color: blue;">0.7744</span>  | <span style="color: blue;">0.7391</span>  | <span style="color: blue;">0.7184</span>  | <span style="color: blue;">0.7291</span>  | <span style="color: blue;">0.6898</span>  | <span style="color: red;">0.4235</span>  | <span style="color: blue;">0.4200</span>  | <span style="color: blue;">0.3997</span>  | <span style="color: blue;">0.6348</span>  |
| GPT4Turbo         | 0.7059  | 0.6398  | 0.6220   | <span style="color: red;">0.7055</span>  | <span style="color: red;">0.7048</span>  | <span style="color: red;">0.6806</span>  | 0.3698  | 0.3811  | 0.3383   | <span style="color: red;">0.5722</span>  |
| GeminiPro         | <span style="color: red;">0.7529</span>  | 0.7012  | 0.6708   | 0.6233  | 0.6315  | 0.5796   | 0.4006  | <span style="color: red;">0.4040</span>  | 0.3734   | 0.5710  |
| InternX2          | 0.7176  | 0.6770  | 0.6220   | 0.6288  | 0.6255  | 0.6180   | 0.4204  | 0.3982  | 0.3659   | 0.5638  |
| InternVL2         | 0.7118  | <span style="color: red;">0.7019</span>  | 0.6280   | 0.6442  | 0.6436  | 0.6383   | 0.3759  | 0.3669  | 0.3412   | 0.5614  |
| GeminiFlash       | 0.7235  | 0.6708  | <span style="color: red;">0.7073</span>  | 0.5975  | 0.6036  | 0.5575   | 0.3840  | 0.3522  | 0.3487   | 0.5495  |
| LLaVANext         | 0.6529  | 0.6087  | 0.5732   | 0.6276  | 0.6382  | 0.6150   | 0.3957  | 0.4006  | 0.3873   | 0.5445  |
| MiniCPM           | 0.7081  | 0.6471  | 0.5610   | 0.5626  | 0.6024  | 0.5880   | 0.4025  | 0.4047  | <span style="color: red;">0.3885</span>  | 0.5405  |
| Qwen2-VL          | 0.6765  | 0.6708  | 0.5732   | 0.5914  | 0.6024  | 0.5335   | 0.4142  | 0.4127  | 0.3787   | 0.5393  |
| DeepseekVL        | 0.6149  | 0.5824  | 0.5244   | 0.6679  | 0.6227  | 0.6383   | 0.4167  | 0.4043  | 0.3741   | 0.5384  |
| MPlugOwl3         | 0.6706  | 0.6398  | 0.6159   | 0.5920  | 0.5715  | 0.5671   | 0.3728  | 0.3729  | 0.3729   | 0.5307  |
| ShareGPT4V        | 0.6273  | 0.5588  | 0.5488   | 0.6227  | 0.6145  | 0.6473   | 0.3716  | 0.3769  | 0.3390   | 0.5229  |
| Qwen1.5-VL        | 0.6087  | 0.5765  | 0.5000   | 0.6178  | 0.5642  | 0.5964   | 0.3895  | 0.3717  | 0.3502   | 0.5083  |
| LLaVAo            | 0.5353  | 0.5652  | 0.5305   | 0.5387  | 0.5255  | 0.5749   | <span style="color: blue;">0.4259</span>  | 0.3990  | 0.3809   | 0.4972  |
| Phi3.5            | 0.5765  | 0.5652  | 0.5244   | 0.5337  | 0.5679  | 0.5114   | 0.3660  | 0.3564  | 0.3342   | 0.4818  |
| Monkey            | 0.5471  | 0.5155  | 0.4451   | 0.5712  | 0.5648  | 0.5413   | 0.3833  | 0.3487  | 0.3573   | 0.4750  |
| LLaVA1.5          | 0.4706  | 0.4596  | 0.4695   | 0.6049  | 0.5679  | 0.6210   | 0.3457  | 0.3433  | 0.3476   | 0.4701  |
| MPlugOwl2         | 0.5647  | 0.5652  | 0.5000   | 0.5245  | 0.5255  | 0.5311   | 0.3364  | 0.3284  | 0.3043   | 0.4645  |
| InstructBLIP      | 0.4529  | 0.5280  | 0.4756   | 0.5534  | 0.5467  | 0.5653   | 0.3284  | 0.3414  | 0.3557   | 0.4606  |
| VisualGLM         | 0.4765  | 0.5217  | 0.5061   | 0.3994  | 0.3885  | 0.3623   | 0.3864  | 0.3571  | 0.3830   | 0.4198  |

| Relative | MCQ low | MCQ mid | MCQ high | VQA low | VQA mid | VQA high | CAP low | CAP mid | CAP high | Overall |
|--------------------|---------|---------|----------|---------|---------|----------|---------|---------|----------|---------|
| GPT4o              | <span style="color: blue;">0.7471</span>  | <span style="color: blue;">0.6894</span>  | <span style="color: blue;">0.6159</span>  | <span style="color: red;">0.5787</span>  | <span style="color: blue;">0.5725</span>  | <span style="color: blue;">0.5622</span>  | 0.2274  | 0.2134  | 0.2083   | <span style="color: blue;">0.4907</span>  |
| InternX2          | 0.6353  | 0.6087  | 0.5488   | 0.5038  | 0.5127  | 0.4639   | 0.2440  | 0.2317  | 0.2070   | <span style="color: red;">0.4396</span>  |
| MPlugOwl3         | 0.6087  | 0.5882  | 0.5488   | 0.5242  | 0.4877  | 0.4938   | 0.2423  | 0.2106  | <span style="color: red;">0.2205</span>  | 0.4359  |
| GPT4Turbo         | 0.5941  | 0.5590  | 0.4817   | <span style="color: blue;">0.5872</span>  | <span style="color: red;">0.5575</span>  | 0.5196  | 0.1972  | 0.1910  | 0.1836   | 0.4302  |
| DeepseekVL        | 0.5706  | 0.5342  | 0.4756   | 0.5384  | 0.5164  | 0.4934   | <span style="color: red;">0.2540</span>  | <span style="color: red;">0.2341</span>  | 0.2089   | 0.4251  |
| GeminiPro         | 0.6706  | 0.6211  | 0.5793   | 0.4640  | 0.4799  | 0.4510   | 0.1773  | 0.1874  | 0.1649   | 0.4219  |
| InternVL2         | 0.6294  | 0.6149  | 0.5427   | 0.4849  | 0.4850  | 0.4556   | 0.1940  | 0.1893  | 0.1698   | 0.4185  |
| LLaVANext         | 0.5882  | 0.5155  | 0.4817   | 0.5061  | 0.5065  | 0.4531   | 0.2310  | 0.2159  | 0.2161   | 0.4129  |
| Qwen2-VL          | <span style="color: red;">0.6706</span>  | <span style="color: red;">0.6522</span>  | 0.5244   | 0.4217  | 0.3926  | 0.3627   | 0.2210  | 0.2025  | 0.1957   | 0.4049  |
| GeminiFlash       | 0.6235  | 0.5714  | <span style="color: red;">0.6037</span>  | 0.4397  | 0.4719  | 0.4031   | 0.1681  | 0.1709  | 0.1654   | 0.4021  |
| ShareGPT4V        | 0.5528  | 0.4941  | 0.4573   | 0.5067  | 0.4897  | <span style="color: red;">0.5303</span>  | 0.2109  | 0.2032  | 0.1733   | 0.4019  |
| Monkey            | 0.4647  | 0.4534  | 0.3598   | 0.5036  | 0.4882  | 0.4546   | <span style="color: blue;">0.2828</span>  | <span style="color: blue;">0.2451</span>  | <span style="color: blue;">0.2379</span>  | 0.3877  |
| Qwen1.5-VL        | 0.5342  | 0.4941  | 0.4085   | 0.4712  | 0.4311  | 0.4637   | 0.2530  | 0.2152  | 0.2046   | 0.3860  |
| InstructBLIP      | 0.4529  | 0.4720  | 0.4451   | 0.4937  | 0.4615  | 0.4738   | 0.2343  | 0.2302  | 0.2061   | 0.3855  |
| LLaVAo            | 0.5059  | 0.5093  | 0.4817   | 0.4482  | 0.4224  | 0.4214   | 0.2078  | 0.2075  | 0.2012   | 0.3784  |
| Phi3.5            | 0.5176  | 0.4845  | 0.4695   | 0.4564  | 0.4891  | 0.3896   | 0.1915  | 0.1950  | 0.1825   | 0.3751  |
| MiniCPM           | 0.5176  | 0.5280  | 0.4512   | 0.3909  | 0.4233  | 0.4223   | 0.1967  | 0.1885  | 0.1955   | 0.3683  |
| LLaVA1.5          | 0.4412  | 0.3727  | 0.3720   | 0.5101  | 0.4558  | 0.5101   | 0.1955  | 0.1883  | 0.1850   | 0.3592  |
| MPlugOwl2         | 0.4529  | 0.4472  | 0.4146   | 0.3480  | 0.3659  | 0.3551   | 0.1676  | 0.1628  | 0.1507   | 0.3184  |
| VisualGLM         | 0.3765  | 0.4161  | 0.3841   | 0.2038  | 0.1990  | 0.1722   | 0.1951  | 0.1911  | 0.2071   | 0.2604  |

## How to use




<div align="left">
