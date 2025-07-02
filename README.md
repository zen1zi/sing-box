# Sing-Box Configuration Template

A sophisticated [sing-box](https://sing-box.sagernet.org/) configuration template engineered for advanced routing scenarios and maximum flexibility. This template is designed to work seamlessly with subscription converter tools like [Sub-Store](https://github.com/sub-store-org/Sub-Store) to generate production-ready configuration files.

## ✨ Key Features

- **🌐 TUN Mode Support:** Transparent proxying configured on `172.20.0.1/30` for system-wide traffic capture
- **🎯 Intelligent DNS Routing:** Dual DNS architecture with separate resolvers for domestic (`local_dns`) and international (`proxy_dns`) domains
- **🔧 Granular Policy Management:** Comprehensive policy groups for major services including Netflix, Google, Spotify, AI platforms, and more
- **📡 Dynamic Rule Sets:** Remote rule sets with automatic updates for continuously optimized routing rules
- **⚡ Clash API Integration:** Built-in Clash API support for seamless management via external dashboards (Yacd, Metacubexd)
- **🚀 Performance Optimized:** Advanced DNS caching and FakeIP configuration for minimal latency

## 🚀 Quick Start

> **Important:** This is a configuration template, not a standalone config. It requires your proxy subscription to function.

### Prerequisites
- A subscription converter tool (recommended: [Sub-Store](https://github.com/sub-store-org/Sub-Store))
- A valid proxy subscription from your service provider

### Setup Instructions

1. **Install Sub-Store or similar converter**
2. **Import this template:**
   - Use the raw URL of `sub_store_template/tun_template_1.11.json`
3. **Configure your subscription:**
   - Add your proxy subscription link to the converter
4. **Generate configuration:**
   - The converter will merge your nodes with this template
5. **Deploy to sing-box:**
   - Use the generated `config.json` with your sing-box client

## 📁 Repository Structure

```
├── sub_store_template/
│   └── tun_template_1.11.json    # Main configuration template
└── rule_set/                     # Custom routing rules
    ├── emby.json                 # Emby media server rules
    ├── eu.json                   # European region rules
    ├── iso.json                  # ISO/International rules
    └── spark.json                # Spark email client rules
```

### Template File
- **`sub_store_template/tun_template_1.11.json`**: Core configuration template compatible with sing-box v1.11+

### Rule Sets
- **`rule_set/`**: Custom rule definitions automatically fetched by sing-box for dynamic routing updates

## 🎛️ Policy Groups

The template provides comprehensive routing policies organized into three categories:

### 🌍 Service-Specific Policies
Dedicated selectors for optimal service routing:
- **Streaming:** `Netflix`, `Disney+`, `YouTube`, `Bilibili`, `Spotify`, `Emby`
- **Technology:** `Google`, `Apple`, `Microsoft`, `Github`
- **Communication:** `Telegram`, `Slack`, `LinkedIn`
- **Productivity:** `Dropbox`, `Spark`, `PayPal`
- **Gaming:** `Nintendo`
- **AI Services:** `AIGC` (AI/GPT services)
- **Social Media:** `TikTok`

### 🗺️ Regional Selectors
Geographic routing options:
- **Asia-Pacific:** `Hong Kong`, `Taiwan`, `Japan`, `Korea`, `Singapore`
- **Americas:** `United States`
- **Europe:** `Europe`
- **Domestic:** `China`
- **Fallback:** `Others`

### ⚙️ Functional Groups
Core routing mechanics:
- **`Proxy`**: Manual node selection interface
- **`Auto`**: Latency-based automatic selection (`url-test`)
- **`Direct`**: Bypass proxy for local traffic

## 🔧 Advanced Configuration

### DNS Configuration
- **Local DNS**: `223.5.5.5`, `119.29.29.29` for domestic domains
- **Proxy DNS**: `1.1.1.1`, `8.8.8.8` for international domains
- **FakeIP**: Enabled for enhanced performance

### API Management
- **Clash API**: `http://127.0.0.1:9090`
- **Web UI**: Compatible with Yacd, Metacubexd, and other Clash dashboards

## 📝 License

This project is available under the MIT License. Feel free to modify and distribute according to your needs.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit issues or pull requests to improve this template.

---

> **Disclaimer**: This template is for educational and personal use. Ensure compliance with your local laws and service provider terms when using proxy services.