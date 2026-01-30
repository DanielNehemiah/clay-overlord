# sample server running gpt-oss-20b at http://127.0.0.1:8033

llama-server -hf ggml-org/gpt-oss-20b-GGUF --jinja -c 0 --host 127.0.0.1 --port 8033

# Running llama cli for Ministral-3-Instruct-2512
llama-cli -hf unsloth/Ministral-3-14B-Instruct-2512-GGUF:Q4_K_XL --jinja -ngl 99 --threads -1 --ctx-size 32684 --temp 0.15


# Running llama server for Ministral-3-Instruct-2512

llama-server -hf unsloth/Ministral-3-14B-Instruct-2512-GGUF:Q4_K_XL --jinja -ngl 99 --threads -1 --ctx-size 32684 --temp 0.15 -c 0 --host 127.0.0.1 --port 8033

llama-server -hf unsloth/Ministral-3-14B-Instruct-2512-GGUF:Q4_K_XL --jinja -ngl 99 --threads -1 --ctx-size 32684 --temp 0.15 -c 0 --host 0.0.0.0 --port 8033