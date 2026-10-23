# JDownloader Reach

JDownloader Reach is an independent Windows desktop control shell for an already installed JDownloader engine. It is built with C#/.NET 10, Avalonia, and FluentAvalonia and targets Windows x86-64 and ARM64.

## Included

- JDownloader Reach 0.3.0 shell with local API state check, LinkGrabber link submission, a basic queue snapshot, start-download request, path persistence, and Save Logs ZIP.
- Resolver Reach as the companion DNS-over-HTTPS diagnostic app.
- Separate x86-64 and ARM64 Inno Setup installer scripts.
- A GitHub Actions workflow that publishes both native architectures and checks PE machine types before compiling installers.
- Source, third-party notices, and project-specific documentation.

## Not included

- The JDownloader Java engine. Install JDownloader separately.
- Ollama GGUF Importer. It is not integrated into or bundled with this project.

## Build and downloads

Push to main or run Actions → JDownloader Reach Windows installers → Run workflow. The workflow uploads separate x64 and ARM64 setup executables as Actions artifacts. Artifacts expire after 30 days; create a GitHub Release for durable downloads.

## Security boundary

The optional legacy JDownloader API client is fixed to `http://127.0.0.1:3128/`. This interface may be deprecated and unauthenticated. Never expose port 3128 to a LAN or the internet. The app does not open firewall ports or change Windows DNS settings.

## Current limitations

This is a control shell, not a Java-to-C# port or a complete replacement for JDownloader's native interface. Queue/API behavior must be checked against an installed JDownloader build; CI verifies compile/package correctness, not live API behavior.

See [docs/INTEGRATION-ARCHITECTURE.md](docs/INTEGRATION-ARCHITECTURE.md), [CHANGELOG.md](CHANGELOG.md), and [docs/PROJECT-MEMORY.md](docs/PROJECT-MEMORY.md).

The project is independent and is not affiliated with or endorsed by JDownloader or AppWork.
