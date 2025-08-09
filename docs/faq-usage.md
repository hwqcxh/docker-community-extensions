## FAQ Operational Examples and Usage

This section elaborates on examples from `faqs/README.md` with context and safe usage guidance.

### List Containers Associated with an Extension

Extensions’ containers share a common label (`com.docker.compose.project`). To list them via CLI:

```bash
docker container ls --filter "label=com.docker.compose.project=<your extension label>"
```

Find the exact label by inspecting the extension container:

```bash
docker inspect <container_id_or_name> | grep com.docker.compose.project -n
```

### Programmatic Listing via Docker Extensions SDK

Within an extension UI/backend using the Docker Extensions SDK, you can invoke Docker CLI through the client:

```ts
await ddClient.docker.cli.exec('container', [
  'ls',
  '--filter',
  'label=com.docker.compose.project=<your extension label>'
]);
```

- `ddClient` is the Extensions SDK client injected into your extension context
- Replace the label placeholder with your extension’s actual project label

### Port Exposure Best Practices

- Avoid hard-coding public host ports; prefer sockets as scaffolded by `docker extension init`.
- If ports are necessary, document collisions and configurability.

### Installation Version Pinning

To install a specific extension version via CLI:

```bash
docker extension install <publisher>/<extension>:<version>
# example
docker extension install foo/bar:0.0.1
```

Use semantic versions where provided.