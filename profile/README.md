<p align="center">
  <img src="https://raw.githubusercontent.com/shukka-app/shukka/main/public/favicon.svg" width="72" height="72" alt="Shukka">
</p>

<h1 align="center">Shukka</h1>

<p align="center">
  <strong>Self-hosted updates for Electron and Tauri.</strong><br>
  Your bucket. Your feed. Your panel.
</p>

<p align="center">
  自行托管桌面应用的自动更新。<br>
  安装包装进你自己的对象存储，由面板决定何时向用户开放新版本。
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

Shukka 是单管理员的自托管更新服务。创建应用、接上 S3 / R2 / MinIO，再从 CI 发版。已安装的 Electron / Tauri 客户端继续用原来的更新器，只是改为读取一条公开 feed。

```bash
docker run -d --name shukka -p 3000:3000 -v shukka-data:/data ghcr.io/shukka-app/shukka
```

| | English | 中文 |
| --- | --- | --- |
| **Storage** | Installers stay in *your* bucket. Shukka never proxies the bytes. | 安装包留在你自己的 bucket。Shukka 不中转字节。 |
| **Feed** | `electron-updater` and plugin-updater read `/api/update/{app}/{channel}` with no credentials. | `electron-updater` 与 plugin-updater 无凭证读取 `/api/update/{app}/{channel}`。 |
| **Drafts** | Uploads stay unpublished until you promote them. | 上传后默认是草稿，确认后才对用户可见。 |
| **CI** | One GitHub Action publishes an `electron-builder` or Tauri output directory. | 一个 GitHub Action 发布 `electron-builder` 或 Tauri 产物目录。 |

### Repositories

| Repo | What it is |
| --- | --- |
| [`shukka`](https://github.com/shukka-app/shukka) | Panel, API, update feed, and the publish Action |
| [`docs`](https://github.com/shukka-app/docs) | Public documentation (fumadocs, zh-CN / en-US) |
| [`monorepo`](https://github.com/shukka-app/monorepo) | Workspace that vendors the product and docs as submodules |
