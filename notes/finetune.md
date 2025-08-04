# Quantization types

Dynamic 2.0 GGUF and Dynamic 4-bit Safetensors are both quantization formats used to reduce the size and memory footprint of large language models, enabling them to run on consumer hardware. Dynamic 2.0 GGUF, specifically from Unsloth, prioritizes a balance between model accuracy and efficiency, offering a smaller disk size compared to older GGUF versions while maintaining high accuracy. On the other hand, Dynamic 4-bit quantization, often used with libraries like Bitsandbytes, aims to compress models further but can sometimes lead to accuracy degradation if not implemented carefully.


# Types of fine tuning
These terms describe different techniques used in machine learning, particularly with large language models (LLMs), to optimize performance, efficiency, and resource usage.

## Adapters (Parameter-Efficient Fine-Tuning - PEFT methods like LoRA):

    Concept: Instead of fine-tuning all parameters of a large pre-trained model, adapters introduce a small number of new, trainable parameters (the "adapter" modules) that are inserted into the model's architecture. Only these adapter parameters are updated during fine-tuning, while the original model weights remain frozen.

    Purpose: Significantly reduces the number of trainable parameters, leading to faster training, less memory usage, and easier storage and deployment of multiple fine-tuned versions of a single base model.

## Finetune (Full Fine-Tuning):

    Concept: Involves taking a pre-trained model and further training it on a specific dataset for a particular task. Unlike adapters, full fine-tuning updates all or a significant portion of the pre-trained model's parameters.

    Purpose: Adapts a general-purpose model to a specific domain or task, potentially achieving higher performance than adapter-based methods for that specific task, but at the cost of higher computational and memory requirements.

## Merge:

    Concept: Refers to combining the parameters of an adapter (e.g., LoRA weights) with the base model's parameters. This typically results in a single, consolidated model where the adapter's influence is integrated directly into the base model's weights.

    Purpose: Simplifies deployment by creating a single model file, potentially improving inference speed by eliminating the need for separate adapter computations during runtime. However, merging can sometimes lead to performance degradation, especially if the base model is quantized and the adapter is not.

## Quantization:

    Concept: Reduces the precision of a model's parameters (weights and/or activations) from higher-precision data types (e.g., 32-bit floating-point) to lower-precision data types (e.g., 8-bit integers or 4-bit integers). 

    Purpose: Decreases model size, reduces memory footprint, and potentially accelerates inference speed by allowing computations with lower-precision arithmetic. This often comes with a slight trade-off in model accuracy.