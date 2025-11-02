# 🚀 DANTO Integration Guide

## New Features Added

### 🤖 MiniMax M2 AI Provider (FREE!)

MiniMax M2 is now supported as a free AI provider for trading decisions.

#### Why MiniMax M2?
- ✅ **Completely FREE** - No API costs
- ✅ **High Performance** - Competitive with paid models
- ✅ **Anthropic Compatible** - Uses Claude-style API format
- ✅ **Long Context** - Handles large market data efficiently

#### Configuration

```json
{
  "id": "binance_minimax",
  "name": "Binance MiniMax Trader",
  "enabled": true,
  "ai_model": "minimax",
  "exchange": "binance",
  "binance_api_key": "your_binance_api_key",
  "binance_secret_key": "your_binance_secret_key",
  "minimax_key": "your_minimax_api_key",
  "initial_balance": 1000,
  "scan_interval_minutes": 3
}
```

#### Getting MiniMax API Key

1. Visit [MiniMax Platform](https://api.minimax.io)
2. Sign up for a free account
3. Navigate to API Keys section
4. Create a new API key
5. Copy the key (starts with `mm-`)

#### Environment Variables (Alternative Setup)

You can also configure MiniMax using environment variables:

```bash
export ANTHROPIC_BASE_URL="https://api.minimax.io/anthropic"
export ANTHROPIC_AUTH_TOKEN="your_minimax_api_key"
export ANTHROPIC_MODEL="MiniMax-M2"
```

---

### 🏦 Delta Exchange Integration

Delta Exchange is now supported as a crypto derivatives trading platform.

#### Why Delta Exchange?
- ✅ **Advanced Derivatives** - Options, futures, perpetuals
- ✅ **High Leverage** - Up to 100x leverage available
- ✅ **Low Fees** - Competitive trading fees
- ✅ **API Rich** - Comprehensive REST API
- ✅ **Global Access** - Available worldwide

#### Configuration

```json
{
  "id": "delta_deepseek",
  "name": "Delta Exchange DeepSeek Trader",
  "enabled": true,
  "ai_model": "deepseek",
  "exchange": "delta",
  "delta_api_key": "your_delta_api_key",
  "delta_api_secret": "your_delta_api_secret",
  "delta_testnet": false,
  "deepseek_key": "your_deepseek_api_key",
  "initial_balance": 1000.0,
  "scan_interval_minutes": 3
}
```

#### Getting Delta Exchange API Keys

1. **Register Account**
   - Visit [Delta Exchange](https://www.delta.exchange)
   - Complete KYC verification
   - Enable futures trading

2. **Create API Keys**
   - Go to Account → API Management
   - Click "Create New API Key"
   - Enable required permissions:
     - ✅ Read Account Info
     - ✅ Read Positions
     - ✅ Place Orders
     - ✅ Cancel Orders
   - Save API Key and Secret

3. **Security Settings**
   - Whitelist your IP address
   - Set appropriate rate limits
   - Enable 2FA for additional security

#### Supported Features

| Feature | Status | Notes |
|---------|--------|-------|
| Spot Trading | ❌ | Not supported (futures only) |
| Perpetual Futures | ✅ | Full support |
| Options Trading | ✅ | Basic support |
| Leverage Trading | ✅ | Up to 100x |
| Stop Loss/Take Profit | ✅ | Advanced order types |
| Position Management | ✅ | Full position control |

---

## Updated Configuration Examples

### Multi-Provider Competition

```json
{
  "traders": [
    {
      "id": "binance_deepseek",
      "name": "Binance DeepSeek",
      "ai_model": "deepseek",
      "exchange": "binance",
      "deepseek_key": "sk-xxx"
    },
    {
      "id": "delta_minimax",
      "name": "Delta MiniMax",
      "ai_model": "minimax",
      "exchange": "delta",
      "minimax_key": "mm-xxx"
    },
    {
      "id": "hyperliquid_qwen",
      "name": "Hyperliquid Qwen",
      "ai_model": "qwen",
      "exchange": "hyperliquid",
      "qwen_key": "sk-xxx"
    }
  ]
}
```

### AI Provider Comparison

| Provider | Cost | Speed | Quality | Free Tier |
|----------|------|-------|---------|-----------|
| **DeepSeek** | $0.14/1M tokens | Fast | Excellent | ❌ |
| **Qwen** | $0.20/1M tokens | Medium | Very Good | ❌ |
| **MiniMax M2** | **FREE** | Fast | Very Good | ✅ |
| **Custom (GPT-4)** | $10/1M tokens | Medium | Excellent | ❌ |

---

## Migration Guide

### From Existing Setup

1. **Backup Configuration**
   ```bash
   cp config.json config.json.backup
   ```

2. **Update Configuration**
   - Add new AI provider fields
   - Add new exchange configurations
   - Test with small amounts first

3. **Gradual Migration**
   - Start with one new provider/exchange
   - Monitor performance for 24-48 hours
   - Gradually migrate more capital

### Testing New Features

1. **MiniMax Testing**
   ```json
   {
     "id": "test_minimax",
     "enabled": true,
     "ai_model": "minimax",
     "initial_balance": 100,
     "scan_interval_minutes": 5
   }
   ```

2. **Delta Exchange Testing**
   ```json
   {
     "id": "test_delta",
     "enabled": true,
     "exchange": "delta",
     "delta_testnet": true,
     "initial_balance": 100
   }
   ```

---

## Troubleshooting

### MiniMax Issues

**Error: "Invalid API Key"**
- Verify key format (should start with `mm-`)
- Check account status on MiniMax platform
- Ensure API key has proper permissions

**Error: "Rate Limit Exceeded"**
- MiniMax has generous free limits
- Increase `scan_interval_minutes` if needed
- Check for multiple concurrent requests

### Delta Exchange Issues

**Error: "Insufficient Permissions"**
- Verify API key permissions in Delta dashboard
- Ensure trading permissions are enabled
- Check IP whitelist settings

**Error: "Invalid Signature"**
- Verify API secret is correct
- Check system time synchronization
- Ensure no extra spaces in credentials

---

## Performance Optimization

### AI Provider Selection

- **For Cost Efficiency**: Use MiniMax M2 (free)
- **For Maximum Performance**: Use DeepSeek
- **For Reliability**: Use Qwen
- **For Advanced Features**: Use Custom GPT-4

### Exchange Selection

- **For Liquidity**: Use Binance
- **For Decentralization**: Use Hyperliquid
- **For Advanced Derivatives**: Use Delta Exchange
- **For Low Fees**: Use Aster DEX

### Resource Management

```json
{
  "leverage": {
    "btc_eth_leverage": 5,
    "altcoin_leverage": 3
  },
  "scan_interval_minutes": 5,
  "max_daily_loss": 5.0
}
```

---

## Support

For issues with new integrations:

1. **Check Logs**: Look for specific error messages
2. **Verify Configuration**: Ensure all required fields are set
3. **Test Connectivity**: Use exchange/AI provider test endpoints
4. **Community Support**: Join [Telegram Developer Community](https://t.me/nofx_dev_community)

---

**Last Updated**: 2025-11-03
**Version**: 2.1.0
