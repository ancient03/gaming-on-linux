# Roblox

- **Platform / Store:** Sober (Flatpack)
- **Status Kompatibilitas:** 🟡 Gold
- **Tanggal Pengujian:** 2026-11-02

---

### ⚙️ Compability Tools
- **Proton / Wine Version:** -
- **Steam Play Compatibility:** -

---

### 🚀 Steam Launch Options

```bash

```


---

### 🛠️ Tweak Tambahan
Untuk GPU Nvidia lawas di sarankan mengubah konfigurasi sober supaya bisa lancar menggunakan Vulkan. Karena Pada GPU NVIDIA (seperti GTX 1650), menggunakan OpenGL di Sober sering kali menyebabkan penurunan performa/lag berat atau stuttering karena overhead penerjemahan.

1. Buka Terminal (Ctrl + Alt + T) Lalu ketik.

```bash
__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia flatpak run org.vinegarhq.Sober --gfx-api vulkan
```




---

### ⚠️ Masalah yang Ditemukan & Solusi
| Masalah | Penyebab | Solusi / Workaround |
| :--- | :--- | :--- | 
| Stuttering parah selama bermain di home | Graphic API Open GL | Ubah ke Vulkan Graphic API aseli Linux |

---

### 📝 Catatan Tambahan
- Setelah beberapa tweak game berjalan lancar tapi agak stutering di awal
