# ClaudeDesktop-Config

更好的 Claude Code Desktop 配置。

- 禁用 Anthropic 遥测功能
- 禁用 Bootstrap 远程配置功能
- 禁用 OTLP 本地日志，已配置成 off
- 允许 .dxt / .mcpb 扩展及本地 MCP
- 内嵌 Claude 模型定义，解决官方模型显示不全的问题

## V1 配置

```json
{
  "inferenceProvider": "gateway",
  "inferenceGatewayBaseUrl": "https://xxxxxxxx",
  "inferenceCredentialKind": "static",
  "inferenceGatewayApiKey": "sk-xxxxxxxx",
  "modelDiscoveryEnabled": false,
  "inferenceModels": [
    { "name": "claude-3-5-haiku-20241022", "labelOverride": "Claude 3.5 Haiku", "anthropicFamilyTier": "haiku" },
    { "name": "claude-3-7-sonnet-20250219", "labelOverride": "Claude 3.7 Sonnet", "anthropicFamilyTier": "sonnet" },
    { "name": "claude-sonnet-4-20250514", "labelOverride": "Claude Sonnet 4", "anthropicFamilyTier": "sonnet" },
    { "name": "claude-sonnet-4-5-20250929", "labelOverride": "Claude Sonnet 4.5", "anthropicFamilyTier": "sonnet" },
    { "name": "claude-sonnet-4-6", "labelOverride": "Claude Sonnet 4.6", "anthropicFamilyTier": "sonnet", "supports1m": true },
    { "name": "claude-sonnet-5", "labelOverride": "Claude Sonnet 5", "anthropicFamilyTier": "sonnet", "supports1m": true },
    { "name": "claude-opus-4-20250514", "labelOverride": "Claude Opus 4", "anthropicFamilyTier": "opus" },
    { "name": "claude-opus-4-1-20250805", "labelOverride": "Claude Opus 4.1", "anthropicFamilyTier": "opus" },
    { "name": "claude-opus-4-5-20251101", "labelOverride": "Claude Opus 4.5", "anthropicFamilyTier": "opus" },
    { "name": "claude-opus-4-6", "labelOverride": "Claude Opus 4.6", "anthropicFamilyTier": "opus", "supports1m": true },
    { "name": "claude-opus-4-7", "labelOverride": "Claude Opus 4.7", "anthropicFamilyTier": "opus", "supports1m": true, "isFamilyDefault": true },
    { "name": "claude-opus-4-8", "labelOverride": "Claude Opus 4.8", "anthropicFamilyTier": "opus", "supports1m": true },
    { "name": "claude-fable-5", "labelOverride": "Claude Fable 5", "anthropicFamilyTier": "fable", "supports1m": true }
  ],
  "coworkEgressAllowedHosts": ["*"],
  "disableDeploymentModeChooser": true,
  "disableEssentialTelemetry": true,
  "disableNonessentialTelemetry": true,
  "disableNonessentialServices": true,
  "otlpDesktopLogLevel": "off",
  "disableAutoUpdates": true,
  "bootstrapEnabled": false,
  "isDesktopExtensionEnabled": true,
  "isDesktopExtensionSignatureRequired": false,
  "isLocalDevMcpEnabled": true
}
```

## v2

```json
{
  "$schemaVersion": 2,
  "inference": {
    "provider": "gateway",
    "baseUrl": "https://xxxxxxxx",
    "credential": {
      "kind": "static",
      "apiKey": "sk-xxxxxxxx"
    },
    "modelDiscoveryEnabled": false,
    "models": [
      { "name": "claude-3-5-haiku-20241022", "labelOverride": "Claude 3.5 Haiku", "anthropicFamilyTier": "haiku" },
      { "name": "claude-3-7-sonnet-20250219", "labelOverride": "Claude 3.7 Sonnet", "anthropicFamilyTier": "sonnet" },
      { "name": "claude-sonnet-4-20250514", "labelOverride": "Claude Sonnet 4", "anthropicFamilyTier": "sonnet" },
      { "name": "claude-sonnet-4-5-20250929", "labelOverride": "Claude Sonnet 4.5", "anthropicFamilyTier": "sonnet" },
      { "name": "claude-sonnet-4-6", "labelOverride": "Claude Sonnet 4.6", "anthropicFamilyTier": "sonnet", "supports1m": true },
      { "name": "claude-sonnet-5", "labelOverride": "Claude Sonnet 5", "anthropicFamilyTier": "sonnet", "supports1m": true },
      { "name": "claude-opus-4-20250514", "labelOverride": "Claude Opus 4", "anthropicFamilyTier": "opus" },
      { "name": "claude-opus-4-1-20250805", "labelOverride": "Claude Opus 4.1", "anthropicFamilyTier": "opus" },
      { "name": "claude-opus-4-5-20251101", "labelOverride": "Claude Opus 4.5", "anthropicFamilyTier": "opus" },
      { "name": "claude-opus-4-6", "labelOverride": "Claude Opus 4.6", "anthropicFamilyTier": "opus", "supports1m": true },
      { "name": "claude-opus-4-7", "labelOverride": "Claude Opus 4.7", "anthropicFamilyTier": "opus", "supports1m": true, "isFamilyDefault": true },
      { "name": "claude-opus-4-8", "labelOverride": "Claude Opus 4.8", "anthropicFamilyTier": "opus", "supports1m": true },
      { "name": "claude-fable-5", "labelOverride": "Claude Fable 5", "anthropicFamilyTier": "fable", "supports1m": true }
    ]
  },
  "workspace": {
    "allowedEgressHosts": ["*"]
  },
  "authentication": {
    "disableClaudeAiSignIn": true
  },
  "telemetry": {
    "disableEssential": true,
    "disableNonessential": true,
    "disableNonessentialServices": true
  },
  "otlp": {
    "desktopLogLevel": "off"
  },
  "autoUpdater": {
    "disable": true
  },
  "bootstrap": {
    "enabled": false
  },
  "extensions": {
    "enabled": true,
    "signatureRequired": false
  },
  "mcp": {
    "allowLocalDev": true
  }
}
```

## 参考

- [Configuration Reference](https://claude.com/docs/third-party/claude-desktop/configuration)
- [Configuration Changelog](https://claude.com/docs/third-party/claude-desktop/configuration-changelog)
- [Telemetry & Egress](https://claude.com/docs/third-party/claude-desktop/telemetry)
- [Data Storage](https://claude.com/docs/third-party/claude-desktop/data-storage)
- [Bootstrap v2 Schema (flat)](https://claude.com/docs/third-party/claude-desktop/schemas/bootstrap-config-v2.schema.json)

## License

MIT