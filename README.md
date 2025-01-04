# 🌅 Dawn 扩展机器人 [v1.6]

<div align="center">
  <img src="./console/images/console.png" alt="Dawn 扩展机器人控制台" width="600"/>
  
  <p align="center">
    <a href="https://t.me/JamBitPY">
      <img src="https://img.shields.io/badge/Telegram-频道-blue?style=for-the-badge&logo=telegram" alt="Telegram 频道">
    </a>
    <a href="https://t.me/+u7hWfz0WqsFkNmMy">
      <img src="https://img.shields.io/badge/Telegram-聊天-blue?style=for-the-badge&logo=telegram" alt="Telegram 聊天">
    </a>
  </p>
</div>

## 📋 目录
- [功能](#-功能)
- [要求](#-要求)
- [安装](#-安装)
- [配置](#%EF%B8%8F-配置)
- [使用](#-使用)
- [故障排除](#-故障排除)

## 🚀 功能

- ✨ **账户管理**
  - ✅ 自动账户注册和登录
  - 📧 智能账户重新验证系统
  - 🛡️ 基于令牌的认证存储
  
- 🤖 **自动化**
  - 🌾 智能任务完成
  - 💰 优化的积分获取
  - 🔄 高级的保持活跃系统
  
- 📊 **分析与导出**
  - 📈 全面的账户统计
  - 📉 被封禁账户跟踪
  - 📋 未验证账户监控
  
- 🔒 **安全**
  - 🧩 高级验证码解决集成
  - 🌐 代理支持（HTTP/SOCKS5）
  - 🔐 安全的邮件集成

## 💻 要求

- Python 3.11 或更高版本
- 稳定的网络连接
- 有效的邮箱账户
- 可用的代理（HTTP/SOCKS5）
- 验证码服务订阅（[2captcha](https://2captcha.com/zh/enterpage)/[anticaptcha](https://anti-captcha.com/zh/clients/reports/dashboard)）

## 🛠️ 安装

1. **克隆仓库**
   ```bash
   git clone https://github.com/huaguihai/DawnBot.git
   ```

2. **设置虚拟环境**
   ```bash
   python -m venv venv
   source venv/Scripts/activate  # Windows
   source venv/bin/activate      # Unix/MacOS
   ```

3. **安装依赖**
   ```bash
   pip install -r requirements.txt
   ```

## ⚙️ 配置

### 📁 settings.yaml

```yaml
# 核心配置
threads: 30                    # 并发操作线程数（最小：1）
keepalive_interval: 120        # 保持活跃信号间隔（秒）
referral_codes:               # 多个推荐码支持
  - ""                        # 在此添加你的推荐码

# 邮件重定向设置
redirect_settings:
  enabled: false              # 启用/禁用邮件重定向
  email: "test@gmail.com"     # 重定向邮箱地址
  password: "password"        # 邮箱密码
  imap_server: "imap.gmail.com"
  use_proxy: true            # 为邮件操作使用代理

# 验证码配置
captcha_module: 2captcha      # 选择：'2captcha' 或 'anticaptcha'
two_captcha_api_key: ""       # 2captcha API 密钥
anti_captcha_api_key: ""      # Anticaptcha API 密钥

# 启动设置
delay_before_start:
  min: 2                      # 最小启动延迟（秒）
  max: 3                      # 最大启动延迟（秒）

# 邮箱提供商设置
imap_settings:
  # 全球提供商
  gmail.com: imap.gmail.com
  yahoo.com: imap.mail.yahoo.com
  outlook.com: imap-mail.outlook.com
  hotmail.com: imap-mail.outlook.com
  icloud.com: imap.mail.me.com
  
  # 区域提供商
  mail.ru: imap.mail.ru
  rambler.ru: imap.rambler.ru
  gmx.com: imap.gmx.com
  onet.pl: imap.poczta.onet.pl
```

### 📁 输入文件结构

#### accounts/register.txt
```
邮箱:密码
邮箱:密码
```

#### accounts/farm.txt
```
邮箱:密码
邮箱:密码
```

#### accounts/reverify.txt
```
邮箱:密码
邮箱:密码
```

#### proxies/proxies.txt
```
http://用户:密码@ip:端口
http://ip:端口:用户:密码
socks5://用户:密码@ip:端口
```

## 🚀 使用

1. 按照上述说明配置所有必要文件
2. 启动机器人：
   ```bash
   python run.py
   ```

## ⚠️ 重要提示

- 🕒 推荐的保持活跃间隔：120秒
- 📧 Gmail用户：使用应用专用密码
- 🔄 未验证的账户可以使用注册模块重新验证
- 💾 授权令牌存储在本地数据库
- 🤖 需要外部验证码服务（2captcha/anticaptcha）

## 🔧 故障排除

### 常见问题及解决方案

#### 📧 邮箱验证失败
- 检查settings.yaml中的IMAP设置
- 检查邮箱提供商的安全设置
- 确保为Gmail使用应用专用密码

#### 🧩 验证码问题
- 验证API密钥有效性
- 检查服务余额
- 确保所选服务正常运行

#### 🌐 代理问题
- 验证代理格式
- 检查代理功能
- 确保代理认证正确

## 📞 支持

加入我们的Telegram社区获取支持：
- 📢 频道: [JamBitPY](https://t.me/JamBitPY)
- 💬 聊天: [JamBitChat](https://t.me/JamBitChat)
