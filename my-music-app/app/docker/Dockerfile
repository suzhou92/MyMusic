FROM python:3.11-slim

WORKDIR /app

# 安装依赖
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 复制代码
COPY src/ ./app/

# 复制 APK 安装包（放在 src 同级目录）
COPY MyMusic.apk ./MyMusic.apk

# 复制微信二维码（技术支持）
COPY wechat_qr.jpg ./wechat_qr.jpg

# 端口
EXPOSE 5173

# 启动
CMD ["uvicorn", "app.main:app", "--host", "0.0.0.0", "--port", "5173"]
