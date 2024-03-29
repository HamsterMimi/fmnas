# New Indicators and Optimizations for Zero-Shot NAS Based on Feature Maps

## Prepare

### 1. Installation

```
python >= 3.6
pytorch == 1.8.0
torchvision == 0.9.0
tesnsorboard == 2.4.1
scipy == 1.5.2
gpustat
```
### 2. Install `zero-cost-nas`

```bash
cd zero-cost-nas
pip install .
cd ..
```

## Usage/Examples

### NAS-Bench-201 Spaces

**Step-1.** Download three datasets (CIFAR-10, CIFAR-100, ImageNet16-120) from [Google Drive](https://drive.google.com/drive/folders/1T3UIyZXUhMmIuJLOBMIYKAsJknAtrrO4) and benchmark files of NAS-Bench-201 from [Google Drive](https://drive.google.com/file/d/1SKW0Cu0u8-gb18zDpaAGi0f74UdXeGKs/view) , then place them into the directory `./data`, one can see [nas-bench-201](https://pypi.org/project/nas-bench-201/) for more detail.

**Step-2. ** Install NAS-Bench-201 api:

```bash
pip install nas-bench-201
```

**Step-3.** Run Zero-Cost-PT with appointed zero-cost proxy:

```bash
cd exp_scripts
bash zerocostpt_nb201_pipline.sh --metric [metric] --batch_size [batch_size] --seed [seed]
```

You can choice metric from `['snip', 'fisher', 'synflow', 'grad_norm', 'grasp', 'jacob_cov','tenas', 'var', 'cor', 'norm', 'comb'] `

### DARTS-like Spaces

#### 1. DARTS CNN Space

```bash
cd exp_scripts
bash zerocostpt_darts_pipline.sh --metric [metric] --batch_size [batch_size] --seed [seed]
```

#### 2. DARTS Subspaces S1-S4

````bash
cd exp_scripts
bash zerocostpt_darts_pipline.sh --metric [metric] --batch_size [batch_size] --seed [seed] --space [s1-s4]
````

## Reference

Our code is based on [Zero-Cost-PT](https://github.com/zerocostptnas/zerocost_operation_score) and [Zero-Cost-NAS](https://github.com/SamsungLabs/zero-cost-nas).





