# PicoClaw

```
pkg update && pkg upgrade -y
pkg install proot-distro -y
proot-distro install ubuntu
proot-distro login ubuntu
```



```
apt update && apt upgrade -y
apt install wget tar nano ca-certificates -y
```
```
wget https://github.com/sipeed/picoclaw/releases/download/v0.2.2/picoclaw_Linux_arm64.tar.gz

tar -xzvf picoclaw_Linux_arm64.tar.gz

chmod +x picoclaw
mv picoclaw /usr/local/bin/
```

```

mkdir -p ~/.picoclaw
```
```
cat <<EOF > ~/.picoclaw/config.json
{
  "agents": {
    "defaults": {
      "workspace": "/root/.picoclaw/workspace",
      "model": "my-local-model"
    }
  },
  "model_list": [
    {
      "model_name": "my-local-model",
      "model": "ollama/kimi-k2.5:cloud", 
      "api_base": "http://127.0.0.1:11434/v1",
      "api_key": "ollama"
    }
  ],
  "channels": {
    "telegram": {
      "enabled": true,
      "token": "YOUR_TELEGRAM_TOKEN_HERE",
      "allow_from": [TELEGRAM_ID_HERE]
    }
  }
}
EOF
```
```
picoclaw gateway
```
