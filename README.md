# AQUA-PEARL-INN-Token-
AQUA PEARL INN (API) token smart contract on Binance Smart Chain.
🌊 AQUA PEARL INN (API) Token

AQUA PEARL INN (API) is a decentralized cryptocurrency token built on Binance Smart Chain (BSC), designed for the future of hospitality and luxury experiences.

---

🚀 Features

- BEP20 Token on BSC
- Fast & Low Fees
- Community Driven
- Future Hospitality Use Case

---

💡 Vision

To create a global hospitality ecosystem where token holders get benefits such as hotel discounts, loyalty rewards, and exclusive services.

---

🔗 Contract Details

- Name: AQUA PEARL INN
- Symbol: API
- Network: Binance Smart Chain

---

💧 Liquidity

Liquidity is added on PancakeSwap to enable trading.

---

🌐 Website

Coming soon...

---

📣 Community

- Telegram: Coming soon
- Twitter: Coming soon

---

⚠️ Disclaimer

This project is for educational and experimental purposes. Please do your own research before investing.
🌊 AQUA PEARL INN (API)

Whitepaper

---

1. 📌 Introduction

AQUA PEARL INN (API) is a decentralized cryptocurrency token built on the Binance Smart Chain (BSC), designed to revolutionize the hospitality and luxury experience industry.

The project aims to integrate blockchain technology with real-world hotel services, enabling seamless rewards, discounts, and future digital ownership opportunities.

---

2. 🎯 Vision

Our vision is to create a global ecosystem where:

- Travelers can benefit from token-based rewards
- Hotels can adopt blockchain for loyalty programs
- Users can access exclusive hospitality experiences

---

3. 🚀 Mission

- Build a trusted hospitality token
- Enable real-world use cases
- Create a strong global community
- Ensure transparency and decentralization

---

4. 🪙 Token Overview

- Token Name: AQUA PEARL INN
- Symbol: API
- Blockchain: Binance Smart Chain (BEP-20)
- Total Supply: 1,000,000 API
- Decimals: 18

---

5. 💡 Use Cases

AQUA PEARL INN (API) will be used for:

- 🏨 Hotel booking discounts (future integration)
- 🎁 Loyalty rewards for customers
- 🌐 Membership access to exclusive services
- 💎 Premium experiences in hospitality ecosystem

---

6. 💧 Liquidity & Trading

Liquidity is added on decentralized exchanges like PancakeSwap to enable:

- Buying and selling of API tokens
- Market-based price discovery
- Open and permissionless trading

---

7. 🔒 Security & Transparency

- Smart contract deployed on blockchain
- Publicly verifiable transactions
- Community-driven development

Future plans include:

- Smart contract audit
- Liquidity locking

---

8. 📣 Community & Growth

The success of AQUA PEARL INN depends on its community.

We will build presence through:

- Telegram groups
- Social media platforms
- Community engagement programs

---

9. 🛣️ Roadmap

Phase 1

- Token creation
- Liquidity launch
- Website development

Phase 2

- Community building
- Marketing campaigns
- Exchange visibility

Phase 3

- Hospitality partnerships
- Utility integration
- Mobile/web platform

---

10. ⚠️ Disclaimer

AQUA PEARL INN (API) is an experimental and community-driven project.

- Cryptocurrency investments carry risk
- Users should conduct their own research (DYOR)
- The project does not guarantee profits

---

11. 🌐 Conclusion

AQUA PEARL INN aims to bridge the gap between blockchain technology and real-world hospitality services.

By combining innovation, trust, and community, API strives to build a sustainable and valuable ecosystem for the future.

---

© 2026 AQUA PEARL INN (API). All rights reserved.

Token Name: AQUA PEARL INN
Symbol: API
Network: Binance Smart Chain

👉 Fast, low fees, scalable


token algorithm i will share you


// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract AquaPearlInn {

    string public name = "AQUA PEARL INN";
    string public symbol = "API";
    uint8 public decimals = 18;
    uint256 public totalSupply = 1000000 * 10**18;

    address public owner;

    mapping(address => uint256) public balanceOf;
    mapping(address => mapping(address => uint256)) public allowance;

    uint256 public taxPercent = 2; // 2% fee

    constructor() {
        owner = msg.sender;
        balanceOf[msg.sender] = totalSupply;
    }

    modifier onlyOwner() {
        require(msg.sender == owner, "Not owner");
        _;
    }

    function transfer(address _to, uint256 _value) public returns (bool) {
        require(balanceOf[msg.sender] >= _value, "Low balance");

        uint256 fee = (_value * taxPercent) / 100;
        uint256 sendAmount = _value - fee;

        balanceOf[msg.sender] -= _value;
        balanceOf[_to] += sendAmount;
        balanceOf[owner] += fee; // fee goes to owner

        return true;
    }

    function setTax(uint256 _tax) public onlyOwner {
        taxPercent = _tax;
    }
}


last added some words token making algorithm make it fast