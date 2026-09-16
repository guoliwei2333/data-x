# 克隆仓库

```bash
git config --global http.proxy http://127.0.0.1:7897          
git config --global https.proxy http://127.0.0.1:7897
git clone https://github.com/datawhalechina/easy-data-x-ai.git
cd easy-data-x-ai
```
<img width="2784" height="1892" alt="image" src="https://github.com/user-attachments/assets/eb3709da-3c87-424a-93a8-fc1b595af2aa" />

# 安装依赖
```bash
npm install
```
# 本地预览
```bash
npm run docs:dev
```
![[Pasted image 20260914230613.png]]

# 在仓库根目录创建 Python 3.11 虚拟环境
```bash
python3 -m venv .easy_data
source .easy_data/bin/activate
python -m pip install --upgrade pip
python -m pip install -r code/requirements-test.txt
python -m pip check
```
![[Pasted image 20260914232214.png]]
![[Pasted image 20260914232345.png]]
# 先跑不需要 API Key 和数据库的离线评测
```bash
PYTHONPATH=code/D3:code python code/D3/d3_5_evaluate.py
```
![[Pasted image 20260914233039.png]]
# 真实模型示例才需要复制并填写本地配置
```bash
cp code/.env.example code/.env
python code/D1/d1_1_base.py
```
![[Pasted image 20260914235814.png]]
