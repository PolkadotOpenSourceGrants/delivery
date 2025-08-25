# General Notes

App successfully boots:
```ts
npm start

> OpenGov Voting Tool@1.3.0 start
> node dist/app.js

[2025-08-25 20:17:41] INFO: Starting OpenGov Voting Tool v1.3.0
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "app"
    deepSyncLimit: 100
    deepSyncHour: 3
    refreshInterval: "900"
[2025-08-25 20:17:41] INFO: Waiting until the start minute...
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "app"
[2025-08-25 20:17:41] INFO: Waiting until start minute...
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
[2025-08-25 20:17:41] INFO: Waiting until START_MINUTE
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    waitTimeSeconds: 2580
    startMinute: 0
[2025-08-25 20:17:41] INFO: No ready proposals found.
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "mimir"
```
Docker build works:

```sh
docker-compose up --build
Creating network "votingtool_polkadot-voting-network" with driver "bridge"
Building polkadot-voting-tool
[+] Building 71.9s (21/21) FINISHED                                                                         docker:default
 => [internal] load build definition from Dockerfile                                                                  0.0s
 => => transferring dockerfile: 1.52kB                                                                                0.0s
 => [internal] load metadata for docker.io/library/node:18-alpine                                                     1.4s
 => [internal] load .dockerignore                                                                                     0.0s
 => => transferring context: 613B                                                                                     0.0s
 => [builder 1/8] FROM docker.io/library/node:18-alpine@sha256:8d6421d663b4c28fd3ebc498332f249011d118945588d0a35cb9b  3.5s
 => => resolve docker.io/library/node:18-alpine@sha256:8d6421d663b4c28fd3ebc498332f249011d118945588d0a35cb9bc4b8ca09  0.0s
 => => sha256:dd71dde834b5c203d162902e6b8994cb2309ae049a0eabc4efea161b2b5a3d0e 40.01MB / 40.01MB                      1.7s
 => => sha256:1e5a4c89cee5c0826c540ab06d4b6b491c96eda01837f430bd47f0d26702d6e3 1.26MB / 1.26MB                        0.5s
 => => sha256:8d6421d663b4c28fd3ebc498332f249011d118945588d0a35cb9bc4b8ca09d9e 7.67kB / 7.67kB                        0.0s
 => => sha256:929b04d7c782f04f615cf785488fed452b6569f87c73ff666ad553a7554f0006 1.72kB / 1.72kB                        0.0s
 => => sha256:ee77c6cd7c1886ecc802ad6cedef3a8ec1ea27d1fb96162bf03dd3710839b8da 6.18kB / 6.18kB                        0.0s
 => => sha256:f18232174bc91741fdf3da96d85011092101a032a93a388b79e99e69c2d5c870 3.64MB / 3.64MB                        0.3s
 => => extracting sha256:f18232174bc91741fdf3da96d85011092101a032a93a388b79e99e69c2d5c870                             0.1s
 => => sha256:25ff2da83641908f65c3a74d80409d6b1b62ccfaab220b9ea70b80df5a2e0549 446B / 446B                            0.6s
 => => extracting sha256:dd71dde834b5c203d162902e6b8994cb2309ae049a0eabc4efea161b2b5a3d0e                             1.5s
 => => extracting sha256:1e5a4c89cee5c0826c540ab06d4b6b491c96eda01837f430bd47f0d26702d6e3                             0.0s
 => => extracting sha256:25ff2da83641908f65c3a74d80409d6b1b62ccfaab220b9ea70b80df5a2e0549                             0.0s
 => [internal] load build context                                                                                     0.0s
 => => transferring context: 452.44kB                                                                                 0.0s
 => [builder 2/8] WORKDIR /app                                                                                        0.3s
 => [production 2/9] RUN apk add --no-cache dumb-init                                                                 1.0s
 => [builder 3/8] COPY backend/package*.json ./                                                                       0.0s
 => [builder 4/8] RUN npm ci                                                                                         13.7s
 => [production 3/9] RUN addgroup -g 1001 -S nodejs && adduser -S nodejs -u 1001                                      0.3s 
 => [production 4/9] WORKDIR /app                                                                                     0.0s 
 => [production 5/9] COPY backend/package*.json ./                                                                    0.0s 
 => [production 6/9] RUN npm ci --only=production && npm cache clean --force                                         12.8s
 => [builder 5/8] COPY backend/src ./src                                                                              0.0s
 => [builder 6/8] COPY backend/tsconfig.json ./                                                                       0.0s
 => [builder 7/8] COPY backend/jest.config.js ./                                                                      0.0s
 => [builder 8/8] RUN npm run build                                                                                   4.1s 
 => [production 7/9] COPY --from=builder /app/dist ./dist                                                             0.1s 
 => [production 8/9] COPY backend/public ./public                                                                     0.0s 
 => [production 9/9] RUN chown -R nodejs:nodejs /app                                                                 45.4s 
 => exporting to image                                                                                                2.6s 
 => => exporting layers                                                                                               2.6s 
 => => writing image sha256:f6536685023a2faa122932e5a2e305e061537795c08fda48b553a5ac6993bac2                          0.0s 
 => => naming to docker.io/library/votingtool_polkadot-voting-tool                                                    0.0s 
Creating votingtool_polkadot-voting-tool_1 ... done
Attaching to votingtool_polkadot-voting-tool_1
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.216Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"app","version":"1.3.0","deepSyncLimit":100,"deepSyncHour":3,"refreshInterval":"900","msg":"Starting OpenGov Voting Tool v1.3.0"}
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.217Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"app","msg":"Waiting until the start minute..."}
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.218Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"utils","msg":"Skipping wait until start minute..."}
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.220Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"app","msg":"Starting periodic referenda refresh..."}
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.224Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"app","version":"1.3.0","port":"3000","msg":"OpenGov Voting tool v1.3.0 is running on port 3000"}
polkadot-voting-tool_1  | {"level":30,"time":"2025-08-25T20:33:52.253Z","pid":7,"hostname":"ea957530839f","service":"VotingTool","version":"1.3.0","subsystem":"mimir","msg":"No ready proposals found."}
```
## Testing

Some unit tests currently failing.

<details>
    <summary>Output</summary>

```
npm test

> OpenGov Voting Tool@1.3.0 test
> jest

 FAIL  tests/integration/subscan.integration.test.ts (7.23 s)
  ● Subscan Integration Tests › API Integration › should successfully connect to Subscan APIs and return valid data structure

    Error checking Subscan: kusamaExtrinsics is not iterable

      296 |
      297 |   } catch (error: any) {
    > 298 |     throw new Error(`Error checking Subscan: ${error.message}`);
          |           ^
      299 |   }
      300 | }
      301 |

      at src/mimir/checkForVotes.ts:298:11
      at fulfilled (src/mimir/checkForVotes.ts:5:58)

  ● Subscan Integration Tests › API Integration › should handle real referendum IDs and return proper hash mapping

    Error checking Subscan: kusamaExtrinsics is not iterable

      296 |
      297 |   } catch (error: any) {
    > 298 |     throw new Error(`Error checking Subscan: ${error.message}`);
          |           ^
      299 |   }
      300 | }
      301 |

      at src/mimir/checkForVotes.ts:298:11
      at fulfilled (src/mimir/checkForVotes.ts:5:58)

  ● Subscan Integration Tests › Data Processing › should return valid extrinsic hash map structure

    Error checking Subscan: Request failed with status code 429

      296 |
      297 |   } catch (error: any) {
    > 298 |     throw new Error(`Error checking Subscan: ${error.message}`);
          |           ^
      299 |   }
      300 | }
      301 |

      at src/mimir/checkForVotes.ts:298:11
          at Generator.throw (<anonymous>)
      at rejected (src/mimir/checkForVotes.ts:6:65)

  ● Subscan Integration Tests › Data Processing › should handle empty referendum list gracefully

    Error checking Subscan: Request failed with status code 429

      296 |
      297 |   } catch (error: any) {
    > 298 |     throw new Error(`Error checking Subscan: ${error.message}`);
          |           ^
      299 |   }
      300 | }
      301 |

      at src/mimir/checkForVotes.ts:298:11
          at Generator.throw (<anonymous>)
      at rejected (src/mimir/checkForVotes.ts:6:65)

  ● Subscan Integration Tests › Data Processing › should handle non-existent referendum IDs gracefully

    Error checking Subscan: Request failed with status code 429

      296 |
      297 |   } catch (error: any) {
    > 298 |     throw new Error(`Error checking Subscan: ${error.message}`);
          |           ^
      299 |   }
      300 | }
      301 |

      at src/mimir/checkForVotes.ts:298:11
          at Generator.throw (<anonymous>)
      at rejected (src/mimir/checkForVotes.ts:6:65)

 FAIL  tests/unit/fetchReferendas.test.ts
  ● Polkassembly Unit Tests - fetchDataFromAPI › should handle API errors gracefully and return empty arrays

    Network Error

      106 |     const errorMessage = 'Network Error';
      107 |
    > 108 |     const axiosError = new Error(errorMessage);
          |                        ^
      109 |     (axiosError as any).isAxiosError = true;
      110 |     (axiosError as any).code = 'ECONNABORTED';
      111 |     (axios.get as jest.Mock).mockRejectedValueOnce(axiosError);

      at tests/unit/fetchReferendas.test.ts:108:24
      at tests/unit/fetchReferendas.test.ts:8:71
      at Object.<anonymous>.__awaiter (tests/unit/fetchReferendas.test.ts:4:12)
      at Object.<anonymous> (tests/unit/fetchReferendas.test.ts:102:80)

  ● Polkassembly Unit Tests - fetchDataFromAPI › should handle a null list of posts from the API and return empty arrays

    Invalid response structure from Polkassembly API for network Polkadot

      31 |     if (!response.data || !Array.isArray(response.data.posts)) {
      32 |       logError(logger, { network, responseData: response.data }, "Invalid response structure from Polkassembly API", ErrorType.INVALID_RESPONSE);
    > 33 |       throw new Error(`Invalid response structure from Polkassembly API for network ${network}`);
         |             ^
      34 |     }
      35 |
      36 |     const posts: PolkassemblyReferenda[] = response.data.posts;

      at src/polkAssembly/fetchReferendas.ts:33:13
      at fulfilled (src/polkAssembly/fetchReferendas.ts:5:58)

  ● Polkassembly Unit Tests - fetchDataFromAPI › should handle a response where the posts field is undefined and return empty arrays

    Invalid response structure from Polkassembly API for network Polkadot

      31 |     if (!response.data || !Array.isArray(response.data.posts)) {
      32 |       logError(logger, { network, responseData: response.data }, "Invalid response structure from Polkassembly API", ErrorType.INVALID_RESPONSE);
    > 33 |       throw new Error(`Invalid response structure from Polkassembly API for network ${network}`);
         |             ^
      34 |     }
      35 |
      36 |     const posts: PolkassemblyReferenda[] = response.data.posts;

      at src/polkAssembly/fetchReferendas.ts:33:13
      at fulfilled (src/polkAssembly/fetchReferendas.ts:5:58)

[2025-08-25 20:36:24] ERROR: Timeout fetching data from Polkassembly API
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "polkassembly"
    network: "Kusama"
    timeout: 10000
    type: "timeout"
[2025-08-25 20:36:24] ERROR: Invalid response structure from Polkassembly API
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "polkassembly"
    network: "Polkadot"
    responseData: {
      "posts": null
    }
    type: "invalidResponse"
[2025-08-25 20:36:24] ERROR: Unexpected error fetching data from Polkassembly API
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "polkassembly"
    network: "Polkadot"
    error: "Invalid response structure from Polkassembly API for network Polkadot"
[2025-08-25 20:36:24] ERROR: Invalid response structure from Polkassembly API
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "polkassembly"
    network: "Polkadot"
    responseData: {}
    type: "invalidResponse"
[2025-08-25 20:36:24] ERROR: Unexpected error fetching data from Polkassembly API
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "polkassembly"
    network: "Polkadot"
    error: "Invalid response structure from Polkassembly API for network Polkadot"
[2025-08-25 20:36:24] WARN: ⏳ Rate limited, retrying in 1066ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1066
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:25] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:25] WARN: ⏳ Rate limited, retrying in 2000ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 2000
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:27] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:27] WARN: ⏳ Rate limited, retrying in 1049ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1049
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:28] WARN: ⏳ Rate limited, retrying in 1005ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1005
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:29] WARN: ⏳ Rate limited, retrying in 2066ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 2066
    attempt: 2
    maxRetries: 2
[2025-08-25 20:36:31] INFO: ✅ Operation succeeded after 3 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 3
    operationType: "interactive"
[2025-08-25 20:36:31] WARN: ⏳ Rate limited, retrying in 1040ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1040
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:32] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:32] WARN: ⏳ Rate limited, retrying in 1095ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1095
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:34] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:34] WARN: ⏳ Rate limited, retrying in 1015ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1015
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:35] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:35] WARN: ⏳ Rate limited, retrying in 1084ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1084
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:36] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:36] WARN: ⏳ Rate limited, retrying in 1008ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1008
    attempt: 1
    maxRetries: 1
[2025-08-25 20:36:37] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:37] DEBUG: 🔄 Deduplicating operation
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationKey: "same-key"
 PASS  tests/unit/rate-limit-handler.test.ts (12.815 s)
[2025-08-25 20:36:39] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 25000
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:40] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 184665
    assetId: "1984"
    ticker: "USDT"
[2025-08-25 20:36:40] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 160800
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 500
    network: "Polkadot"
    usdValue: 3500
    rate: 7
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 500
    network: "Polkadot"
    usdValue: 3500
    rate: 7
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 250
    network: "Polkadot"
    usdValue: 1750
    rate: 7
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
[2025-08-25 20:36:42] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
 FAIL  tests/integration/mimir.integration.test.ts (27.54 s)
  ● Mimir Integration Tests › Kusama Transaction Submission › should successfully submit a vote transaction to sandbox Mimir

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Kusama Transaction Submission › should handle batch transactions in sandbox

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Kusama Transaction Submission › should successfully submit 20 related transactions to sandbox Mimir

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Kusama End-to-End Flow › should complete full voting cycle in sandbox

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Polkadot Transaction Submission › should successfully submit a vote transaction to sandbox Mimir

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Polkadot Transaction Submission › should handle batch transactions in sandbox

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Polkadot Transaction Submission › should successfully submit 20 related transactions to sandbox Mimir

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

  ● Mimir Integration Tests › Polkadot End-to-End Flow › should complete full voting cycle in sandbox

    HTTP error! status: 403 Forbidden

      84 |
      85 |     if (!response.ok) {
    > 86 |       throw new Error(
         |             ^
      87 |         `HTTP error! status: ${response.status} ${response.statusText}`
      88 |       );
      89 |     }

      at src/mimir/proposeVote.ts:86:13
      at fulfilled (src/mimir/proposeVote.ts:5:58)

[2025-08-25 20:36:44] WARN: ⏳ Rate limited, retrying in 106ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 106
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:45] WARN: ⏳ Rate limited, retrying in 208ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 208
    attempt: 2
    maxRetries: 2
[2025-08-25 20:36:45] INFO: ✅ Operation succeeded after 3 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 3
    operationType: "interactive"
[2025-08-25 20:36:45] WARN: ⏳ Rate limited, retrying in 211ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 211
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:45] WARN: ⏳ Rate limited, retrying in 429ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 429
    attempt: 2
    maxRetries: 2
[2025-08-25 20:36:45] INFO: ✅ Operation succeeded after 3 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 3
    operationType: "interactive"
[2025-08-25 20:36:45] DEBUG: 🔄 Deduplicating operation
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationKey: "same-key"
[2025-08-25 20:36:46] WARN: ⏳ Rate limited, retrying in 1000ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "interactive"
    delay: 1000
    attempt: 1
    maxRetries: 2
[2025-08-25 20:36:45] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 130000
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:47] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "interactive"
[2025-08-25 20:36:47] WARN: ⏳ Rate limited, retrying in 53ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "bulk"
    delay: 53
    attempt: 1
    maxRetries: 5
[2025-08-25 20:36:47] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "bulk"
[2025-08-25 20:36:47] WARN: ⏳ Rate limited, retrying in 50ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "bulk"
    delay: 50
    attempt: 1
    maxRetries: 5
[2025-08-25 20:36:47] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "bulk"
[2025-08-25 20:36:47] WARN: ⏳ Rate limited, retrying in 51ms
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    operationType: "bulk"
    delay: 51
    attempt: 1
    maxRetries: 5
[2025-08-25 20:36:46] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 15000
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:46] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 7653
    network: "Polkadot"
    usdValue: 53571
    rate: 7
 PASS  tests/integration/rate-limit-demo.test.ts
[2025-08-25 20:36:47] INFO: ✅ Operation succeeded after 2 attempts
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "rate-limit"
    attempt: 2
    operationType: "bulk"
[2025-08-25 20:36:47] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 495800
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:48] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 49
    network: "Polkadot"
    usdValue: 343
    rate: 7
 PASS  tests/integration/onchain.integration.test.ts
[2025-08-25 20:36:49] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 49
    network: "Polkadot"
    usdValue: 343
    rate: 7
 PASS  tests/integration/fetchReferendas.test.ts
[2025-08-25 20:36:50] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 5600
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:50] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 5600
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:50] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 5600
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:50] DEBUG: Calculated stablecoin reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    usdtAmount: 5600
    assetId: "1337"
    ticker: "USDC"
[2025-08-25 20:36:51] INFO: Successfully fetched and cached DOT/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    rate: 3.75
 PASS  tests/integration/coingecko.integration.test.ts
 PASS  tests/unit/utils.validation.test.ts
[2025-08-25 20:36:51] INFO: Successfully fetched and cached KSM/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    rate: 14.53
 PASS  tests/unit/network-deduplication.test.ts
 PASS  tests/integration/readyFileHandlers.integration.test.ts
 PASS  tests/unit/price-cache.test.ts
 PASS  tests/unit/rate-limit-config.test.ts
 PASS  tests/unit/utils.test.ts
[2025-08-25 20:36:51] INFO: Successfully fetched and cached DOT/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    rate: 10.5
[2025-08-25 20:36:51] ERROR: Error fetching DOT/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    error: "API Error"
[2025-08-25 20:36:51] INFO: Successfully fetched and cached DOT/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    rate: 10.5
[2025-08-25 20:36:51] INFO: Successfully fetched and cached KSM/USD rate
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    rate: 20.7
 PASS  tests/integration/polkassembly.content.test.ts (14.668 s)
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 500
    network: "Polkadot"
    usdValue: 3500
    rate: 7
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 500
    network: "Polkadot"
    usdValue: 3500
    rate: 7
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 250
    network: "Polkadot"
    usdValue: 1750
    rate: 7
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
[2025-08-25 20:36:52] DEBUG: Calculated native token reward
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "utils"
    nativeValue: 125
    network: "Polkadot"
    usdValue: 875
    rate: 7
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'res' -> object with constructor 'Object'
    --- property 'req' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
[2025-08-25 20:36:53] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 3608
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "84e10b88-1df3-48cc-a65c-d210ffab102a"
    }
[2025-08-25 20:36:53] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 4189
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "237f0efc-e2a6-474c-b001-1c5b58872477"
    }
[2025-08-25 20:36:53] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 6475
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "a2cddd0a-145c-4f07-a92e-1962672db2f7"
    }
[2025-08-25 20:36:54] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 11917
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "a127e8cd-d746-43f4-8a2d-06b8eb60a976"
    }
[2025-08-25 20:36:54] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 12345
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "body failed validation. Fix one:\nbody.parent.page_id should be defined, instead was `undefined`.\nbody.parent.database_id should be a valid uuid, instead was `\"invalid-database-id\"`.\nbody.parent.data_source_id should be defined, instead was `undefined`.\nbody.parent.workspace should be defined, instead was `undefined`.",
      "request_id": "8925cc49-233d-419f-8482-48579ca085c5"
    }
[2025-08-25 20:36:54] INFO: Starting referenda update
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    newStatus: "Deciding"
    newRequestedAmount: 100.5
    network: "Polkadot"
[2025-08-25 20:36:54] INFO: Updating properties
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    propertiesPayload: {
      "title": "Test Error Handling",
      "requestedAmount": 100.5,
      "referendumTimeline": "Deciding"
    }
[2025-08-25 20:36:54] ERROR: Referenda update failed
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "path failed validation: path.page_id should be a valid uuid, instead was `\"invalid-page-id\"`.",
      "request_id": "84346e9f-2f9a-409c-acf1-59e5e49cee55"
    }
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'parser' -> object with constructor 'Object'
    --- property 'socket' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'res' -> object with constructor 'Object'
    --- property 'req' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
[2025-08-25 20:37:03] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 8028
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "90fb1bc8-cb4f-4dc6-8e75-f21284dcddd3"
    }
[2025-08-25 20:37:03] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 10687
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "49b148f7-e9c2-4ab9-a1b9-31fcebe3bf2c"
    }
[2025-08-25 20:37:04] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 5740
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "58470a71-1160-45dd-a0bf-0dd09ed06f3a"
    }
[2025-08-25 20:37:04] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 6870
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "82b4cdc3-6145-4c35-b69b-11cec2b6426b"
    }
[2025-08-25 20:37:04] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 12345
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "body failed validation. Fix one:\nbody.parent.page_id should be defined, instead was `undefined`.\nbody.parent.database_id should be a valid uuid, instead was `\"invalid-database-id\"`.\nbody.parent.data_source_id should be defined, instead was `undefined`.\nbody.parent.workspace should be defined, instead was `undefined`.",
      "request_id": "b92cbdf8-c491-47f5-a313-a0e0ee690d90"
    }
[2025-08-25 20:37:04] INFO: Starting referenda update
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    newStatus: "Deciding"
    newRequestedAmount: 100.5
    network: "Polkadot"
[2025-08-25 20:37:04] INFO: Updating properties
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    propertiesPayload: {
      "title": "Test Error Handling",
      "requestedAmount": 100.5,
      "referendumTimeline": "Deciding"
    }
[2025-08-25 20:37:04] ERROR: Referenda update failed
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "path failed validation: path.page_id should be a valid uuid, instead was `\"invalid-page-id\"`.",
      "request_id": "a0f76e94-f94d-4db0-bc29-9ce7a448e17e"
    }
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'parser' -> object with constructor 'Object'
    --- property 'socket' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'res' -> object with constructor 'Object'
    --- property 'req' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
[2025-08-25 20:37:13] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 3805
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "0808b4f6-cb7c-4a38-bdc8-1bb126c4d219"
    }
[2025-08-25 20:37:14] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 5802
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "de518784-b0fb-41d3-965e-c252cd67060c"
    }
[2025-08-25 20:37:14] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 9059
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "4a18b46b-beb2-480b-ac22-daad9bcbba65"
    }
[2025-08-25 20:37:14] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 10220
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "e9abac68-53f1-4bae-a13e-e4b7ea9767a0"
    }
[2025-08-25 20:37:14] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 12345
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "body failed validation. Fix one:\nbody.parent.page_id should be defined, instead was `undefined`.\nbody.parent.database_id should be a valid uuid, instead was `\"invalid-database-id\"`.\nbody.parent.data_source_id should be defined, instead was `undefined`.\nbody.parent.workspace should be defined, instead was `undefined`.",
      "request_id": "180a5072-0d3a-4c7c-84dc-5a226ad6d79d"
    }
[2025-08-25 20:37:14] INFO: Starting referenda update
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    newStatus: "Deciding"
    newRequestedAmount: 100.5
    network: "Polkadot"
[2025-08-25 20:37:14] INFO: Updating properties
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    propertiesPayload: {
      "title": "Test Error Handling",
      "requestedAmount": 100.5,
      "referendumTimeline": "Deciding"
    }
[2025-08-25 20:37:14] ERROR: Referenda update failed
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "path failed validation: path.page_id should be a valid uuid, instead was `\"invalid-page-id\"`.",
      "request_id": "1947992d-e4ec-4577-8a59-8abce3e6f265"
    }
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'parser' -> object with constructor 'Object'
    --- property 'socket' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'res' -> object with constructor 'Object'
    --- property 'req' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
 FAIL  tests/integration/notion-connection.test.ts
  ● Test suite failed to run

    Jest worker encountered 4 child process exceptions, exceeding retry limit

      at ChildProcessWorker.initialize (node_modules/jest-worker/build/workers/ChildProcessWorker.js:181:21)

[2025-08-25 20:37:23] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 10621
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "fef284bb-1caf-4186-833b-a4b6de680d58"
    }
[2025-08-25 20:37:23] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 4767
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "262945ed-609b-497e-a7ec-b4d34f4c6ffe"
    }
[2025-08-25 20:37:23] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 10806
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "6ae39e71-2d3b-4dd3-8339-568845cccae2"
    }
[2025-08-25 20:37:23] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 8828
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 404,
      "code": "object_not_found",
      "message": "Could not find database with ID: 25aebbbc-8d54-80ac-ad78-c74fad1026a4. Make sure the relevant pages and databases are shared with your integration.",
      "request_id": "98f101c6-e121-49f1-af5a-fd210e232f28"
    }
[2025-08-25 20:37:23] ERROR: Error creating page
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    postId: 12345
    network: "Polkadot"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "body failed validation. Fix one:\nbody.parent.page_id should be defined, instead was `undefined`.\nbody.parent.database_id should be a valid uuid, instead was `\"invalid-database-id\"`.\nbody.parent.data_source_id should be defined, instead was `undefined`.\nbody.parent.workspace should be defined, instead was `undefined`.",
      "request_id": "81a0f2d1-d2cb-41ff-af9f-c7aec5e8c73e"
    }
[2025-08-25 20:37:23] INFO: Starting referenda update
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    newStatus: "Deciding"
    newRequestedAmount: 100.5
    network: "Polkadot"
[2025-08-25 20:37:23] INFO: Updating properties
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    propertiesPayload: {
      "title": "Test Error Handling",
      "requestedAmount": 100.5,
      "referendumTimeline": "Deciding"
    }
[2025-08-25 20:37:24] ERROR: Referenda update failed
    service: "VotingTool"
    version: "1.3.0"
    subsystem: "notion"
    pageId: "invalid-page-id"
    postId: 12345
    newTitle: "Test Error Handling"
    error: {
      "object": "error",
      "status": 400,
      "code": "validation_error",
      "message": "path failed validation: path.page_id should be a valid uuid, instead was `\"invalid-page-id\"`.",
      "request_id": "1a807cd8-9eef-4193-8eec-5b83ff2a02a9"
    }
node:internal/child_process/serialization:164
    const string = JSONStringify(message) + '\n';
                   ^

TypeError: Converting circular structure to JSON
    --> starting at object with constructor 'Object'
    |     property 'parser' -> object with constructor 'Object'
    --- property 'socket' closes the circle
    at stringify (<anonymous>)
    at writeChannelMessage (node:internal/child_process/serialization:164:20)
    at process.target._send (node:internal/child_process:851:17)
    at process.target.send (node:internal/child_process:751:19)
    at reportSuccess (/home/ubuntu/VotingTool/backend/node_modules/jest-worker/build/workers/processChild.js:82:11)

Node.js v24.6.0
 FAIL  tests/integration/notion.integration.test.ts
  ● Test suite failed to run

    Jest worker encountered 4 child process exceptions, exceeding retry limit

      at ChildProcessWorker.initialize (node_modules/jest-worker/build/workers/ChildProcessWorker.js:181:21)

Test Suites: 5 failed, 12 passed, 17 total
Tests:       16 failed, 98 passed, 114 total
Snapshots:   0 total
Time:        67.888 s
```
</details>
