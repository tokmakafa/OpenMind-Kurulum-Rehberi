# 🤖 OpenMind Fabric Portal'da Ilk Robotunuzu Olusturun

macOS ve Linux sistemlerinde OM1 ajanini kurmak ve dagitmak icin kapsamli rehber.

---

## 📋 Icindekiler
- [Gereksinimler](#-gereksinimler)
- [API Key Alma](#-api-key-alma)
- [macOS Kurulumu](#-macos-kurulumu)
- [Linux Kurulumu](#-linux-kurulumu)
- [Robotu Calistirma](#-robotu-calistirma)
- [Dogrulama](#-dogrulama)
- [Sorun Giderme](#-sorun-giderme)

---

## 🔧 Gereksinimler

### macOS
- macOS (Apple Silicon veya Intel)
- Homebrew paket yoneticisi
- OpenMind API Anahtarlari (OpenMind Fabric Portal'dan edinin - yeni kullanicilar icin $5 kredi)

### Linux
- Ubuntu/Debian tabanli dagitim
- Sudo yetkilerine sahip terminal erisimi
- Internet baglantisi

---

## 🔑 API Key Alma

### Adim 1: OpenMind Fabric Portal'a Kayit Olun

1. [OpenMind Fabric Portal](https://fabric.openmind.com) adresine gidin
2. **Sign Up** butonuna tiklayin
3. Email adresiniz ve sifrenizle kayit olun
4. Email dogrulamasi yapin

### Adim 2: API Key Olusturun

1. Portal'a giris yapin
2. **Settings** veya **API Keys** bolumune gidin
3. **Create New API Key** butonuna tiklayin
4. API Key'inizi kopyalayin ve guvenli bir yere kaydedin

**Ornek API Key:**
```
om_1234567890abcdefghijklmnopqrstuvwxyz
```

**ONEMLI:** API Key'inizi kimseyle paylasmаyin! Bu anahtari kaybederseniz yenisini olusturmaniz gerekecek.

---

## 🍎 macOS Kurulumu

### Adim 1: Homebrew Kurulumu

Eger Homebrew yuklu degilse, Terminal'de su komutu calistirin:
```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Homebrew Kurulumunu Dogrulayın
```bash
brew --version
```

### Adim 2: PortAudio Kurulumu
```bash
brew install portaudio
```

### Adim 3: FFmpeg Kurulumu
```bash
brew install ffmpeg
```

### Adim 4: Rust Kurulumu
```bash
brew install rust
```

### Adim 5: UV Paket Yoneticisi Kurulumu
```bash
brew install uv
```

### Adim 6: OM1 Projesini Klonlayin
```bash
git clone https://github.com/OpenMindAGI/OM1.git
```

### Proje Dizinine Gecin
```bash
cd OM1
```

### Adim 7: Git Alt Modullerini Guncelleyin
```bash
git submodule update --init
```

### Adim 8: Sanal Ortam Olusturun
```bash
uv venv
```

### Adim 9: Kurulumu Calistirin
```bash
bash scripts/setup.sh
```

### Adim 10: .env Dosyasi Olusturun

OM1 klasorunun icinde `.env` dosyasi olusturun:
```bash
nano .env
```

### Adim 11: API Key'lerinizi Girin

Asagidaki satirlari kopyalayin ve `your_api_key_here` kismini yukarida aldiginiz gercek API key'inizle degistirin:
```
OPENMIND_API_KEY=your_api_key_here
ANTHROPIC_API_KEY=your_anthropic_key_here
```

**Ornek (Gercek key'lerinizle degistirin):**
```
OPENMIND_API_KEY=om_1234567890abcdefghijklmnopqrstuvwxyz
ANTHROPIC_API_KEY=sk-ant-1234567890abcdefghijklmnopqrstuvwxyz
```

### Adim 12: Dosyayi Kaydedin

- Kaydetmek icin: `Ctrl + O` basin
- Enter'a basin
- Cikmak icin: `Ctrl + X` basin

### Adim 13: .env Dosyasini Kontrol Edin
```bash
cat .env
```

API key'lerinizi gorebilmelisiniz.

---

## 🐧 Linux Kurulumu

### Adim 1: Sistemi Guncelleyin
```bash
sudo apt-get update
```

### Adim 2: PortAudio ve Python Gelistirme Paketlerini Kurun
```bash
sudo apt-get install portaudio19-dev python-all-dev -y
```

### Adim 3: FFmpeg Kurulumu
```bash
sudo apt-get install ffmpeg -y
```

### Adim 4: ALSA Araclarini Kurun
```bash
sudo apt-get install alsa-utils -y
```

### Ses Modulunu Yukleyin
```bash
sudo modprobe snd-dummy
```

### Adim 5: UV Yukleyicisini Indirin
```bash
wget https://astral.sh/uv/install.sh
```

### Yukleyiciyi Calistirilabilir Yapin
```bash
chmod +x install.sh
```

### UV Yukleyicisini Calistirin
```bash
./install.sh
```

### Adim 6: OM1 Deposunu Klonlayin
```bash
git clone https://github.com/OpenMindAGI/OM1.git
```

### Proje Dizinine Gecin
```bash
cd OM1
```

### Adim 7: Git Alt Modullerini Guncelleyin
```bash
git submodule update --init
```

### Adim 8: Sanal Ortam Olusturun
```bash
uv venv
```

### Adim 9: Kurulumu Calistirin
```bash
bash scripts/setup.sh
```

### Adim 10: .env Dosyasi Olusturun

OM1 klasorunun icinde `.env` dosyasi olusturun:
```bash
nano .env
```

### Adim 11: API Key'lerinizi Girin

Asagidaki satirlari kopyalayin ve `your_api_key_here` kismini yukarida aldiginiz gercek API key'inizle degistirin:
```
OPENMIND_API_KEY=your_api_key_here
ANTHROPIC_API_KEY=your_anthropic_key_here
```

**Ornek (Gercek key'lerinizle degistirin):**
```
OPENMIND_API_KEY=om_1234567890abcdefghijklmnopqrstuvwxyz
ANTHROPIC_API_KEY=sk-ant-1234567890abcdefghijklmnopqrstuvwxyz
```

### Adim 12: Dosyayi Kaydedin

- Kaydetmek icin: `Ctrl + O` basin
- Enter'a basin
- Cikmak icin: `Ctrl + X` basin

### Adim 13: .env Dosyasini Kontrol Edin
```bash
cat .env
```

API key'lerinizi gorebilmelisiniz.

---

## 🚀 Robotu Calistirma

### Sanal Ortami Aktif Edin
```bash
source .venv/bin/activate
```

Terminal'inizde `(.venv)` ifadesini gormelisiniz.

### Robotu Baslatin
```bash
python main.py
```

veya
```bash
uv run main.py
```

### Ilk Calistirmada

Robot ilk kez calistiginda sizden:
- Kullanici adi
- Robot ismi
- Ses tercihleri
- Dil secimi

gibi temel ayarlari yapmanizi isteyecek.

---

## ✅ Dogrulama

### Homebrew'i Kontrol Edin (macOS)
```bash
brew --version
```

### PortAudio'yu Kontrol Edin (macOS)
```bash
brew list portaudio
```

### FFmpeg'i Kontrol Edin
```bash
ffmpeg -version
```

### Cargo'yu Kontrol Edin (Rust)
```bash
cargo --version
```

### UV'yi Kontrol Edin
```bash
uv --version
```

### API Key'leri Kontrol Edin
```bash
cat .env
```

veya
```bash
echo $OPENMIND_API_KEY
```

---

## 🔍 Sorun Giderme

### API Key Hatasi: "API key not found"

**Cozum 1: .env dosyasini kontrol edin**
```bash
cd OM1
cat .env
```

Eger dosya bossa veya yoksa, yukaridaki adimlarla yeniden olusturun.

**Cozum 2: Ortam degiskenlerini manuel olarak ayarlayin**
```bash
export OPENMIND_API_KEY="om_1234567890abcdefghijklmnopqrstuvwxyz"
export ANTHROPIC_API_KEY="sk-ant-1234567890abcdefghijklmnopqrstuvwxyz"
```

### API Key Hatasi: "Invalid API key"

**Cozum:**
- OpenMind Portal'da API key'inizin aktif oldugunu kontrol edin
- API key'i dogru kopyaladiginizdan emin olun (bosluk veya ozel karakter olmamali)
- API key'in basinda/sonunda bosluk olmadigini kontrol edin
- Yeni bir API key olusturup tekrar deneyin

**Dogru format:**
```
OPENMIND_API_KEY=om_1234567890abcdefghijklmnopqrstuvwxyz
```

**Yanlis formatlar:**
```
OPENMIND_API_KEY = om_1234...  (esittir isaretinin etrafinda bosluk olmamali)
OPENMIND_API_KEY= om_1234...   (key'den once bosluk olmamali)
```

### .env Dosyasi Gorunmuyor
```bash
ls -la
```

Bu komutla gizli dosyalari gorebilirsiniz. Eger `.env` yoksa:
```bash
touch .env
nano .env
```

### macOS: Homebrew Komutu Bulunamadi
```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
```
```bash
eval "$(/opt/homebrew/bin/brew shellenv)"
```

### Izin Reddedildi Hatasi
```bash
sudo chmod +x install.sh
```

### Linux: Sistem Paketlerini Guncelleyin
```bash
sudo apt-get update
```
```bash
sudo apt-get upgrade
```

### Ses Cihazlarini Kontrol Edin
```bash
aplay -l
```

### Git Alt Modullerini Senkronize Edin
```bash
git submodule sync
```
```bash
git submodule update --init --recursive
```

### Python Sanal Ortam Aktif Edilemiyor
```bash
# Sanal ortami yeniden olusturun
rm -rf .venv
uv venv
source .venv/bin/activate
```

### nano Editoru Kullanimi

- **Yazmak:** Normal sekilde yazmaya baslayin
- **Kaydetmek:** `Ctrl + O` basin, sonra `Enter`
- **Cikmak:** `Ctrl + X` basin
- **Silmek:** `Ctrl + K` (tum satiri siler)
- **Aramak:** `Ctrl + W`

---

## 📚 Ek Kaynaklar

- [OpenMind Fabric Portal](https://fabric.openmind.com)
- [OpenMind Dokumantasyonu](https://docs.openmind.com)
- [Homebrew Dokumantasyonu](https://docs.brew.sh)
- [UV Dokumantasyonu](https://github.com/astral-sh/uv)

---

## 🤝 Katkida Bulunma

Katkilarinizi bekliyoruz! Sunlari yapabilirsiniz:
- Hata bildirme
- Yeni ozellik onerme
- Pull request gonderme
- Dokumantasyonu gelistirme

---

## 📝 Lisans

Bu rehber egitim amacli olarak saglanmaktadir.

---

## ⚠️ Onemli Notlar

- **API Key'lerinizi asla GitHub'a yuklemeyin!**
- `.env` dosyasini `.gitignore` dosyaniza ekleyin
- API key'lerinizi kimseyle paylasmаyin
- `sudo` ile komut calistirirken sifreniz istenecektir
- Sifre yazarken karakterler gorunmez (guvenlik ozelligi)
- Kurulum sirasinda stabil internet baglantisi oldugundan emin olun
- Buyuk degisiklikler yapmadan once sisteminizi yedekleyin

---

## 💡 Ipuclari

- Terminal'de otomatik tamamlama icin `Tab` tusunu kullanin
- Onceki komutlari hatirlamak icin `↑` ok tusunu kullanin
- Sisteminizi ve paketlerinizi duzenli olarak guncel tutun
- API key'lerinizi duzenli olarak yenileyin
- Test ortami icin ayri bir API key kullanin
- `.env` dosyasini yedekleyin ama guvenli bir yerde saklayin

---

## 🎯 Hizli Baslangic Ozeti

### macOS:
1. ✅ OpenMind Portal'dan API key alin
2. ✅ Homebrew yukleyin
3. ✅ `brew install portaudio ffmpeg rust uv`
4. ✅ `git clone https://github.com/OpenMindAGI/OM1.git`
5. ✅ `cd OM1`
6. ✅ `git submodule update --init`
7. ✅ `uv venv`
8. ✅ `bash scripts/setup.sh`
9. ✅ `nano .env` (API key'leri girin)
10. ✅ `source .venv/bin/activate`
11. ✅ `python main.py`

### Linux:
1. ✅ OpenMind Portal'dan API key alin
2. ✅ `sudo apt-get update`
3. ✅ `sudo apt-get install portaudio19-dev python-all-dev ffmpeg alsa-utils -y`
4. ✅ UV yukleyin (wget + install.sh)
5. ✅ `git clone https://github.com/OpenMindAGI/OM1.git`
6. ✅ `cd OM1`
7. ✅ `git submodule update --init`
8. ✅ `uv venv`
9. ✅ `bash scripts/setup.sh`
10. ✅ `nano .env` (API key'leri girin)
11. ✅ `source .venv/bin/activate`
12. ✅ `python main.py`

---

**OpenMind Toplulugu icin ❤️ ile yapildi**

*Destek ve sorulariniz icin lutfen resmi OpenMind dokumantasyonuna veya topluluk forumlarina basvurun.*
