# Download HuggingFace Model with Command Line Interface (CLI)
[ref](https://huggingface.co/docs/huggingface_hub/main/guides/cli)
```bash
pip install -U "huggingface_hub[cli]"
```


## Login
First, create a token from [Hugging Face Settings](https://huggingface.co/settings/tokens) (Permission: write).  
```bash
huggingface-cli login
```
* Add token as git credential?  --> n  

---

If you encounter `huggingface-cli: command not found` : [ref](https://blog.csdn.net/weixin_40959890/article/details/129819257)  
```bash
echo "export PATH=\"`python3 -m site --user-base`/bin:\$PATH\"" >> ~/.bashrc
source ~/.bashrc
```
Then retry `huggingface-cli login`.  It should work now.  


## Download Model
### Download an entire repository
```bash
huggingface-cli download {repo ID} --local-dir {local path}
```
- Optional parameters:  
    `--include`:  e.g., `--include "*.json" "*.safetensors"`  
    `--exclude`:  e.g., `--exclude "*.bin"`  

### Download a single file
```bash
huggingface-cli download {repo ID} {file name} --local-dir {local path}
```

## Logout
```bash
huggingface-cli logout
```