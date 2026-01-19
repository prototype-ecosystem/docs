+++
template = "landing.html"
title = "Prototype Network"

[extra]
version = "v0.1.0"

section_order = ["hero", "features"]

[extra.hero]
title = "Prototype Network"
badge = "Next-Gen Blockchain"
description = "A high-performance blockchain platform featuring ProtoBFT consensus, parallel EVM execution, and inverse rewards for true decentralization."
gradient_opacity = 40
image_opacity = 20
cta_buttons = [
    { text = "Get Started", url = "/docs/protocore", style = "primary" },
    { text = "View on GitHub", url = "https://github.com/prototype-ecosystem", style = "secondary" }
]

[extra.features_section]
title = "Key Features"
description = "Built for performance, security, and decentralization"
features = [
    { title = "ProtoBFT Consensus", desc = "Byzantine Fault Tolerant consensus with 2-block finality and VRF-based randomness", icon = "fa-solid fa-shield-halved" },
    { title = "Parallel EVM", desc = "Concurrent transaction execution for maximum throughput while maintaining compatibility", icon = "fa-solid fa-bolt" },
    { title = "Inverse Rewards", desc = "Unique validator incentives that promote true network decentralization", icon = "fa-solid fa-scale-balanced" },
    { title = "Account Abstraction", desc = "Native ERC-4337 support for smart contract wallets and gasless transactions", icon = "fa-solid fa-wallet" },
]
+++
