# 🤖 OpenMind Fabric Portal'da Ilk Robotunuzu Olusturun

macOS ve Linux sistemlerinde OM1 ajanini kurmak ve dagitmak icin kapsamli rehber.

---

## 📋 Icindekiler
- [Gereksinimler](#-gereksinimler)
- [macOS Kurulumu](#-macos-kurulumu)
- [Linux Kurulumu](#-linux-kurulumu)
- [Dogrulama](#-dogrulama)
- [Sorun Giderme](#-sorun-giderme)
- [Sonraki Adimlar](#-sonraki-adimlar)

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

---

## 🔍 Sorun Giderme

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

---

## 🚀 Sonraki Adimlar

1. **API anahtarlarinizi yapilandirin** - OM1 projesinde
2. **Robot parametrelerinizi ayarlayin** - dokumantasyona gore
3. **Ilk ajaninizi calistirin** - saglanan betikleri kullanarak
4. **OpenMind Fabric Portal'a baglanin** - dagitiminizi izlemek icin

---

## 📚 Ek Kaynaklar

- [OpenMind Fabric Portal](https://openmind.com)
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

- `sudo` ile komut calistirirken sifreniz istenecektir
- Sifre yazarken karakterler gorunmez (guvenlik ozelligi)
- Kurulum sirasinda stabil internet baglantisi oldugundan emin olun
- Buyuk degisiklikler yapmadan once sisteminizi yedekleyin

---

## 💡 Ipuclari

- Terminal'de otomatik tamamlama icin `Tab` tusunu kullanin
- Onceki komutlari hatirlamak icin `↑` ok tusunu kullanin
- Sisteminizi ve paketlerinizi duzenli olarak guncel tutun

---

**OpenMind Toplulugu icin ❤️ ile yapildi**

*Destek ve sorulariniz icin lutfen resmi OpenMind dokumantasyonuna veya topluluk forumlarina basvurun.*
