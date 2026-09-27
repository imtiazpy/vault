# Ubuntu System Snapshot — Pre LTS Upgrade

> **Snapshot taken:** 2026-06-17  
> **Current OS:** Ubuntu 20.04.6 LTS (focal)  
> **Kernel:** 5.15.0-181-generic  
> **Desktop:** GNOME (ubuntu:GNOME)  
> **Target upgrade:** Latest LTS (Ubuntu 24.04 LTS as of 2026)  
> **User:** imtiapy (`write2pythonist@gmail.com`)

Use this note to rebuild your machine after upgrading Ubuntu. **Back up the items in [[#Critical backups before upgrading]] first — upgrading without backups is risky.**

---

## Critical backups before upgrading

Copy these to an external drive or cloud **before** you upgrade:

| What | Path | Notes |
|---|---|---|
| SSH keys & config | `~/.ssh/` | `id_ed25519`, `github-*`, `gitlab-*`, `gmbh-*`, `bz-matt`, `config` |
| GPG keys | `~/.gnupg/` | |
| Git config | `~/.gitconfig` | |
| Shell config | `~/.bashrc`, `~/.profile`, `~/.bash_aliases` | |
| Custom shell scripts | `~/Desktop/shellCommands/` | `.customCommands.sh`, `.site-status.sh` |
| Cursor / VS Code | `~/.cursor/`, `~/.config/Cursor/`, `~/.vscode/`, `~/.config/Code/` | Settings, keybindings, snippets |
| Docker data | `~/.docker/` | Images, credentials |
| Ollama models | `~/.ollama/` | **~4.6 GB** of models |
| Obsidian vault | `~/Desktop/vault/work.md/` | This vault |
| Projects | `~/Desktop/allProjects/` | All dev work |
| Documents | `~/Documents/` | Resume, certs, etc. |
| Downloads AppImages | `~/Downloads/Obsidian-1.12.7.AppImage` | |
| Virtualenvs | `~/.virtualenvs/` | 27 named envs — or recreate from project `requirements.txt` |
| Browser profiles | `~/.mozilla/`, `~/.config/google-chrome/` | Bookmarks, logins (export separately too) |
| PostgreSQL data | `/var/lib/postgresql/` | Versions 12, 13, 17 present on disk |
| NordVPN login | Re-login after install | |
| `.netrc`, API keys | `~/.netrc`, project `.env` files | **Never commit secrets** |

**Export package list now (run in terminal):**
```bash
apt-mark showmanual | sort > ~/Desktop/manual-packages-$(date +%F).txt
snap list > ~/Desktop/snap-packages-$(date +%F).txt
code --list-extensions > ~/Desktop/vscode-extensions-$(date +%F).txt
cursor --list-extensions > ~/Desktop/cursor-extensions-$(date +%F).txt
```

---

## Quick restore order (after fresh LTS install)

1. System update + build essentials
2. Restore `~/.ssh`, `~/.gitconfig`, shell dotfiles
3. Install browsers, editors (Chrome, Cursor, VS Code)
4. Install dev stack (git, nvm/node, Python, Docker, PostgreSQL, Redis, nginx)
5. Install snap apps + AppImages
6. Restore `~/.config/` app settings (or reconfigure)
7. Clone/restore projects from `~/Desktop/allProjects/`
8. Reinstall Cursor/VS Code extensions (lists below)
9. Restore Ollama models or re-pull
10. Re-enable systemd services you need

---

## Desktop environment

| Setting | Value |
|---|---|
| Session | Ubuntu GNOME |
| GNOME extensions (enabled) | `desktop-icons@csoriano`, `ubuntu-appindicators@ubuntu.com`, `ubuntu-dock@ubuntu.com` |
| Autostart apps | Remmina applet, Skype for Linux |
| Default terminal | Terminator (also have GNOME Terminal) |
| Wallpaper meta | `ubuntu-wallpapers` installed |

---

## GUI applications

### Installed via APT (manually selected)

| App | Package |
|---|---|
| Google Chrome | `google-chrome-stable` |
| Firefox (locale) | `firefox-locale-en` |
| VS Code | `code` |
| Cursor | `cursor` |
| Docker Desktop + Engine | `docker-ce`, `docker-ce-cli`, `docker-compose-plugin`, `docker-buildx-plugin`, `docker-desktop` |
| FileZilla | `filezilla` |
| LibreOffice (full suite) | via `ubuntu-desktop` + help packs |
| Thunderbird | + `thunderbird-locale-en`, `thunderbird-locale-en-us` |
| Terminator | `terminator` |
| Upwork | `upwork` |
| NordVPN | `nordvpn` |
| ngrok | `ngrok` |
| nginx | `nginx` |
| VLC | also via snap (see below) |
| GNOME Screenshot | `gnome-screenshot` |
| Network Manager OpenVPN | `network-manager-openvpn-gnome` |
| Ubuntu Desktop (meta) | `ubuntu-desktop`, `ubuntu-restricted-extras` |
| GDebi | `gdebi`, `gdebi-core` |

### Installed via Snap

```bash
sudo snap install btop
sudo snap install postman --channel=v8/stable    # v8.12.7
sudo snap install vlc
# Also present: canonical-livepatch, snap-store, modem-manager (system)
```

### AppImage / manual install

| App | Location / notes |
|---|---|
| Obsidian | `~/Downloads/Obsidian-1.12.7.AppImage` — config at `~/.config/obsidian` |
| Ollama | `/usr/local/bin/ollama` — install from https://ollama.com — models in `~/.ollama/` |

### Apps with config present (reinstall if needed)

These have folders under `~/.config/` — app may have been removed but settings remain. Reinstall after upgrade if you still use them:

- **LM Studio** — `~/.config/LM-Studio`
- **Zoom** — `~/.config/zoomus.conf`
- **Skype** — `~/.config/Skype`, autostart entry
- **Microsoft Edge** — `~/.config/microsoft-edge`
- **MongoDB Compass** — `~/.config/MongoDB Compass`
- **pgAdmin 4** — `~/.config/pgadmin`, `~/.config/pgadmin4`
- **OBS Studio** — `~/.config/obs-studio` (PPA was configured)
- **Krita** — `~/.config/kritarc` (PPA was configured)
- **Inkscape** — `~/.config/inkscape` (PPA was configured)
- **Blender** — `~/.config/blender`
- **Kazam** — `~/.config/kazam`
- **Remmina** — `~/.config/remmina`
- **TeamViewer** — `~/.config/teamviewer`
- **Indicator Sticky Notes** — `~/.config/indicator-stickynotes` (PPA was configured)
- **n8n** — `~/.n8n` (minimal data)
- **Netlify CLI config** — `~/.config/netlify`

---

## Third-party APT repositories (PPAs & external repos)

> **Important:** After upgrading to 24.04, many of these URLs must be updated from `focal` → `noble`. Do not blindly copy old repo files.

| Source | Purpose |
|---|---|
| `packages.microsoft.com` | VS Code, Edge |
| `dl.google.com/linux/chrome/deb` | Google Chrome |
| `download.docker.com/linux/ubuntu` | Docker |
| `deb.nodesource.com/node_14.x` | Node.js (also use nvm — see below) |
| `dl.yarnpkg.com/debian` | Yarn |
| `apt.postgresql.org` (pgdg) | PostgreSQL |
| `repo.mongodb.org` (6.0 focal) | MongoDB |
| `nginx.org/packages/mainline` | nginx mainline |
| `ngrok-agent.s3.amazonaws.com` | ngrok |
| `repo.nordvpn.com` | NordVPN |
| `repository.spotify.com` | Spotify |
| `ppa:deadsnakes/ppa` | Python 3.9–3.12 |
| `ppa:obsproject/obs-studio` | OBS Studio |
| `ppa:dimula73/krita` | Krita |
| `ppa:inkscape.dev/stable` | Inkscape |
| `ppa:umang/indicator-stickynotes` | Sticky Notes |
| `ppa:rabbitmq/rabbitmq-erlang` | RabbitMQ Erlang |
| `packagecloud.io/rabbitmq/rabbitmq-server` | RabbitMQ |
| `deb.anydesk.com` | AnyDesk (repo present, may be inactive) |
| `repo.skype.com` | Skype (repo present) |
| `ftp.postgresql.org/.../pgadmin4` | pgAdmin 4 |

---

## Manually installed APT packages (full list)

These are packages explicitly installed (not auto-installed as dependencies). This is your **primary apt restore list**:

```
apt-transport-https
autoconf
automake
build-essential
ca-certificates
cmake
code
containerd.io
curl
cursor
default-libmysqlclient-dev
docker-buildx-plugin
docker-ce
docker-ce-cli
docker-compose-plugin
docker-desktop
ffmpeg
filezilla
firefox-locale-en
fonts-indic
g++
gdebi
gdebi-core
git
git-lfs
gnome-screenshot
gnome-terminal
gnupg
gnupg2
google-chrome-stable
jq
language-pack-en
language-pack-en-base
language-pack-gnome-en
language-pack-gnome-en-base
libbz2-dev
libc6-dev
libdouble-conversion-dev
libevent-dev
libffi-dev
libgdbm-dev
libgflags-dev
libgoogle-glog-dev
liblz4-dev
liblzma-dev
libmysqlclient-dev
libncurses-dev
libncursesw5-dev
libpcre2-dev
libpq-dev
libreoffice-help-common
libreoffice-help-en-us
libsnappy-dev
libsodium-dev
libsqlite3-dev
libssl-dev
libtool
libxml2-dev
libxslt1-dev
libzstd-dev
linux-generic-hwe-20.04
make
mokutil
net-tools
network-manager-openvpn-gnome
nginx
ngrok
ninja-build
nmap
nodejs
nordvpn
openssh-server
pkg-config
postgresql-13
python3
python3-all-dev
python3-dev
python3-tk
python3-venv
python3.9
python3.9-venv
python3.10
python3.11
python3.12
redis-server
software-properties-common
sqlite3
terminator
texlive-latex-base
thunderbird-locale-en
thunderbird-locale-en-us
tk-dev
traceroute
tree
ubuntu-desktop
ubuntu-desktop-minimal
ubuntu-restricted-extras
ubuntu-standard
ubuntu-wallpapers
upwork
wget
wvdial
yarn
zlib1g-dev
zstd
```

**Bulk reinstall helper (after setting up repos on new Ubuntu):**
```bash
# Edit the list for 24.04 compatibility first, then:
xargs -a manual-packages.txt sudo apt install -y
```

---

## Development environment

### Node.js (via NVM)

| Item | Value |
|---|---|
| NVM dir | `~/.nvm` |
| Default version | **v18.14.2** |
| Installed versions | v16.15.1, v18.14.2, v18.18.2, v20.14.0, v22.22.2 |
| System node (apt) | Also installed via `nodejs` package (NodeSource 14.x repo) |

**Restore NVM:**
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
nvm install 18.14.2
nvm install 20.14.0
nvm install 22.22.2
nvm alias default 18.14.2
```

**Global npm packages (on v18.14.2):**
- `corepack`
- `expo-cli@6.3.10`
- `lighthouse@12.8.0`
- `pnpm@9.12.3`

**Global yarn packages:**
- `create-next-app@16.0.0`
- `create-vite@4.0.0`

### Python

| Version | Notes |
|---|---|
| 3.8.10 | System default (Ubuntu 20.04) |
| 3.9.5 | + venv support |
| 3.10.17 | via deadsnakes PPA |
| 3.11.12 | via deadsnakes PPA |
| 3.12.7 | via deadsnakes PPA |

**Python tooling (pip/poetry):**
- `poetry`, `pipenv`, `virtualenv`, `docker-compose` (pip)
- User pip tools in `~/.local/bin/`: `django-admin`, `wagtail`, `ipython`, `poetry`, `pipenv`, etc.

**Restore Python on 24.04:**
```bash
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.11 python3.12 python3.11-venv python3.12-venv python3-dev python3-venv
pip install poetry pipenv
```

### Docker

| Component | Version |
|---|---|
| Docker Engine | 28.0.4 |
| Docker Compose | v5.1.4 (plugin) |
| Docker Desktop | Installed |

**User groups:** `docker`, `lxd`

**Docker images present:**
- `mcp/youtube-transcript`
- `mcp/fetch`
- `mcp/brave-search`
- `mcp/obsidian`

**Compose project found:**
- `~/Desktop/allProjects/sovereign/docker-compose.yml`

### Databases & servers

| Service | Version | Enabled on boot |
|---|---|---|
| PostgreSQL | 13.20 (client/server) — dirs for 12, 13, 17 on disk | ✅ `postgresql.service` |
| Redis | 5.0.7 | ✅ `redis-server.service`, `redis.service` |
| nginx | 1.27.0 (mainline) | ✅ `nginx.service` |
| OpenSSH | server installed | ✅ `ssh.service`, `sshd.service` |
| Docker | | ✅ `docker.service`, `containerd.service` |
| NordVPN | | ✅ `nordvpnd.service` |

### Other dev tools (apt)

```
build-essential  cmake  git  git-lfs  ffmpeg  jq  nmap  tree
sqlite3  texlive-latex-base  openssh-server  net-tools  traceroute
autoconf  automake  libtool  pkg-config  ninja-build
# MySQL/Postgres dev headers: libmysqlclient-dev, libpq-dev, libsqlite3-dev
# Various -dev libs for compiling C/C++ extensions
```

### Git

```
user.name=Imtiaz Ahmed
user.email=write2pythonist@gmail.com
```

---

## VS Code extensions

```
alexcvzz.vscode-sqlite
bibhasdn.django-html
bradlc.vscode-tailwindcss
dawhite.mustache
eamodio.gitlens
esbenp.prettier-vscode
github.copilot
github.copilot-chat
mblode.pretty-formatter
mintlify.document
ms-python.autopep8
ms-python.debugpy
ms-python.isort
ms-python.python
ms-python.vscode-pylance
ms-python.vscode-python-envs
openai.chatgpt
redhat.vscode-yaml
ritwickdey.liveserver
s-nlf-fh.glassit
sidthesloth.html5-boilerplate
streetsidesoftware.code-spell-checker
tyriar.lorem-ipsum
wayou.vscode-todo-highlight
xabikos.reactsnippets
```

**One-liner restore:**
```bash
cat vscode-extensions.txt | xargs -L1 code --install-extension
```

---

## Cursor extensions

```
alexcvzz.vscode-sqlite
anysphere.cursorpyright
bibhasdn.django-html
bradlc.vscode-tailwindcss
dawhite.mustache
eamodio.gitlens
esbenp.prettier-vscode
mblode.pretty-formatter
mintlify.document
ms-python.autopep8
ms-python.debugpy
ms-python.isort
ms-python.python
redhat.vscode-yaml
ritwickdey.liveserver
s-nlf-fh.glassit
sidthesloth.html5-boilerplate
streetsidesoftware.code-spell-checker
tyriar.lorem-ipsum
wayou.vscode-todo-highlight
xabikos.reactsnippets
```

**One-liner restore:**
```bash
cat cursor-extensions.txt | xargs -L1 cursor --install-extension
```

---

## Shell customizations

**`~/.bashrc` additions:**
- Sources `~/Desktop/shellCommands/.customCommands.sh`
- Sources `~/Desktop/shellCommands/.site-status.sh`
- Loads NVM (`~/.nvm`)

**Aliases:** `ll`, `la`, `l`, `alert` (standard Ubuntu)

**User groups:** `sudo`, `docker`, `lxd`, `nordvpn`, `lpadmin`, `sambashare`, `plugdev`, `netdev`

---

## Cron jobs

```
* * * * * /home/$USER/test_script.sh
```

Script at `~/test_script.sh` appends timestamp to `~/script_log.log`. Disable or update after upgrade if no longer needed.

---

## Project directories

**Main workspace:** `~/Desktop/allProjects/`

```
agentic_workflow    AIW-Assessment      aliReza           client-proejcts
Docker-project      enterprise          ExamSystem        flask
github              git-shortcuts-scripts  HH             iCodeThis
ICT_Smart_Lab       imtiaz-bakar        mobile_games      next-learn
open-source         PET_IMS             saas              sample_projects
server              sharuf              SkillBox          sovereign
test-ai             UI-Design           vite              Wagtail
```

**Documents:** `~/Documents/` — Resume, books, certificates, AnyDesk folder, Lightshot, etc.

**Obsidian vault:** `~/Desktop/vault/work.md/`

**Largest projects by disk usage** (prioritize these in backups):

| Size | Project |
|---|---|
| 7.8 GB | `client-proejcts` |
| 1.7 GB | `Wagtail` |
| 1.6 GB | `open-source` |
| 1.1 GB | `HH` |
| 786 MB | `next-learn` |
| 737 MB | `github` |
| 629 MB | `SkillBox` |
| 475 MB | `sharuf` |
| 355 MB | `ICT_Smart_Lab` |
| 286 MB | `ExamSystem` |
| 253 MB | `Docker-project` |
| 66 MB | `enterprise` (includes `pet_ims`) |

---

## Python virtualenvs (`~/.virtualenvs/`)

```
app-ls7qZ6qu              app-obZR5C8O              app-pxzEWJMh
app-to06VIyv              app-WjyN6paV              backend-NRUOIjVc
boilerplate.tenz.in-CUartzbk  bzmatt.ch-bbw3Xy97     django_version-ZXJw18o_
eCommerce-Bu3XG04t        Ellipsis-Web-DKJO75jc     geschaeftsbericht.thalwil.ch-*
geschafts-PlL_N3h4        ICT_Smart_Lab-TbyD-vRT    img-restore-flask-y8JJADRY
medical_management-_a3OsWb5  multi-site-wagtail-i9ov1nxz  Tenzin-aJ5n37mw
tenz.in-U_oAP3no          test-ai-NqOJq-nr           thinker-tank.net-Ygg5H7x1
Today-8JuFt11l            trial-25d_ArEc             webtool7-0Ifl0lih
```

> Tip: Prefer recreating venvs from each project's `requirements.txt` / `poetry.lock` on the new OS rather than copying venv folders.

---

## AI / automation tools

| Tool | Status | Data location |
|---|---|---|
| Ollama | Installed (`/usr/local/bin/ollama`) | `~/.ollama/` (~4.6 GB) |
| LM Studio | Config present | `~/.config/LM-Studio`, `~/.lmstudio` |
| Claude | Config present | `~/.claude/`, `~/.claude.json` |
| Codex | Config present | `~/.codex/` |
| Gemini | Config present | `~/.gemini/` |
| n8n | Config present | `~/.n8n/` |
| Cursor | Installed | `~/.cursor/`, `~/.config/Cursor/` |

---

## Fonts (notable)

- `fonts-indic` (manual install)
- `fonts-noto-cjk`, `fonts-noto-color-emoji`
- `fonts-liberation`, `fonts-liberation2`
- `ttf-mscorefonts-installer` (Microsoft core fonts)
- Many Indic/regional fonts via `fonts-indic` meta

---

## Upgrade notes: 20.04 → 24.04 LTS

1. **Recommended path:** Upgrade 20.04 → 22.04 → 24.04 (do not skip LTS versions in-place).
2. **Alternative:** Fresh install 24.04 + restore from this note (often cleaner for dev machines).
3. **Replace after upgrade:**
   - `linux-generic-hwe-20.04` → HWE kernel meta for 24.04
   - All `focal` repo entries → `noble`
   - PostgreSQL 13 → consider upgrading to PG 16/17 on 24.04
   - Redis 5.0 → 24.04 ships newer Redis
   - NodeSource 14.x repo → use NVM instead (14 is EOL)
4. **Docker Desktop:** Reinstall from Docker's site for Noble.
5. **Python 3.8:** Not on 24.04 by default — migrate projects to 3.11+.
6. **Test cron job:** Remove the every-minute cron if it was only for testing.

---

## Post-upgrade verification checklist

- [ ] `git config --global --list` matches above
- [ ] `nvm use 18.14.2 && node -v` works
- [ ] `docker run hello-world` works
- [ ] `psql --version` and DB connections work
- [ ] `redis-cli ping` returns PONG
- [ ] `nginx -t` passes
- [ ] Chrome, Cursor, FileZilla, Terminator launch
- [ ] NordVPN connects
- [ ] SSH keys work (`ssh -T git@github.com`)
- [ ] Cursor/VS Code extensions restored
- [ ] Obsidian opens vault at `~/Desktop/vault/work.md`
- [ ] Ollama models work (`ollama list`)
- [ ] Open a project from `~/Desktop/allProjects/enterprise/pet_ims` and run it

---

## Related notes

- [[How to Get Clients for AI Services]]

---

*Generated automatically by system scan on 2026-06-17. Re-run the export commands in [[#Critical backups before upgrading]] before you actually upgrade to refresh this data.*
