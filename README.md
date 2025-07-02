# Sing-Box Configuration Template

This repository contains a personal [sing-box](https://sing-box.sagernet.org/) configuration template designed for advanced routing and flexibility. It is intended to be used with a subscription converter tool like [Sub-Store](https://github.com/sub-store-org/Sub-Store) to generate a complete, runnable configuration file.

## Key Features

- **TUN Mode:** Configured for transparent proxying on `172.20.0.1/30`.
- **Advanced DNS Routing:** Separate DNS for domestic (`local_dns`) and foreign (`proxy_dns`) domains to optimize speed and accuracy.
- **Fine-grained Policy Routing:** Includes numerous policy groups (`selector`) for popular services like Netflix, Google, Spotify, AIGC, and more, allowing for specific node selection for each service.
- **Remote Rule Sets:** Leverages remote `rule_set` files for automatic updates to routing rules, including custom rules hosted within this repository.
- **Clash API Compatibility:** Features an integrated Clash API for easy management via external UI dashboards (e.g., Yacd, Metacubexd).
- **Optimized for Performance:** Caching for DNS and FakeIP is enabled to reduce latency.

## How to Use

This is **not** a standalone configuration. It is a template that requires your proxy subscription details to be injected into it.

1.  **Get a Subscription Converter:** Use a tool like [Sub-Store](https://github.com/sub-store-org/Sub-Store).
2.  **Import the Template:** Add the URL of the `sub_store_template/tun_template_1.11.json` file from this repository as your configuration template in the converter.
3.  **Add Your Subscription:** Add your proxy subscription link to the converter.
4.  **Generate the Configuration:** The converter will merge your subscription nodes with this template to produce a final, complete `config.json` file.
5.  **Use the Generated File:** Use the generated configuration file with your sing-box client.

## File Structure

- **`sub_store_template/`**: Contains the main `sing-box` configuration template (`tun_template_1.11.json`). This is the file you should point your subscription converter to.
- **`rule_set/`**: Contains custom rule sets used by the main template. These are fetched remotely by `sing-box` based on the URLs defined in the template.
  - `emby.json`
  - `eu.json`
  - `iso.json`
  - `spark.json`

## Policy Groups

The template includes the following selector and url-test groups, which will be populated by your subscription converter:

- **Service-Specific Selectors:** `China`, `Nintendo`, `Microsoft`, `Google`, `Apple`, `Github`, `AIGC`, `Spotify`, `Disney+`, `Netflix`, `TikTok`, `YouTube`, `Bilibili`, `Emby`, `Telegram`, `Dropbox`, `Spark`, `PayPal`, `LinkedIn`, `Slack`.
- **Region-Specific Selectors:** `Others`, `Europe`, `Korea`, `Japan`, `Hong Kong`, `Taiwan`, `United States`, `Singapore`.
- **Functional Groups:**
  - `Proxy`: A selector for all your proxy nodes.
  - `Auto`: A `url-test` group for automatic node selection based on latency.
  - `Direct`: A direct connection outbound.