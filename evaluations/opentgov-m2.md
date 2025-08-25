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
