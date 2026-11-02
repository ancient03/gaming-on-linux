# 🎮 Gaming on Linux - Dokumentasi & Catatan Kompatibilitas

Repositori dokumentasi dan catatan konfigurasi untuk menjalankan game Windows di Linux menggunakan Steam, Proton, Wine, dan berbagai tweak pendukung.

---

## 📁 Struktur Repositori

```text
gamingonlinux/
├── README.md               # Panduan utama, cheatsheet, dan indeks game
├── TEMPLATE.md             # File template kosong siap salin untuk game baru
└── games/                  # Folder catatan kompatibilitas per game (1 file per game)
    ├── apex-legends.md
    ├── baldurs-gate-3.md
    ├── cyberpunk-2077.md
    ├── elden-ring.md
    ├── gta-v.md
    ├── helldivers-2.md
    ├── monster-hunter-world.md
    ├── red-dead-redemption-2.md
    ├── skyrim-se.md
    └── the-witcher-3.md
```

---

## 📑 Indeks Game Teruji

| Game | Status | Runner Rekomendasi | Tautan Dokumentasi |
| :--- | :---: | :--- | :--- |
| **Cyberpunk 2077** | 🟢 Platinum | `GE-Proton9-x` / `Proton Experimental` | [Lihat Catatan](games/cyberpunk-2077.md) |
| **Elden Ring** | 🟢 Platinum | `Proton Experimental` / `Proton 9.0-x` | [Lihat Catatan](games/elden-ring.md) |
| **Apex Legends** | 🟢 Platinum | `Proton Experimental` | [Lihat Catatan](games/apex-legends.md) |
| **Baldur's Gate 3** | 🟢 Platinum | `Proton Experimental` (DX11) | [Lihat Catatan](games/baldurs-gate-3.md) |
| **Grand Theft Auto V** | 🟡 Gold | `GE-Proton9-x` | [Lihat Catatan](games/gta-v.md) |
| **The Witcher 3: Wild Hunt** | 🟢 Platinum | `GE-Proton9-x` / `Proton 9.0-x` | [Lihat Catatan](games/the-witcher-3.md) |
| **Helldivers 2** | 🟡 Gold | `Proton Experimental` | [Lihat Catatan](games/helldivers-2.md) |
| **Red Dead Redemption 2** | 🟡 Gold | `Proton 9.0-x` / `GE-Proton` (Vulkan) | [Lihat Catatan](games/red-dead-redemption-2.md) |
| **Monster Hunter: World** | 🟢 Platinum | `Proton 8.0-5` / `GE-Proton` | [Lihat Catatan](games/monster-hunter-world.md) |
| **Skyrim Special Edition** | 🟢 Platinum | `GE-Proton9-x` | [Lihat Catatan](games/skyrim-se.md) |

> *Catatan status:* 🟢 **Platinum** (Berjalan lancar tanpa hambatan) • 🟡 **Gold** (Perlu sedikit tweak sederhana) • 🟠 **Silver** (Dapat dimainkan namun ada bug kecil) • 🔴 **Borked** (Tidak dapat dimainkan).

---

## 📋 Template Dokumentasi Game

Gunakan template di bawah ini saat menambahkan game baru. Buat file baru di dalam folder `games/<nama-game>.md`:

```bash
cp TEMPLATE.md games/nama-game.md
```

### Format Template:

```markdown
# 🕹️ [Nama Game]

- **Platform / Store:** Steam / Heroic / Lutris / Bottles / Epic Games
- **App ID / URL:** [Tautan Steam Store atau ProtonDB]
- **Status Kompatibilitas:** 🟢 Platinum / 🟡 Gold / 🟠 Silver / 🔴 Borked
- **Tanggal Pengujian:** YYYY-MM-DD

---

### 🖥️ Spesifikasi Sistem Pengujian
- **Distro:** [Contoh: Arch Linux / Fedora 40 / Pop!_OS 22.04]
- **Kernel:** [Contoh: 6.8.9-zen1]
- **GPU & Driver:** [Contoh: AMD Radeon RX 6700 XT (Mesa 24.1) / NVIDIA RTX 3060 (Driver 550.78)]
- **Desktop Environment / Window Manager:** [Contoh: KDE Plasma 6 (Wayland) / GNOME 46 (X11)]

---

### ⚙️ Konfigurasi & Runner
- **Proton / Wine Version:** [Contoh: GE-Proton9-5 / Proton Experimental / Proton 8.0-5]
- **Steam Play Compatibility:** `Dicentang / Dipaksa (Force use of a specific compatibility tool)`

---

### 🚀 Steam Launch Options
\`\`\`bash
gamemoderun mangohud %command%
\`\`\`

---

### 🛠️ Tweak Tambahan (Jika Diperlukan)
- [ ] Install dependensi via Winetricks/Protontricks:
  \`\`\`bash
  protontricks [APP_ID] d3dcompiler_47 vcrun2019
  \`\`\`
- [ ] Ubah konfigurasi game (.ini / config):
  - Lokasi file: `~/.steam/steam/steamapps/compatdata/[APP_ID]/pfx/drive_c/...`
  - Perubahan: [Keterangan tweak]

---

### ⚠️ Masalah yang Ditemukan & Solusi
| Masalah | Penyebab | Solusi / Workaround |
| :--- | :--- | :--- |
| [Deskripsi kendala] | [Penyebab bug] | [Langkah perbaikan / launch options] |

---

### 📝 Catatan Tambahan
- Performa: [Catatan FPS rata-rata / stabilitas]
- Anti-Cheat: [Jika ada informasi terkait EAC / BattlEye]
```

---

## 🚀 Cheatsheet Steam Launch Options

Di Steam: Klik kanan Game ➔ **Properties** ➔ **General** ➔ Kolom **Launch Options**.

### 1. Optimasi & Monitoring Performa
```bash
# Mengaktifkan Feral GameMode (CPU performance governor):
gamemoderun %command%

# Menampilkan HUD overlay FPS, suhu, RAM, VRAM (MangoHud):
mangohud %command%

# Kombinasi GameMode + MangoHud:
gamemoderun mangohud %command%
```

### 2. Gamescope (Upscaling AMD FSR & Isolasi Resolusi)
```bash
# Render game 1080p lalu upscale ke 1440p dengan FSR:
gamescope -w 1920 -h 1080 -W 2560 -H 1440 -F fsr -- %command%

# Render 720p ke 1080p (cocok untuk GPU terintegrasi / low-end):
gamescope -w 1280 -h 720 -W 1920 -H 1080 -F fsr -- %command%

# Kunci framerate ke 60 FPS via gamescope:
gamescope -r 60 -- %command%

# Paksa mode borderless window:
gamescope -b -f -- %command%
```

### 3. Laptop Hybrid (Dual GPU Intel/AMD + NVIDIA)
```bash
# Menjalankan game pada dedicated GPU NVIDIA (Prime Offload):
__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia %command%

# Gabungan GPU NVIDIA + GameMode + MangoHud:
__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia gamemoderun mangohud %command%
```

### 4. DirectX & Stabilitas (DXVK / VKD3D)
```bash
# Matikan Esync (coba jika game crash saat loading):
PROTON_NO_ESYNC=1 %command%

# Matikan Fsync (coba jika game mengalami freeze/deadlock):
PROTON_NO_FSYNC=1 %command%

# Backend OpenGL (hanya untuk game DirectX lawas yang bermasalah di Vulkan):
PROTON_USE_WINED3D=1 %command%

# Optimasi shader pipeline GPU AMD (RADV Mesa):
RADV_PERFTEST=gpl %command%

# Override DLL kustom (misal ReShade, CET, mod loader):
WINEDLLOVERRIDES="dxgi=n,b" %command%
```

### 5. Debugging & Log Crash
```bash
# Membuat log Proton untuk melihat penyebab game crash:
PROTON_LOG=1 %command%
# File log otomatis disimpan di: ~/steam-[APP_ID].log
```

---

## 💻 Perintah Terminal Esensial

### 1. Instalasi Tool Gaming Pendukung
- **GameMode:**
  - Ubuntu/Debian: `sudo apt install gamemode`
  - Arch Linux: `sudo pacman -S gamemode lib32-gamemode`
  - Fedora: `sudo dnf install gamemode`
- **MangoHud & GOverlay:**
  - Arch Linux: `sudo pacman -S mangohud lib32-mangohud goverlay`
  - Flatpak: `flatpak install flathub org.freedesktop.Platform.VulkanLayer.MangoHud`
- **ProtonUp-Qt (Download GE-Proton):**
  - `flatpak install flathub net.davidotek.pupgui2`
- **Protontricks (Install DLL Windows / VCRedist):**
  - `flatpak install flathub com.github.Matoking.protontricks`

### 2. Diagnosa Driver & Vulkan
```bash
# Cek deteksi Vulkan dan nama GPU:
vulkaninfo --summary

# Cek GPU & driver kernel aktif:
lspci -k | grep -EA3 'VGA|3D'

# Cek status driver NVIDIA:
nvidia-smi
```

### 3. Lokasi & Reset Prefix Proton
```bash
# Direktori prefix game (C:\ virtual):
~/.steam/steam/steamapps/compatdata/[APP_ID]/pfx/

# Reset prefix game (hapus jika data prefix korup):
rm -rf ~/.steam/steam/steamapps/compatdata/[APP_ID]/
```

---

## 🛡️ Referensi Anti-Cheat
- [ProtonDB](https://www.protondb.com/) — Kompatibilitas game & tweak komunitas.
- [Are We Anti-Cheat Yet?](https://areweanticheatyet.com/) — Status dukungan game online multiplayer di Linux.
- Pastikan **Proton EasyAntiCheat Runtime** dan **Proton BattlEye Runtime** terinstal di Steam Library (Tools).
