# Project Name

> one-line description of the project.

## 📌 Overview
(프로젝트의 배경, 목적, 핵심 기능을 간략히 설명합니다.)

## 🛠️ Environment Setup
이 프로젝트는 **Conda** 환경과 **Hydra** 설정을 사용합니다.

```bash
# 1. Create Environment
conda create -n my_env python=3.9
conda activate my_env

# 2. Install Dependencies
pip install -r requirements.txt
```

## 🚀 Usage

### Running the App
Config는 `conf/config.yaml`에서 관리됩니다. (Hydra)

```bash
python src/main.py mode=train dataset=cifar10
```

## 📂 Project Structure
```
.
├── conf/               # Hydra Configurations
├── docs/               # Detailed Documentation
├── src/                # Source Code (Modular)
│   ├── core/
│   └── utils/
├── tests/              # Unit Tests
└── README.md
```
