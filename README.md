# 🧠 Ritual Node VPS Setup Guide (Beginner-Friendly)

> A simple, step-by-step guide to run the **Ritual Infernet Node** on a VPS (Linux Ubuntu).  
> This guide is designed for **newcomers with zero technical knowledge** — just copy and paste!

---

## ✅ Requirements

| Item              | Description                                                         |
|-------------------|---------------------------------------------------------------------|
| VPS               | Minimum: 4 vCPU, 16GB RAM, 100+ GB SSD (Ubuntu 20.04 or 22.04)      |
| SSH Client        | For accessing your VPS (PuTTY for Windows, Terminal for Mac/Linux)  |

---

## 🖥 Recommended VPS Providers

| Provider   | Recommended Plan         | Link                        |
|------------|--------------------------|-----------------------------|
| Contabo    | VPS S (16 GB RAM)        | https://contabo.com         |
| Hetzner    | CPX21 or higher          | https://hetzner.com         |
| Vultr      | High Performance Plan    | https://www.vultr.com       |

---

## 🔐 Step 1: Connect to Your VPS

### 🪟 Windows Users
1. Download & install **[PuTTY](https://www.putty.org/)**.
2. Enter your VPS IP in "Host Name".
3. Login with:
   - Username: `root`
   - Password: (Paste by right-clicking)

### 🍎 Mac/Linux Users
Open your Terminal and connect:
```bash
ssh root@YOUR_VPS_IP
```
> Replace `YOUR_VPS_IP` with the IP address given by your VPS provider.

---

## ⚙️ Step 2: Install and Run Ritual Node

After logging into your VPS, copy and paste each command one-by-one:

### ✅ 1. Update your server
```bash
apt update && apt upgrade -y
```

### ✅ 2. Install required packages
```bash
apt install -y curl git screen docker.io docker-compose
```

### ✅ 3. Start Docker and enable it on boot
```bash
systemctl start docker
systemctl enable docker
```

### ✅ 4. Clone the official Ritual node repository
```bash
git clone https://github.com/ritualnetwork/infernet-container-starter.git
cd infernet-container-starter
```

### ✅ 5. Run the node using Docker
```bash
docker-compose -f deploy/docker-compose.yaml up -d
```

🎉 That's it! Your Ritual Node is now running in the background.

---

## 🧪 Step 3: Verify Node Is Running

Check running containers:
```bash
docker ps
```

View live logs:
```bash
docker logs infernet-node -f
```

---

## 🛑 Bonus Commands

Stop the node:
```bash
docker-compose -f deploy/docker-compose.yaml down
```

Restart the node:
```bash
docker-compose -f deploy/docker-compose.yaml up -d
```

---

## 🔗 Useful Links

- 🔧 [Official Node Repo](https://github.com/ritualnetwork/infernet-container-starter)
- 📖 [Node Docs](https://ritual.academy/nodes/setup/)
- 💬 [Ritual Discord](https://discord.gg/ritual)

---

## 🙋 Need Help?

If you’re stuck, ask for help in the [Ritual Discord](https://discord.gg/ritual).

---

## 📢 Disclaimer

> This guide is for educational purposes only. Guide By ZK (Zeeshan Khan)
