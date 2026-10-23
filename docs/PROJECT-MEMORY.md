# JDownloader Reach — project memory

## Project identity
- Current product version: 0.3.0 (assembly/file version 0.3.0.0).
- Stack: C# / .NET 10, Avalonia, FluentAvalonia.
- Targets: Windows x86-64 (win-x64) and ARM64 (win-arm64).
- Main app: src/JDownloaderReach/.
- Bundled companion: src/ResolverReach/.
- CI packaging: .github/workflows/jdownloader-reach.yml.
- Installers: installer/JDownloaderReach-x64.iss and installer/JDownloaderReach-arm64.iss.

## Current behavior
Launch a user-selected JDownloader2.exe; check the optional local API; submit links to LinkGrabber; display a basic package snapshot; request that queued downloads start; launch Resolver Reach; persist executable paths in %LOCALAPPDATA%\JDownloaderReach\settings.json; export logs and runtime metadata to ZIP.

## Explicit exclusions
Ollama GGUF Importer is not integrated and is not bundled. It is outside this repository. JDownloader's Java engine is not bundled and must be installed separately.

## Security
The optional API URL is fixed to http://127.0.0.1:3128/. It may be deprecated/unauthenticated. Never expose the port externally. Do not accept remote API hosts without a proper security redesign.

## Build verification baseline
The cleaned 0.3.0 build passed both architectures in workflow run 39946624955, commit b86b6743c1d8da8e597bd9e3cbf10dcecfe35305. That workflow validated native PE machine types, compiled both Inno Setup installers and uploaded artifacts. It did not test a physical-device installation or live JDownloader API integration.

## Licensing
JDownloader's engine is not copied or redistributed. The control-shell source is documented as MIT-licensed by the source project; Resolver Reach third-party notices remain applicable. Audit source/binary licenses before any future engine bundling.
