# Evaluation

- **Status:** Accepted
- **Application Document:** https://github.com/PolkadotOpenSourceGrants/apply/blob/master/applications/sublua.md
- **Milestone:** 2


| Number | Deliverable | Accepted | Link | Notes |
|--------|-------------|------|-------|-------|
| **0a.** | **License** | <ul><li>[x] </li></ul> | [LICENSE](https://github.com/MontaQLabs/sublua/blob/main/LICENSE) | MIT License |
| **0b.** | **Documentation** | <ul><li>[x] </li></ul> | [README.md](https://github.com/MontaQLabs/sublua/blob/main/README.md)<br>[docs/API.md](https://github.com/MontaQLabs/sublua/blob/main/docs/API.md)<br>[docs/SECURITY.md](https://github.com/MontaQLabs/sublua/blob/main/docs/SECURITY.md)<br>[docs/GAME_DEVELOPMENT.md](https://github.com/MontaQLabs/sublua/blob/main/docs/GAME_DEVELOPMENT.md) |  |
| **0c.** | **Testing and Testing Guide** | <ul><li>[x] </li></ul> | [test/run_tests.lua](https://github.com/MontaQLabs/sublua/blob/main/test/run_tests.lua)<br>[test/test_user_api.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_user_api.lua)<br>[test/test_dynamic_metadata.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_dynamic_metadata.lua)<br>[test/test_advanced_crypto.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_advanced_crypto.lua)<br>[test/test_websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_websocket.lua) |  |
| **0d.** | **Docker** | <ul><li>[x] </li></ul> | N/A | Docker not applicable |
| **0e.** | **Article** | <ul><li>[x] </li></ul> | [ARTICLE.md](https://github.com/MontaQLabs/sublua/blob/main/ARTICLE.md) | |
| **1.** | **WebSocket Connection Management** | <ul><li>[x] </li></ul> | [sublua/websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/websocket.lua)<br>[polkadot-ffi-subxt/src/lib.rs](https://github.com/MontaQLabs/sublua/blob/main/polkadot-ffi-subxt/src/lib.rs)<br>[examples/websocket_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/websocket_example.lua)<br>[test/test_websocket.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_websocket.lua) |  |
| **2.** | **Advanced Cryptographic Features** | <ul><li>[x] </li></ul> | [sublua/multisig.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/multisig.lua)<br>[sublua/proxy.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/proxy.lua)<br>[sublua/identity.lua](https://github.com/MontaQLabs/sublua/blob/main/sublua/identity.lua)<br>[examples/multisig_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/multisig_example.lua)<br>[examples/proxy_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/proxy_example.lua)<br>[examples/identity_example.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/identity_example.lua)<br>[test/test_advanced_crypto.lua](https://github.com/MontaQLabs/sublua/blob/main/test/test_advanced_crypto.lua) |  |
| **3.** | **Production Game Example** | <ul><li>[x] </li></ul> | **🎮 Game Executables (Built Locally):**<br>• TreasureHunter-macOS.zip (34MB, standalone .app)<br>• TreasureHunter.love (2.4MB, cross-platform)<br>• Available via [Drive Link] or build locally<br><br>**Source Code:**<br>[game/main.lua](https://github.com/MontaQLabs/sublua/blob/main/game/main.lua) (700+ lines)<br>[game/conf.lua](https://github.com/MontaQLabs/sublua/blob/main/game/conf.lua)<br>[game/PLAY.md](https://github.com/MontaQLabs/sublua/blob/main/game/PLAY.md)<br>[game/GAME_README.md](https://github.com/MontaQLabs/sublua/blob/main/game/GAME_README.md)<br><br>**Build Guide:**<br>[game/BUILD_GAME.md](https://github.com/MontaQLabs/sublua/blob/main/game/BUILD_GAME.md) (Complete build instructions)<br><br>**Terminal Version:**<br>[examples/treasure_hunter_game.lua](https://github.com/MontaQLabs/sublua/blob/main/examples/treasure_hunter_game.lua) |  |
| **4.** | **SDK Packaging and Distribution** | <ul><li>[x] </li></ul> |**📦 LuaRocks Package:**<br>[https://luarocks.org/modules/abhiraj-mengade/sublua](https://luarocks.org/modules/abhiraj-mengade/sublua)<br>**🚀 Releases:**<br>[v0.3.1 (Latest)](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.1)<br>[v0.3.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.3.0)<br>[v0.2.0](https://github.com/MontaQLabs/sublua/releases/tag/v0.2.0)<br>[All Releases](https://github.com/MontaQLabs/sublua/releases)<br>**📝 Source:**<br>[sublua-0.3.1-1.rockspec](https://github.com/MontaQLabs/sublua/blob/main/sublua-0.3.1-1.rockspec)<br>[install_sublua.sh](https://github.com/MontaQLabs/sublua/blob/main/install_sublua.sh)<br>[.github/workflows/ci.yml](https://github.com/MontaQLabs/sublua/blob/main/.github/workflows/ci.yml)<br>[build_binaries.sh](https://github.com/MontaQLabs/sublua/blob/main/build_binaries.sh) |  |
| **5.** | **Security Audit and Hardening** | <ul><li>[x] </li></ul> | [docs/SECURITY.md](https://github.com/MontaQLabs/sublua/blob/main/docs/SECURITY.md) |  |

# General Notes

Overall the project has solid functionality and good test cov for core features. Thanks for adding the quick install script upon request!

Build notes:
- build_binaries.sh creates directories for multiple platforms but only builds for current
- download_ffi.sh attempts to download from GitHub releases but gets a 404 error

## Testing

A lot more unit tests this time, nice job! 48 tests passing. A couple suggestions:
- util.lua and extrinsic.lua lack dedicated test suites, consider adding
- test_installation.lua fails the FFI library test (4/5 passing)
- The test expects ffi.lib to be pre-loaded, but the library requires explicit initialization. Can either fix the test logic or update the installation process to auto-load the FFI library
- Most tests focus on happy paths. Consider adding tests for network failures, invalid inputs, malformed transactions, and timeout scenarios
- Test files contain hardcoded mnemonics and seeds (even if test accounts). Consider using env variables instead
