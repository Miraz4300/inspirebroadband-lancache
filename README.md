# Inspire Broadband Unbound Local DNS

This repository contains Unbound DNS configuration files for **Inspire Broadband Internet**. It maps game and service domains to a local caching server (`10.100.100.10`) to optimize downloads and reduce latency.

## Features
- **Gaming Platforms**: PlayStation, Xbox, Steam, Blizzard, Nintendo, Epic Games, Riot, etc.
- **Game Updates**: Faster patches for Warframe, TESO, Wargaming.net, and others.
- **Windows & Microsoft Updates**: Redirects Windows Update traffic for optimized downloads.

## Setup Instructions

### 1️⃣ Install Unbound (if not already installed)
```bash
sudo apt update && sudo apt install unbound -y
```

### 2️⃣ Clone this repository
```bash
git clone https://github.com/Miraz4300/inspirebroadband-lancache.git
cd inspirebroadband-lancache
```

### 3️⃣ Copy the configuration files
```bash
sudo cp local-dns.conf /etc/unbound/unbound.conf.d/
```

### 4️⃣ Restart Unbound
```bash
sudo systemctl restart unbound
```

### 5️⃣ Verify DNS Resolution
Run the following to check if domains resolve to `10.100.100.10`:
```bash
dig gs2.ww.prod.dl.playstation.net @127.0.0.1 -p 5335
```

## Notes
- This configuration is **only applicable for Inspire Broadband Internet**.
- Ensure that Unbound is properly integrated with **Pi-hole** if you're using it as a recursive resolver.

## Contributing
Feel free to fork, modify, and submit pull requests to improve the configurations.
