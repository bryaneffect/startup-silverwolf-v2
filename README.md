#  Stay Awake - Startup Silverwolf v2

**Personal Homepage Dashboard dengan Dark Mode & Animated Background**

Sebuah homepage modern yang interaktif dengan tema yang dapat disesuaikan, pencarian real-time, bookmark manager, dan animated shader background yang memukau.

---

## 📋 Daftar File

### 1. **index.html** 
File HTML utama yang berisi struktur keseluruhan aplikasi.

**Fitur Utama:**
- 🎨 **Responsive Layout** - Optimal untuk desktop dan mobile
- 🔍 **Live Search** - Integrasi dengan Wikipedia API untuk saran pencarian real-time
- 📌 **Bookmark Manager** - Simpan dan kelola bookmark dengan localStorage
- 🖼️ **Dynamic Banner** - Upload atau paste URL gambar banner
- ⚙️ **Settings Panel** - Menu pengaturan dengan animasi 3D
- 🌓 **Theme Toggle** - Switch antara dark dan light mode
- 📅 **Date & Time Display** - Menampilkan waktu saat ini dengan greeting dinamis
- 🎯 **Social Links** - Tautan ke GitHub, Instagram, TikTok, WhatsApp

**Struktur HTML:**
```
├── Shader Background (Canvas)
├── Settings Panel
│   ├── Settings Home (menu utama)
│   ├── Banner Image Section
│   └── Bookmarks Section
└── Main Content Card
    ├── Top Bar (Settings & Theme Toggle)
    ├── Breadcrumb
    ├── Banner Image
    ├── Greeting
    ├── Search Bar
    ├── Quick Links
    ├── Date & Time
    ├── Social Icons
    └── Footer Ticker
```

**Teknologi:**
- HTML5 Semantic
- Tailwind CSS (CDN)
- Vanilla JavaScript (ES6+)
- WebGL untuk Animated Background
- Local Storage API

---

### 2. **style.css**
File CSS yang berisi styling dan animasi untuk seluruh aplikasi.

**Bagian-bagian Utama:**

#### **Theme Variables**
```css
Light Mode:
--bg: #ede0ff (Soft Lavender)
--text-primary: #1b0f2d (Deep Purple)
--link-hover: #3a1660 (Dark Purple)

Dark Mode:
--bg: #020104 (Near Black)
--text-primary: #e4daf7 (Light Purple)
--link-hover: #c3a4f0 (Light Purple)
```

#### **Komponen Styling:**

**🎨 Main Card**
- `.bg-darkslide` - Glassmorphism background dengan blur effect
- Responsive padding dan sizing

**🔧 Settings Panel**
- `.settings-panel` - Panel dengan animasi 3D yang rotate dan scale
- `.settings-menu-item` - Menu item dengan hover effect
- `.settings-subview` - Sub-page dengan transisi slide

**🎯 3D Tile Effect**
- `.tile-3d` - Pseudo-3D effect pada search bar
- Menggunakan `perspective()` dan `rotateX/Y` untuk depth
- Smooth transition dengan `cubic-bezier(0.23, 1, 0.32, 1)`

**✨ Animasi:**
- `@keyframes lightTrail` - Animasi blinking footer
- Theme transition dengan duration 150ms
- Smooth property transitions

**📱 Media Queries:**
- Mobile overrides (max-width: 639px)
- Full-screen panel pada mobile
- Adjusted font sizes dan spacing

**🌐 Glassmorphism**
- `.glass` - Blur effect dengan backdrop-filter
- Box shadow dengan semi-transparent rgba

---

## 🚀 Fitur Utama

### 🔍 **Live Search**
- Fetch suggestions dari Wikipedia API
- Debounce input untuk optimasi
- Arrow key navigation support
- Auto-redirect ke Google Search

### 🖼️ **Banner Manager**
- Paste URL gambar langsung
- Upload gambar dari perangkat
- Preview real-time
- Simpan ke localStorage
- Reset ke gambar default

### 📌 **Bookmark Manager**
- CRUD (Create, Read, Update, Delete) bookmarks
- Simpan ke localStorage
- Edit nama dan URL inline
- Quick links display
- Empty state handling

### 🌓 **Theme System**
- Dark/Light mode toggle
- Persisten ke localStorage
- Smooth color transitions
- WebGL shader yang aware terhadap theme

### 📅 **Date & Time**
- Real-time update setiap 30 detik
- Greeting dinamis berdasarkan waktu:
  - Pukul 04:00-11:00 → Selamat pagi
  - Pukul 11:00-15:00 → Selamat siang
  - Pukul 15:00-19:00 → Selamat sore
  - Pukul 19:00-04:00 → Selamat malam
- Format tanggal Indonesia

### 🎨 **Animated Background**
- WebGL shader dengan halftone pattern
- Particle-like dot effect
- Cursor-aware distortion (3 mode)
- Dark mode: Deep purple palette
- Light mode: Soft lavender palette
- Responsive resolution scaling
- Performance optimized dengan visibility API

---

## 🛠️ Teknologi & Library

| Teknologi | Kegunaan |
|-----------|----------|
| **Tailwind CSS** | Utility-first CSS framework |
| **WebGL** | Animated background shader |
| **Local Storage** | Persist settings & bookmarks |
| **Wikipedia API** | Live search suggestions |
| **Poppins Font** | Typography dari Google Fonts |
| **ResizeObserver** | Responsive canvas handling |
| **IntersectionObserver** | Detect visibility |
| **MutationObserver** | Monitor DOM changes |

---

## 💾 Local Storage Keys

| Key | Deskripsi | Format |
|-----|-----------|--------|
| `theme` | Mode tema (dark/light) | String: "dark" \| "light" |
| `bannerImage` | URL gambar banner | String: URL |
| `bookmarks` | Daftar bookmark | JSON Array |

**Contoh Bookmarks:**
```javascript
[
  { name: "GitHub", url: "github.com" },
  { name: "Google", url: "google.com" }
]
```

---

## 📱 Responsive Design

**Breakpoint Utama:**
- **Mobile:** < 640px (sm)
  - Full-screen layout
  - Larger touch targets
  - Stacked panels
  
- **Desktop:** ≥ 640px
  - Centered card (max 720px)
  - Floating settings panel
  - Side-by-side elements

**Safe Area Support:**
- Notch-aware padding untuk device dengan notch

---

## 🎯 Kustomisasi

### Mengubah Warna Tema
Edit CSS variables di `:root` dan `html.dark`:
```css
:root {
    --bg: #ede0ff;
    --text-primary: #1b0f2d;
    --link-hover: #3a1660;
    /* ... lebih banyak */
}
```

### Mengubah Nama User
Di file `index.html`, cari:
```javascript
const USER_NAME = "Bryan";
```
Ganti "Bryan" dengan nama Anda.

### Mengubah Social Links
Cari section "Social icons" dan ubah `href` sesuai profil Anda.

### Mengubah Shader Parameter
Di bagian `SHARED` dalam WebGL initialization, ubah nilai untuk perubahan effect:
```javascript
const SHARED = {
    scale: 1.780,        // Ukuran pattern
    intensity: 0.190,    // Intensitas dot
    vignette: 0.600,     // Edge darkening
    // ... lebih banyak
};
```

---

## 🔌 API Integration

### Wikipedia Search API
```
GET https://en.wikipedia.org/w/api.php?action=opensearch&search={query}
```
- Limit: 8 hasil
- Debounce: 200ms
- CORS enabled

### Google Search Redirect
```
https://www.google.com/search?q={query}
```

---

## 🎭 Browser Support

- ✅ Chrome/Edge (latest)
- ✅ Firefox (latest)
- ✅ Safari (latest)
- ⚠️ IE (tidak didukung)

**Fitur WebGL:**
- Fallback jika WebGL tidak tersedia
- Canvas masih render meski WebGL gagal

---

## 📊 Performance Tips

1. **Canvas Resolution Scaling**
   - Auto-scale berdasarkan device pixel ratio
   - Max 2000000 pixel untuk optimasi

2. **Visibility Optimization**
   - Pause rendering jika tab tidak aktif
   - Resume saat tab aktif kembali

3. **Intersection Observer**
   - Pause ketika element tidak di viewport

4. **Debouncing**
   - Search input: 200ms debounce
   - Scroll events: throttled

---

## 🐛 Known Issues & Workarounds

| Issue | Workaround |
|-------|------------|
| Bookmark URL tidak auto-prefix `https://` | Manual tambahkan protocol |
| Banner image CORS error | Gunakan image dengan CORS enabled |
| WebGL tidak kompatibel | Shader background tidak muncul, tapi UI tetap berfungsi |

---

## 📝 Notes

- **Created by:** @exphert (original homepage)
- **Edited by:** @bryaneffect
- **Hosted by:** local host

---

## 🔗 Social Links

- GitHub: https://github.com/bryaneffect
- Instagram: https://instagram.com/bryannfx.os
- TikTok: https://tiktok.com/@bryann_fx
- WhatsApp: https://web.whatsapp.com/
---

## 📄 License

Private Repository

---

**Last Updated:** September 2, 2026
