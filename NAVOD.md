# Nostalgický kvíz 90s/00s — návod ke spuštění

## Co potřebuješ
- Soubor `index.html` (přiložený)
- Notebook nebo PC ve stejné WiFi jako TV
- TV s webovým prohlížečem (LG WebOS 2014+, Samsung Tizen, Android TV)

## Postup

### 1. Spusť lokální server ve složce s `index.html`

Otevři **PowerShell** (Windows) nebo **Terminal** (Mac/Linux) v té složce a zkus
jednu z těchto možností podle toho, co máš nainstalované — stačí, aby fungovala
**jedna**:

**Python** (nejčastější — má ho většina lidí):
```
python -m http.server 8000
```
Pokud `python` nefunguje, zkus `python3` nebo `py`.

**Node.js** (alternativa):
```
npx -y http-server -p 8000
```

**PHP** (alternativa):
```
php -S 0.0.0.0:8000
```

Server musí zůstat běžet po celou dobu hry — okno terminálu nech otevřené.

### 2. Zjisti IP adresu počítače

**Windows** v PowerShellu:
```
ipconfig
```
Najdi řádek `IPv4 Address` pod tvojí WiFi adaptérem (typicky `192.168.x.x`).

**Mac**:
```
ipconfig getifaddr en0
```

**Linux**:
```
hostname -I
```

### 3. Otevři kvíz na televizi

Na TV spusť **Web Browser** a do adresního řádku napiš:

```
http://TVOJE_IP:8000
```

Příklad: `http://192.168.1.42:8000`

### 4. Hraj!

Aplikace ti nabídne **Setup hráčů** — vyplň jména (1–6 hráčů), klikni „Začít hru".
Klikej Magic Remotem (LG) nebo dálkem.

---

## Když to nejede

**`python: command not found` / `python není rozpoznán`**  
→ Stáhni si Python z [python.org](https://python.org). Při instalaci **zaškrtni
„Add Python to PATH"**, jinak ho terminál nenajde.

**TV se nepřipojí na zadanou adresu**  
→ Ověř, že notebook i TV jsou na **stejné WiFi** (ne host/guest síť).  
→ **Firewall** Windowsu může blokovat port 8000 — při prvním spuštění serveru
se objeví dialog „Povolit / Blokovat", dej **Povolit**.  
→ Otestuj si nejdřív sám v prohlížeči notebooku: `http://localhost:8000` —
pokud to tam funguje, ale ne na TV, je to síť nebo firewall.

**TV nemá webový prohlížeč**  
→ LG: stáhni v *LG Content Store* aplikaci „Web Browser".  
→ Samsung: hledej v aplikacích „Internet".  
→ Pokud opravdu nejde, jediná alternativa je **Miracast / Screen Share**
z notebooku (Windows: `Win + K`).

---

## Pravidla hry (zkráceně)

- 6 kategorií × 9 otázek (8 + bonusová) = 54 otázek
- Body 100 → 500 podle obtížnosti, bonus ±500
- **Fáze 1 (Sběr)**: aplikace ukáže postupně všech 9 otázek, hráči si píšou
  odpovědi na papír (každý sám!)
- **Fáze 2 (Vyhodnocení)**: po 5s odpočtu se odhalí každá odpověď, klikneš
  ✅/❌ ke každému hráči
- Vítězí ten s nejvyšším součtem skóre po všech kategoriích
