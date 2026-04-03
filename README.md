# 🚀 Grafana + Prometheus Setup on Ubuntu

A beginner-friendly step-by-step guide to install and configure **Grafana + Prometheus** on Ubuntu for monitoring and visualization.

---

## 📌 Overview

This project helps you set up a complete **monitoring stack**:

* 📊 **Grafana** → Visualization & dashboards
* ⚡ **Prometheus** → Metrics collection & storage

Together, they form an industry-standard monitoring solution used in **DevOps, SRE, and Cloud environments**.

---

## 🌟 What is Grafana?

Grafana is an open-source tool used to visualize and analyze metrics.

### Features:

* Create interactive dashboards
* Real-time monitoring
* Alerting system
* Supports multiple data sources

---

## 🌟 What is Prometheus?

Prometheus is an open-source monitoring system.

### Features:

* Time-series database
* Powerful query language (PromQL)
* Metrics scraping
* Alerting support

---

## ✅ Prerequisites

* Ubuntu 20.04 or later 🐧
* Non-root user with sudo access
* Internet connection 🌐

---

## ⚡ Installation Steps

### 🔹 Install Grafana

```bash
# Update packages
sudo apt update
sudo apt install -y apt-transport-https software-properties-common wget

# Add Grafana GPG key
sudo wget -q -O /usr/share/keyrings/grafana.key https://apt.grafana.com/gpg.key

# Add repository
echo "deb [signed-by=/usr/share/keyrings/grafana.key] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

# Install Grafana
sudo apt update
sudo apt install grafana -y

# Start and enable service
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

---

### 🔹 Install Prometheus

```bash
# Update system
sudo apt update
sudo apt upgrade -y

# Install Prometheus + Node Exporter
sudo apt install prometheus prometheus-node-exporter -y

# Enable services
sudo systemctl enable --now prometheus prometheus-node-exporter
```

---

## ⚙️ Configuration (Optional)

Edit Prometheus config file:

```bash
sudo nano /etc/prometheus/prometheus.yml
```

➡️ Add scrape targets, jobs, and alert rules as needed.

---

## 🌐 Access Web UI

| Tool       | URL                   | Credentials   |
| ---------- | --------------------- | ------------- |
| Grafana    | http://localhost:3000 | admin / admin |
| Prometheus | http://localhost:9090 | —             |

> ⚠️ Change Grafana password after first login.

---

## 🎯 Verify Installation

```bash
# Grafana status
systemctl status grafana-server

# Prometheus status
systemctl status prometheus
```

---

## 🚀 Next Steps

* Add Prometheus as a data source in Grafana
* Create dashboards
* Set up alerts & notifications
* Monitor servers and applications

---

## 💡 Why Use Grafana + Prometheus?

* 📊 Real-time monitoring
* ⚡ Fast & lightweight
* 🔥 Industry-standard tools
* 🎯 Ideal for DevOps & Cloud Engineers

---

## 🙌 Conclusion

You have successfully set up **Grafana + Prometheus** 🎉

Now you can:

* Build dashboards
* Monitor systems
* Improve observability

---

⭐ If you found this useful, give it a **star** and share it!

**Happy Monitoring ❤️**
