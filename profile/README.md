<p align="center">
  <img src="https://raw.githubusercontent.com/shukka-app/shukka/main/public/favicon.svg" width="72" height="72" alt="Shukka">
</p>

<h1 align="center">Shukka</h1>

<p align="center">
  <strong>Self-hosted updates for Electron and Tauri.</strong><br>
  Your bucket. Your feed. Your panel.
</p>

<p align="center">
  <a href="https://github.com/shukka-app/shukka">Product</a>
  ·
  <a href="https://github.com/shukka-app/docs">Docs</a>
  ·
  <a href="https://github.com/shukka-app/shukka/pkgs/container/shukka">Image</a>
  ·
  <a href="https://github.com/shukka-app/shukka/blob/main/LICENSE">MIT</a>
</p>

---

Shukka is a single-admin update service you run yourself. Create an app, point it at S3 / R2 / MinIO, and ship versions from CI. Installed Electron and Tauri clients keep using their own updater — they just read a public feed.

```bash
docker run -d --name shukka -p 3000:3000 -v shukka-data:/data ghcr.io/shukka-app/shukka
```

| | |
| --- | --- |
| **Storage** | Installers stay in *your* bucket. Shukka never proxies the bytes. |
| **Feed** | `electron-updater` and plugin-updater read `/api/update/{app}/{channel}` with no credentials. |
| **Drafts** | Uploads stay unpublished until you promote them. |
| **CI** | One GitHub Action publishes an `electron-builder` or Tauri output directory. |

### Repositories

| Repo | What it is |
| --- | --- |
| [`shukka`](https://github.com/shukka-app/shukka) | Panel, API, update feed, and the publish Action |
| [`docs`](https://github.com/shukka-app/docs) | Public documentation |
| [`monorepo`](https://github.com/shukka-app/monorepo) | Workspace that vendors the product and docs as submodules |
