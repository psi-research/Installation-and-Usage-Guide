# Installation-and-Usage-Guide
## Installation and Usage Guide

### Prerequisites
- Docker

### Project Structure
- `autodrive-llm-finetune`: LLM fine-tuning
- `vllm-serving`: Model API serving using vLLM

### 1. LLM Fine-tuning Setup (autodrive-llm-finetune)

#### 1.1 Docker Installation
```bash
# Load Docker image
docker load -i autodrive-ner-finetune-img.tar

# Run Docker container
./docker_run.sh

###1.2 Training Process

Access Docker container:
