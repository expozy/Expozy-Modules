<h1 align="center">Expozy Modules</h1>

<p align="center">
  <strong>External Connectors for Open Source Platforms</strong>
</p>

<p align="center">
  <a href="#installation"><img src="https://img.shields.io/badge/version-1.0.0-red.svg" alt="Version"></a>
  <a href="#license"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License"></a>
  <a href="#connectors"><img src="https://img.shields.io/badge/connectors-1-green.svg" alt="Connectors"></a>
</p>

---

## Overview

Expozy Modules provides seamless integration between your Expozy instance and popular open-source platforms. Connect your existing systems to leverage the full power of Expozy's headless commerce capabilities.

## Available Connectors

| Platform | Status | Version |
|----------|--------|---------|
| ✅ WordPress | Available | 1.0.0 |
| ⏳ Magento | Coming Soon | - |
| ⏳ Shopify | Coming Soon | - |
| ⏳ WooCommerce | Coming Soon | - |

---

## WordPress Connector

The WordPress connector allows you to integrate your WordPress site with Expozy, enabling seamless content and data synchronization.

### Features

- 🔄 **Two-way Sync** - Synchronize content between WordPress and Expozy
- 📦 **Product Import** - Import products from WordPress/WooCommerce
- 📝 **Content Management** - Manage WordPress content through Expozy
- 🔐 **Secure Authentication** - OAuth 2.0 based secure connection
- ⚡ **Real-time Updates** - Webhook support for instant synchronization

### Requirements

- WordPress 5.0 or higher
- PHP 7.4 or higher
- Expozy Core instance running
- SSL certificate (recommended)

### Installation

1. **Download the Plugin**

   Download the latest release from the [Releases](https://github.com/expozy/expozy-modules/releases) page.

2. **Install in WordPress**

   ```
   WordPress Admin → Plugins → Add New → Upload Plugin
   ```

   Upload the `expozy-connector.zip` file and activate the plugin.

3. **Configure Connection**

   Navigate to **Settings → Expozy** in your WordPress admin panel.

   ```
   Expozy API URL: https://your-expozy-instance.com/api
   API Key: your-api-key
   ```

4. **Test Connection**

   Click "Test Connection" to verify the integration is working correctly.

### Configuration

```php
// wp-config.php (optional advanced configuration)

define('EXPOZY_API_URL', 'https://your-expozy-instance.com/api');
define('EXPOZY_API_KEY', 'your-api-key');
define('EXPOZY_SYNC_INTERVAL', 300); // Sync interval in seconds
define('EXPOZY_DEBUG', false);
```

### Usage

#### Sync Products

```php
// Manual sync trigger
do_action('expozy_sync_products');

// Sync specific product
do_action('expozy_sync_product', $product_id);
```

#### Webhooks

The connector automatically registers webhooks for:

- `product.created`
- `product.updated`
- `product.deleted`
- `order.created`
- `order.updated`

### Hooks & Filters

```php
// Modify data before sync
add_filter('expozy_before_product_sync', function($data, $product_id) {
    // Modify product data
    return $data;
}, 10, 2);

// Action after successful sync
add_action('expozy_after_sync', function($result) {
    // Handle post-sync logic
});
```

---

## Roadmap

We're actively working on expanding our connector ecosystem:

- [ ] **Magento 2 Connector** - Q2 2025
- [ ] **Shopify Connector** - Q3 2025
- [ ] **WooCommerce Standalone** - Q3 2025
- [ ] **PrestaShop Connector** - Q4 2025
- [ ] **OpenCart Connector** - Q4 2025

Want to request a specific connector? [Open an issue](https://github.com/expozy/expozy-modules/issues/new)!

---

## Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/new-connector`)
3. Commit your changes (`git commit -m 'Add new connector'`)
4. Push to the branch (`git push origin feature/new-connector`)
5. Open a Pull Request

### Development Setup

```bash
# Clone the repository
git clone https://github.com/expozy/expozy-modules.git

# Navigate to connector directory
cd expozy-modules/wordpress

# Install dependencies
composer install

# Run tests
composer test
```

---

## Support

- 📧 [Email Support](mailto:support@expozy.com)

---

<p align="center">
  Made with ❤️ by the <a href="https://expozy.com">Expozy</a> Team
</p>
