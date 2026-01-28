# Milestone Delivery 📫

**Application Document**: [SubLua Grant Application](https://github.com/AstarNetwork/PolkadotOpenSourceGrants/blob/main/applications/Sublua.md)  
**Milestone Number**: 2  
**DOT Payment Address**: 13WXPNwHAdKFZL5xF9bScQ5kYueRCevmQDkdm8MwVHExp6EZ

## Context

SubLua v0.3.1 represents a production-ready Lua SDK for Substrate-based blockchains, delivering enterprise-grade features for advanced blockchain application development. This milestone focuses on advanced cryptographic operations, robust WebSocket connection management, comprehensive security documentation, and production deployment tooling with automated distribution.

**Core Achievements:**

1. **Advanced Cryptographic Features**: Full support for multi-signature accounts, proxy accounts, and on-chain identity management using Substrate's native cryptographic primitives via `sp-core` and `subxt`.

2. **WebSocket Connection Management**: Enterprise-grade WebSocket client with automatic reconnection, connection pooling, heartbeat monitoring, and graceful HTTP fallback.

3. **Production Deployment**: Complete SDK packaging with LuaRocks distribution, automated CI/CD pipeline, cross-platform binary distribution, and comprehensive documentation.

4. **Security Hardening**: Comprehensive security documentation covering key storage, mnemonic management, proxy account security, multisig best practices, and production deployment guidelines.

5. **Production Game Example**: Complete game demonstrating player account management, token economics with play-to-earn mechanics, multi-signature treasury, and on-chain leaderboards.

6. **Technical Article**: In-depth technical blog post detailing SubLua's architecture, FFI design, dynamic metadata integration, advanced crypto features, and WebSocket implementation.

## Deliverables

| Number | Deliverable | Link | Notes |
|--------|-------------|------|-------|
| **0a.** | **License** | [LICENSE](https://github.com/MontaQLabs/sublua/blob/main/LICENSE) | MIT License |
| **0b.** | **Documentation** | [README.md](https://github.com/MontaQLabs/sublua/blob/main/README.md)<br>[docs/API.md](https://github.com/MontaQLabs/sublua/blob/main/docs/API.md)<br>[docs/SECURITY.md](https://github.com/MontaQLabs/sublua/blob/main/docs/SECURITY.md)<br>[docs/GAME_DEVELOPMENT.md](https://github.com/MontaQLabs/sublua/blob/main/docs/GAME_DEVELOPMENT.md) | Complete documentation including installation guide, API reference, security best practices, game development guide (925 lines), and advanced usage patterns. |
| **0c.** | **Testing and Testing Guide** | [test/run_tests.lua](https://github.com/MontaQLabs/sublua/blob/main/test/run_tests.lua)<br>[test/test_user_api.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_user_api.lua)<br>[test/test_dynamic_metadata.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_dynamic_metadata.lua)<br>[test/test_advanced_crypto.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_advanced_crypto.lua)<br>[test/test_websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_websocket.lua) | 37+ tests covering core SDK, user API, dynamic metadata, advanced crypto, and WebSocket features. All validated on live networks. |
| **0d.** | **Docker** | N/A | Docker not applicable - SubLua is distributed as a native LuaRocks package with precompiled binaries. Users install via `luarocks install sublua`. |
| **0e.** | **Article** | [ARTICLE.md](https://github.com/MontaQLabs/sublua/blob/main/ARTICLE.md) | **✅ Complete Case Study Article:**<br>Comprehensive technical article (2,800+ words) showcasing SubLua as a complete real-world application. Includes:<br>• Architecture decisions and FFI design rationale<br>• Lessons learned from production deployment<br>• Performance metrics and benchmarks<br>• Real-world use cases (gaming, DeFi, IoT)<br>• Implementation details for all major features<br>• Best practices and security considerations |
| **1.** | **WebSocket Connection Management** | [sublua/websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/websocket.lua)<br>[polkadot-ffi-subxt/src/lib.rs](https://github.com/MontaQLabs/sublua/blob/main/polkadot-ffi-subxt/src/lib.rs)<br>[examples/websocket_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/websocket_example.lua)<br>[test/test_websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_websocket.lua) | ✅ **Fully Implemented:**<br>• Connection pooling (one connection per endpoint)<br>• Automatic reconnection with exponential backoff (100ms → 30s)<br>• Heartbeat monitoring (30-second intervals)<br>• Connection statistics tracking<br>• Thread-safe with Arc + RwLock<br>• 11/11 tests passing on live networks |
| **2.** | **Advanced Cryptographic Features** | [sublua/multisig.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/multisig.lua)<br>[sublua/proxy.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/proxy.lua)<br>[sublua/identity.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/identity.lua)<br>[examples/multisig_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/multisig_example.lua)<br>[examples/proxy_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/proxy_example.lua)<br>[examples/identity_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/identity_example.lua)<br>[test/test_advanced_crypto.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_advanced_crypto.lua) | ✅ **Fully Implemented:**<br>• **Multi-signature accounts**: Deterministic address derivation, threshold validation<br>• **Proxy accounts**: Add/remove proxies, proxy types (Any, NonTransfer, Governance, Staking)<br>• **On-chain identity**: Set/clear/query identity<br>• All operations use `sp-core` for cryptographic correctness<br>• 10/10 tests passing |
| **3.** | **Production Game Example** | **🎮 Game Executables (Built Locally):**<br>• TreasureHunter-macOS.zip (34MB, standalone .app)<br>• TreasureHunter.love (2.4MB, cross-platform)<br>• Available via [Drive Link] or build locally<br><br>**Source Code:**<br>[game/main.lua](https://github.com/MontaQLabs/sublua/blob/main/game/main.lua) (700+ lines)<br>[game/conf.lua](https://github.com/MontaQLabs/sublua/blob/main/game/conf.lua)<br>[game/PLAY.md](https://github.com/MontaQLabs/sublua/blob/main/game/PLAY.md)<br>[game/GAME_README.md](https://github.com/MontaQLabs/sublua/blob/main/game/GAME_README.md)<br><br>**Build Guide:**<br>[game/BUILD_GAME.md](https://github.com/MontaQLabs/sublua/blob/main/game/BUILD_GAME.md) (Complete build instructions)<br><br>**Terminal Version:**<br>[examples/treasure_hunter_game.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/treasure_hunter_game.lua) | ✅ **Complete & Polished Production Game:**<br>• **🎮 Standalone Executable**: TreasureHunter.app (macOS) - double-click to play, no installation required<br>• **🎨 Professional Aesthetics**: Neon cyberpunk theme with geometric graphics, glowing effects, animated background<br>• **💰 Player Account Management**: Wallet UI shows real balance, mnemonic input for secure account access<br>• **🪙 Token Economics**: Entry fees (0.1 WND), play-to-earn rewards (0.01 WND per treasure), score bonuses<br>• **🏆 On-Chain Leaderboard**: Rankings persist on Westend blockchain with medal system (🥇🥈🥉)<br>• **🔐 Secure Transaction Handling**: Treasury account (2-of-3 multisig) manages prize distribution<br>• **🌐 Live Blockchain Integration**: Real-time balance fetching and on-chain reward submission to Westend<br>• **📦 Self-Contained**: Bundles SubLua SDK and FFI library - works out of the box<br>• **📱 Cross-Platform Ready**: Build scripts for macOS .app, Windows .exe, Linux .love<br>• **📖 Complete Documentation**: How to play, how to build, game development guide (925 lines)<br>• **✅ Fully Built**: Executables ready (34MB macOS app, 2.4MB .love file) |
| **4.** | **SDK Packaging and Distribution** | **📦 LuaRocks Package:**<br>[https://luarocks.org/modules/abhiraj-mengade/sublua](https://luarocks.org/modules/abhiraj-mengade/sublua)<br>**🚀 Releases:**<br>[v0.3.1 (Latest)](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.1)<br>[v0.3.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.0)<br>[v0.2.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.2.0)<br>[All Releases](https://github.com/MontaQLabs/sublua/releases)<br>**📝 Source:**<br>[sublua-0.3.1-1.rockspec](https://github.com/MontaQLabs/sublua/blob/main/sublua-0.3.1-1.rockspec)<br>[install_sublua.sh](https://github.com/MontaQLabs/sublua/blob/main/install_sublua.sh)<br>[.github/workflows/ci.yml](https://github.com/MontaQLabs/sublua/blob/main/.github/workflows/ci.yml)<br>[build_binaries.sh](https://github.com/MontaQLabs/sublua/blob/main/build_binaries.sh) | ✅ **Complete Production Distribution:**<br>• **📦 LuaRocks Package**: Published at [luarocks.org/modules/abhiraj-mengade/sublua](https://luarocks.org/modules/abhiraj-mengade/sublua)<br>&nbsp;&nbsp;- 25+ downloads across 10 versions<br>&nbsp;&nbsp;- Install: `luarocks install sublua`<br>&nbsp;&nbsp;- Automated publishing via CI/CD<br>• **🌐 One-Liner Installer**: `curl -sSL https://raw.githubusercontent.com/MontaQLabs/sublua/main/install_sublua.sh \| bash`<br>&nbsp;&nbsp;- Auto-detects OS (macOS/Linux) and architecture<br>&nbsp;&nbsp;- Installs LuaJIT + LuaRocks if needed<br>&nbsp;&nbsp;- Downloads correct precompiled FFI binary<br>&nbsp;&nbsp;- Installs SubLua from LuaRocks<br>&nbsp;&nbsp;- Verifies installation automatically<br>• **⚙️ Automated CI/CD Pipeline** ([ci.yml](https://github.com/MontaQLabs/sublua/blob/main/.github/workflows/ci.yml)):<br>&nbsp;&nbsp;- Multi-platform testing (Ubuntu, macOS)<br>&nbsp;&nbsp;- Automated Rust FFI builds for 3 platforms<br>&nbsp;&nbsp;- GitHub release creation with binary artifacts<br>&nbsp;&nbsp;- LuaRocks publishing on version tags<br>&nbsp;&nbsp;- Pre-commit hooks for quality assurance<br>• **💾 Cross-Platform Binaries**: Precompiled FFI libraries for:<br>&nbsp;&nbsp;- macOS Apple Silicon (aarch64)<br>&nbsp;&nbsp;- macOS Intel (x86_64)<br>&nbsp;&nbsp;- Linux x86_64<br>• **🛠️ Build Scripts**: Reproducible builds with [build_binaries.sh](https://github.com/MontaQLabs/sublua/blob/main/build_binaries.sh) |
| **5.** | **Security Audit and Hardening** | [docs/SECURITY.md](https://github.com/MontaQLabs/sublua/blob/main/docs/SECURITY.md) | ✅ **Comprehensive Security Documentation:**<br>• Key storage best practices<br>• Mnemonic phrase management<br>• Proxy account security<br>• Multisig security guidelines<br>• Production deployment checklist<br>• Network security recommendations |

## Installation Guide

SubLua is designed for **zero-friction installation**. Users can install SubLua without manually handling FFI library paths or complex configuration.

### 🚀 One-Liner Install (Recommended)

```bash
curl -sSL https://raw.githubusercontent.com/MontaQLabs/sublua/main/install_sublua.sh | bash
```

**What it does automatically:**
- ✅ Detects your OS (macOS/Linux) and CPU architecture
- ✅ Installs LuaJIT and LuaRocks (if not present)
- ✅ Installs SubLua from [LuaRocks.org](https://luarocks.org/modules/abhiraj-mengade/sublua)
- ✅ Downloads the correct precompiled FFI binary for your platform
- ✅ Configures paths automatically (`~/.sublua/lib/`)
- ✅ Verifies the installation with a test script
- ✅ No manual configuration required!

### 📦 LuaRocks Install (For Package Managers)

```bash
# Install SubLua from LuaRocks (FFI auto-loads from standard paths)
luarocks install sublua
```

The FFI library is automatically downloaded and placed in `~/.sublua/lib/` by the installer script. SubLua's smart FFI loader searches multiple standard locations, so users don't need to set `SUBLUA_FFI_PATH` or manage paths manually.

### 🛠️ Developer Install (Manual Build)

```bash
# Clone repository
git clone https://github.com/MontaQLabs/sublua.git
cd sublua

# Build FFI library (requires Rust 1.70+)
cd polkadot-ffi-subxt
cargo build --release
cd ..

# Copy binary to standard location
mkdir -p precompiled/macos-aarch64  # or your platform
cp polkadot-ffi-subxt/target/release/libpolkadot_ffi.dylib precompiled/macos-aarch64/

# Run tests
luajit test/run_tests.lua
```

### ✅ Verify Installation

```lua
local sublua = require("sublua")
-- FFI loads automatically, no path configuration needed!
sublua.ffi()
print("SubLua v" .. sublua.version .. " loaded successfully!")

-- Create a signer
local signer = sublua.signer().from_mnemonic("your twelve word mnemonic here")
print("Address:", signer:get_ss58_address(0))  -- Polkadot mainnet
```

**Result:** Works immediately after installation, no environment variables or path configuration required! 🎉

## Running Tests

```bash
# Core SDK tests
cd test && luajit run_tests.lua

# User API tests
luajit test_user_api.lua

# Advanced crypto tests
luajit test_advanced_crypto.lua

# WebSocket tests
luajit test_websocket.lua

# Dynamic metadata tests
luajit test_dynamic_metadata.lua
```

**Expected Output:** All tests pass against live Westend and Polkadot networks.

## CI/CD Pipeline

The automated CI/CD pipeline ([.github/workflows/ci.yml](https://github.com/MontaQLabs/sublua/blob/main/.github/workflows/ci.yml)) provides:

1. **Automated Testing**: Runs test suite on every push/PR against Ubuntu and macOS
2. **Cross-Platform Builds**: Compiles FFI library for Linux x86_64, macOS aarch64, macOS x86_64
3. **Release Automation**: Creates GitHub releases with binary artifacts on version tags
4. **LuaRocks Publishing**: Automatically publishes to LuaRocks on release

## Technical Highlights

- **subxt 0.44** integration for enterprise-grade Substrate interaction
- **sp-core 38.0** for production cryptography (multisig, proxy, identity)
- **tokio-tungstenite** for WebSocket client implementation
- **37+ passing tests** including live network validation
- **Zero external Lua dependencies** for core FFI functionality
- **Cross-platform support**: macOS (aarch64/x86_64), Linux (x86_64)
- **Thread-safe WebSocket pooling** with Arc + RwLock
- **Automatic reconnection** with exponential backoff

## Test Coverage Summary

| Test Suite | Tests | Status |
|------------|-------|--------|
| Core SDK | 8 | ✅ Passing |
| User API | 8 | ✅ Passing |
| Dynamic Metadata | 5 | ✅ Passing |
| Advanced Crypto | 10 | ✅ Passing |
| WebSocket | 11 | ✅ Passing |
| **Total** | **42** | **All Passing** |

## Version History

| Version | Tag | Date | Downloads | Key Features |
|---------|-----|------|-----------|--------------|
| v0.1.0 | [v0.1.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.0) | Sep 2024 | 2 | Initial release with basic FFI |
| v0.1.1 | [v0.1.1](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.1) | Sep 2024 | 2 | Balance queries and transfers |
| v0.1.2 | [v0.1.2](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.2) | Sep 2024 | 3 | Extrinsic builder API |
| v0.1.3 | [v0.1.3](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.3) | Oct 2024 | 1 | RPC improvements |
| v0.1.4 | [v0.1.4](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.4) | Oct 2024 | 3 | Metadata parsing |
| v0.1.5 | [v0.1.5](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.5) | Oct 2024 | 2 | Multi-chain support |
| v0.1.6 | [v0.1.6](https://github.com/MontaQLabs/sublua/releases/tag/v0.1.6) | Oct 2024 | 8 | Dynamic metadata |
| v0.2.0 | [v0.2.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.2.0) | Jan 2026 | 0 | Advanced crypto (multisig, proxy, identity) |
| v0.3.0 | [v0.3.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.0) | Jan 2026 | 4 | WebSocket management, CI/CD |
| **v0.3.1** | [**v0.3.1**](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.1) | **Jan 2026** | **0** | **Production game, installer, documentation** |

**Total Downloads**: 25+ across all versions on [LuaRocks](https://luarocks.org/modules/abhiraj-mengade/sublua)

## Live Network Validation

All features validated on live networks:

- **Westend Testnet**: Balance queries, transfers, metadata fetching, WebSocket connections
- **Polkadot Mainnet**: Metadata discovery, pallet enumeration, runtime compatibility checks
- **Successful Transactions**: Multiple test transactions submitted and confirmed on-chain

## Additional Resources

### 📦 Package & Distribution
- **LuaRocks Package**: https://luarocks.org/modules/abhiraj-mengade/sublua
- **GitHub Repository**: https://github.com/MontaQLabs/sublua
- **Latest Release**: https://github.com/MontaQLabs/sublua/releases/latest
- **All Releases**: https://github.com/MontaQLabs/sublua/releases

### 📚 Documentation
- **Main README**: https://github.com/MontaQLabs/sublua#readme
- **Technical Case Study Article**: [ARTICLE.md](https://github.com/MontaQLabs/sublua/blob/main/ARTICLE.md) (2,800+ words)
- **API Documentation**: [docs/API.md](https://github.com/MontaQLabs/sublua/blob/main/docs/API.md)
- **Game Development Guide**: [docs/GAME_DEVELOPMENT.md](https://github.com/MontaQLabs/sublua/blob/main/docs/GAME_DEVELOPMENT.md) (925 lines)
- **Security Best Practices**: [docs/SECURITY.md](https://github.com/MontaQLabs/sublua/blob/main/docs/SECURITY.md)
- **Contributing Guide**: [CONTRIBUTING.md](https://github.com/MontaQLabs/sublua/blob/main/CONTRIBUTING.md)
- **Change Log**: [CHANGELOG.md](https://github.com/MontaQLabs/sublua/blob/main/CHANGELOG.md)

### 🎮 Game Demo
- **Executables**: Built locally (TreasureHunter-macOS.zip - 34MB, TreasureHunter.love - 2.4MB)
- **Source Code**: [game/main.lua](https://github.com/MontaQLabs/sublua/blob/main/game/main.lua) (700+ lines)
- **How to Play**: [game/PLAY.md](https://github.com/MontaQLabs/sublua/blob/main/game/PLAY.md)
- **Build Guide**: [game/BUILD_GAME.md](https://github.com/MontaQLabs/sublua/blob/main/game/BUILD_GAME.md)
- **Build Yourself**: Run `./build_binaries.sh` to create all executables

### 💡 Code Examples
- **All Examples**: [examples/](https://github.com/MontaQLabs/sublua/tree/main/examples)
- **Basic Usage**: [examples/basic_usage.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/basic_usage.lua)
- **Multi-signature**: [examples/multisig_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/multisig_example.lua)
- **Proxy Accounts**: [examples/proxy_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/proxy_example.lua)
- **On-chain Identity**: [examples/identity_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/identity_example.lua)
- **WebSocket Management**: [examples/websocket_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/websocket_example.lua)
- **Game Integration**: [examples/game_integration.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/game_integration.lua)

---

## Summary: Addressing Reviewer Feedback

### ✅ Fixed: 404 Links
All links now point to correct paths in the main branch. Verified all documentation, code files, and release artifacts are accessible.

### ✅ Delivered: LuaRocks Package & Automated Distribution
- **LuaRocks Package**: Published at https://luarocks.org/modules/abhiraj-mengade/sublua
- **Automated Build Pipeline**: CI/CD workflow builds FFI binaries for 3 platforms
- **Cross-Platform Binaries**: macOS (aarch64, x86_64), Linux (x86_64) available in releases
- **Installation Scripts**: One-liner installer for all major operating systems
- **Zero-Configuration Install**: Users run `curl ... | bash` or `luarocks install sublua` - no manual path management required

### ✅ Delivered: Complete & Polished Game
- **Production-Ready Standalone App**: TreasureHunter.app for macOS (double-click to play)
- **Player Account Management**: Wallet UI with mnemonic input and real balance display
- **Token Economics**: Entry fees, play-to-earn rewards, treasury management
- **On-Chain Leaderboard**: Rankings persisted on Westend blockchain
- **Secure Transaction Handling**: 2-of-3 multisig treasury for prize distribution
- **Professional Aesthetics**: Neon cyberpunk theme with polished graphics
- **Self-Contained**: No external installations required - SubLua SDK bundled inside
- **Complete Documentation**: 925-line game development guide

### ✅ Delivered: Case Study Article
- **Technical Article**: [ARTICLE.md](https://github.com/MontaQLabs/sublua/blob/main/ARTICLE.md) (2,800+ words)
- **Architecture Decisions**: FFI design rationale, why LuaJIT, subxt integration strategy
- **Lessons Learned**: Real production deployment insights and challenges overcome
- **Performance Metrics**: Benchmarks for FFI calls, transaction submission, WebSocket connections
- **Real-World Application Showcase**: Complete walkthrough of Treasure Hunter game as case study

### ✅ Progress Since Milestone 1
**Massive progress beyond basic SDK:**
- 🔐 Advanced cryptography (multisig, proxy, identity)
- 🌐 WebSocket connection management
- 📦 Production distribution (LuaRocks + automated installer)
- 🎮 Complete production game with standalone executables
- 📚 925-line game development guide
- 🔒 Comprehensive security documentation
- 🚀 3 new major releases (v0.2.0, v0.3.0, v0.3.1)
- ✅ 42 passing tests on live networks
- 🛠️ Pre-commit hooks and CI/CD automation

**Installation is now truly effortless** - one command installs everything, no manual configuration needed! 🚀


