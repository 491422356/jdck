狗东账密登录必备文件,文件源自网络,与本人无任何关系
sudo docker run -it \
  -p 12345:12345 \
  -w /etc/app \
  --name taozizhangmi \
  --restart unless-stopped \
  python:3.12 bash -c "
    apt -y update && \
    apt -y install libnss3 libnspr4 libatk1.0-0 libatk-bridge2.0-0 libcups2 libdrm2 libdbus-1-3 libxkbcommon0 libxcomposite1 libxdamage1 libxfixes3 libxrandr2 libgbm1 libasound2 libatspi2.0-0 libxshmfence1 && \
    pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple && \
    python -m pip install --upgrade pip && \
    pip install pyppeteer Pillow asyncio aiohttp opencv-python-headless ddddocr quart && \
    wget https://raw.githubusercontent.com/peach028/jdck/main/api.py -O /etc/app/api.py && \
    wget https://raw.githubusercontent.com/peach028/jdck/main/login.py && \
    python /etc/app/api.py"
