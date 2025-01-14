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
