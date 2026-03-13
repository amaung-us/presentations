## Hugging Face (CLI)

[Back to index](README.md)

---

**Install CLI**
```bash
curl -LsSf https://hf.co/cli/install.sh | bash
```
**Login with Key**

insert key when asked
```bash
hf auth login
```

**Verify**
```bash
hf auth whoami
```

**download *model/repo* to a local directory**
```bash
hf download <repo_id> --local-dir <path_to_folder>
```


**In case all else fail**
```bash 
sudo apt update
sudo apt install -y python3-venv python3-pip

rm -rf /home/mladmin/.hf-cli

curl -LsSf https://hf.co/cli/install.sh | bash
```