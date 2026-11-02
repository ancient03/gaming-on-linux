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
```bash
gamemoderun mangohud %command%
```

---

### 🛠️ Tweak Tambahan (Jika Diperlukan)
- [ ] Install dependensi via Winetricks/Protontricks:
  ```bash
  protontricks [APP_ID] d3dcompiler_47 vcrun2019
  ```
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
