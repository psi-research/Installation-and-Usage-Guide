# Installation-and-Usage-Guide
## Installation and Usage Guide

### Prerequisites
- Docker

### Project Structure
- `autodrive-llm-finetune`: LLM fine-tuning
- `vllm-serving`: Model API serving using vLLM

1. LLM Fine-tuning Setup (autodrive-llm-finetune)

1.1 Docker Installation
1. Load the Docker image:
   ```bash
   docker load -i autodrive-ner-finetune-img.tar

2. Run the Docker container:
   ```bash
   ./docker_run.sh


1.2 Training Process
Step 0: Access Docker Container
Access the running Docker container:
```bash
docker exec -it autodrive-ner-finetune /bin/bash

Step 1: Navigate to Training Directory
Navigate to the training directory inside the container:
```bash
cd /autodrive

Step 2: Dataset Setup
1. Navigate to the datasets directory:
```bash
cd datasets

2. Add training data to final_trainset.jsonl in the following format:
```json
{
    "layer": 4,
    "input": "오후 3시경 스쿨존 내에서 청소년 운전자가 조작하던 오토바이가 과속으로 주행하다 보행 중이던 초등학생을 충격하는 사고가 발생하였습니다.",
    "output": "```json\n{\n    \"vehicle_type\": [\"오토바이\"]\n}\n```",
    "system": "You need to find and extract keywords corresponding to the following labels..."
}

3. Build the dataset:
```bash
python build_data.py


1.3 Model Training
1. Navigate to the training configuration directory:
```bash
cd /autodrive/train_config

2. Modify the yml file:
- Set the dataset path in datasets.path.
- Set the model save path in output_dir.

3. Start the training process:
```bash
./run.sh


1.4 Model Merging
1. Update the merge.sh script:
- Update the path for ./train_config/train_v1.yml.
- Set the correct --lora_model_dir path.

2. Execute the merge:
```bash
./merge.sh


2. Model Serving Setup (vllm-serving)
2.1 Docker Installation
1. Load the Docker image:
```bash
docker load -i vllm-serving-img.tar

2. Run the Docker container:
```bash
./docker_run.sh
