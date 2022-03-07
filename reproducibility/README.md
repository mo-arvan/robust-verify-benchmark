```bash
export PROJECT_NAME=robust-verify-benchmark

docker build -t ${PROJECT_NAME}_image -f reproducibility/dockerfile .


docker run --rm --ipc=host --gpus all -v ${PWD}:/workspace -it ${PROJECT_NAME}_image bash

# inside the container


# Download the dataset, instructions are included in the main readme file.

python main.py --model ADV_MLP_B_0.03 --epsilon 0.03 --lp-greedy
```

