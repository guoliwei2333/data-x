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
<img width="2786" height="1928" alt="image" src="https://github.com/user-attachments/assets/7c400670-90f2-4d61-b099-41fe396cb4a2" />


# 在仓库根目录创建 Python 3.11 虚拟环境
```bash
python3 -m venv .easy_data
source .easy_data/bin/activate
python -m pip install --upgrade pip
python -m pip install -r code/requirements-test.txt
python -m pip check
```
<img width="2012" height="838" alt="image" src="https://github.com/user-attachments/assets/e9b126e7-78d6-47a4-ac76-01957009b3d8" />
<img width="2002" height="832" alt="image" src="https://github.com/user-attachments/assets/21e67dce-f574-4d16-869d-5c7c5230a0f0" />

# 先跑不需要 API Key 和数据库的离线评测
```bash
PYTHONPATH=code/D3:code python code/D3/d3_5_evaluate.py
```
<img width="2780" height="1876" alt="image" src="https://github.com/user-attachments/assets/2b33bb7e-c3ac-4de3-9474-46e4e7780e04" />

# 真实模型示例才需要复制并填写本地配置
```bash
cp code/.env.example code/.env
python code/D1/d1_1_base.py
```
<img width="2006" height="340" alt="image" src="https://github.com/user-attachments/assets/796bc32b-18fd-4f5e-9f55-ad37714b77e5" />

