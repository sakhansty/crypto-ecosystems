# Crypto Ecosystems (Dokumentasi Bahasa Indonesia)

**Crypto Ecosystems** adalah taksonomi proyek open source di bidang blockchain, web3, cryptocurrency, dan ekosistem terdesentralisasi beserta repositorinya. Dataset ini bersifat **tidak lengkap** dan akan terus berkembang, karena setiap hari selalu ada ekosistem dan repositori baru yang muncul.

## Cara Menggunakan Taksonomi

### 🖼️ Mode GUI
Anda dapat menggunakan *taxonomy viewer* di [crypto-ecosystems.xyz](https://crypto-ecosystems.xyz).  
Di sana Anda bisa mencari ekosistem/repo tertentu, serta mengekspor seluruh repositori dari ekosistem pilihan.

### 💻 Mode CLI
Untuk kebutuhan *data science*, taksonomi ini bisa diekspor ke format JSON menggunakan perintah:
```bash
./run.sh export exports.jsonl
```

Contoh mengekspor ekosistem tertentu (misalnya Bitcoin):
```bash
./run.sh export -e Bitcoin bitcoin.jsonl
```

Format ekspor berupa satu entri JSON per baris:
```json
{"eco_name":"Bitcoin","branch":["Lightning"],"repo_url":"https://github.com/alexbosworth/balanceofsatoshis","tags":["#developer-tool"]}
{"eco_name":"Bitcoin","branch":["Lightning"],"repo_url":"https://github.com/bottlepay/lnd","tags":[]}
```

---

## Cara Update Taksonomi

Perubahan dilakukan melalui *migration files* di folder `migrations/` dengan format:
```
migrations/YYYY-MM-DDThhmmss_deskripsi_migrasi
```

Contoh:
```
migrations/2009-01-03T181500_add_bitcoin
migrations/2015-07-30T152613_add_ethereum
```

---

## Format Data DSL

Contoh menambahkan ekosistem baru:
```lua
-- Menambahkan ekosistem
ecoadd Lightning

-- Menambahkan repositori ke ekosistem
repadd Lightning https://github.com/lightningnetwork/lnd #protocol

-- Menghubungkan ekosistem sebagai sub-ekosistem
ecocon Bitcoin Lightning
```

---

## Lisensi & Atribusi

Proyek ini menggunakan lisensi **MIT dengan atribusi**. Jika menggunakan dataset ini dalam proyek Anda, sertakan:

1. Sumber: “Electric Capital Crypto Ecosystems”  
2. Tautan: [https://github.com/electric-capital/crypto-ecosystems](https://github.com/electric-capital/crypto-ecosystems)  
3. Logo: [Logo resmi](static/electric_capital_logo_transparent.png)  

Contoh atribusi:
```
Data Source: Electric Capital Crypto Ecosystems
Jika Anda mengerjakan proyek open source crypto, submit repository Anda ke sini untuk dihitung.
```
