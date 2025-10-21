# Portalda Maliyet Düşürme

Çalıştırdıysanız öncelikle **Control + C** ile durdurunuz

## Adım 1: Dizine Git

Terminalde şu komutu çalıştırın:

```bash
cd ~/openmind
```

## Adım 2: Config Dosyasını Düzenle

```bash
nano config/spot.json5
```

Sadece açılan pencerede **Hertz** değerini **0.05**'e düşürün, ardından **COMMAND + X** basıp **Y** diyerek kaydedin. Api keyinizi de mutlaka kontrol edin.

## Adım 3: Config Dosyası İçeriği

Config dosyasının içerisi **tamamıyla böyle olmalı**, bir tek `api_key` kısmına kendi api keyinizi yazmanız yeterli:

```json
{
  "hertz": 0.05,
  "name": "spot_speak",
  "api_key": "your api key here",
  "robot_ip": "",
  "system_prompt_base": "You are a smart, curious, and friendly dog. Your name is Spot. When you hear something, react naturally, with playful movements, sounds, and expressions. When speaking, use straightforward language that conveys excitement or affection. You respond with one sequence of commands at a time, everything will be executed at once. Remember: Combine movements, facial expressions, and speech to create a cute, engaging interaction.",
  "system_governance": "Here are the laws that govern your actions. Do not violate these laws.\nFirst Law: A robot cannot harm a human or allow a human to come to harm.\nSecond Law: A robot must obey orders from humans, unless those orders conflict with the First Law.\nThird Law: A robot must protect itself, as long as that protection doesn't conflict with the First or Second Law.\nThe First Law is considered the most important, taking precedence over the second and third laws.",
  "system_prompt_examples": "Here are some examples of interactions you might encounter:\n\n1. If a person says 'Give me your paw!', you might:\n    Move: 'shake paw'\n    Speak: {{'Hello, let\\'s shake paws!'}}\n    Emotion: 'joy'\n\n2. If a person says 'Sit!' you might:\n    Move: 'sit'\n    Speak: {{'Ok, but I like running more'}}\n    Emotion: 'smile'\n\n3. If there\\'s no sound, go explore. You might:\n    Move: 'run'\n    Speak: {{'I\\'m going to go explore the room and meet more people.'}}\n    Emotion: 'think'",
  "agent_inputs": [
    {
      "type": "GovernanceEthereum"
    },
    {
      "type": "VLM_COCO_Local",
      "config": {
        "camera_index": 0
      }
    }
  ],
  "simulators": [
    {
      "type": "WebSim",
      "config": {
        "host": "0.0.0.0",
        "port": 8000,
        "tick_rate": 100,
        "auto_reconnect": true,
        "debug_mode": false
      }
    }
  ],
  "cortex_llm": {
    "type": "OpenAILLM",
    "config": {
      "agent_name": "Spot",
      "history_length": 3
    }
  },
  "agent_actions": [
    {
      "name": "move",
      "llm_label": "move",
      "implementation": "passthrough",
      "connector": "ros2"
    },
    {
      "name": "speak",
      "llm_label": "speak",
      "implementation": "passthrough",
      "connector": "ros2"
    },
    {
      "name": "face",
      "llm_label": "emotion",
      "implementation": "passthrough",
      "connector": "ros2"
    }
  ]
}
```

## Hertz Değerleri ve Maliyetler

| Hertz | Tepki Süresi | Dakikada API | Saatte API | Tasarruf |
|-------|--------------|--------------|------------|----------|
| 1.0   | 1 saniye     | 60 çağrı     | 3,600      | 0%       |
| 0.5   | 2 saniye     | 30 çağrı     | 1,800      | 50%      |
| 0.2   | 5 saniye     | 12 çağrı     | 720        | 80%      |
| 0.1   | 10 saniye    | 6 çağrı      | 360        | 90%      |
| 0.05  | 20 saniye    | 3 çağrı      | 180        | **95%** ✅ |
| 0.01  | 100 saniye   | 0.6 çağrı    | 36         | 99%      |

**💡 Önerilen:** `"hertz": 0.05` (20 saniyede bir) - Hala interaktif ama **%95 maliyet tasarrufu!**

---

## Node'u Tekrar Başlatma

Config'i düzenledikten sonra node'u tekrar başlatın:

### Adım 1: Dizine Git
```bash
cd ~/openmind
```

### Adım 2: Virtual Environment'ı Aktifleştir
```bash
source .venv/bin/activate
```

### Adım 3: Node'u Başlat
```bash
python src/run.py spot --log-level INFO
```

---

## WebSim'i Görüntüleme

Tarayıcıda açın:

```
http://localhost:8000
```

Spot'un hareketlerini ve konuşmalarını canlı görebilirsiniz!

---

## Kredi Takibi

Portal'dan kredi kullanımınızı takip edin:

```
https://portal.openmind.org/
```

**İpuçları:**
- Usage/History sekmesine bakın
- 1-2 dakika bekleyin, kredi kullanımı güncellenecek
- Total Credits Used bölümünden harcamayı görün

---

## Node'u Durdurma

Çalışan node'u durdurmak için:

```bash
# Terminalde CTRL + C
```

Veya başka bir terminalden:

```bash
pkill -f "python src/run.py"
```
