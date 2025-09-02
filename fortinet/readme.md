# Přidání HunterShield feeds do FortiGate firewallu

Tento návod popisuje, jak nakonfigurovat FortiGate firewall pro využití threat security feedu ze vzdálené adresy:

```python
huntershield.hunterbox.cz/ips
```

---

## 1. Varianty přístupu

- **Pevná IP adresa** – klient nemá možnost použít autentizaci přes https.
- **Autentizace uživatel / heslo** – klient má dostupnou možnost autentize uživatelským jménem a heslem.

---

## 2. Konfigurace pomocí pevné IP

### Předpoklady

- Vaše veřejná IP adresa je zařazena na whitelistu feedu, je potřeba předat technickému oddělení služby HunterShield
- dostupnost IPs feedu: `http://huntershield.hunterbox.cz/ips`

### Postup

1. Přihlaste se do FortiGate GUI.
2. Přejděte do sekce **Security Fabric > External Feeds**.
3. Klikněte na **Create New > IP Address**.
4. Vyplňte následující údaje:

   - **Name:** HunterShield IP Feed
   - **Type:** IP Feed
   - **URL:** `http://huntershield.hunterbox.cz/ips`
   - **Authentication:** None
   - **Update Interval:** Nastavte dle potřeby (např. 1 hodina)

![Result_Link](https://github.com/domis-corp/huntershield/blob/main/fortinet/images/HunterShield-IPs-http.png)

5. Uložte konfiguraci.
6. Ověřte, že feed je aktivní a data jsou přijímána.

![Result_Link](https://github.com/domis-corp/huntershield/blob/main/fortinet/images/HunterShield-IPs-valid.png)

---

## 3. Konfigurace pomocí Basic Authentication (uživatel/heslo)

### Předpoklady

- Přístupová data (kontaktujte technické oddělení služby HunterShield) vám byla poskytnuta.
- URL feedu: `https://huntershield.hunterbox.cz/ips`

### Postup

1. Přihlaste se do FortiGate GUI.
2. Přejděte do sekce **Security Fabric > External Feeds**.
3. Klikněte na **Create New > IP Address**.
4. Vyplňte následující údaje:

   - **Name:** HunterShield IP Feed
   - **Type:** IP Feed
   - **URL:** `http://huntershield.hunterbox.cz/ips`
   - **Authentication:** Basic
   - **Username:** *uživatel*
   - **Password:** *heslo*
   - **Update Interval:** Nastavte dle potřeby (např. 1 hodina)

![Result_Link](https://github.com/domis-corp/huntershield/blob/main/fortinet/images/HunterShield-IPs-https.png)

5. Uložte konfiguraci.
6. Ověřte, že feed je aktivní a data jsou přijímána.

![Result_Link](https://github.com/domis-corp/huntershield/blob/main/fortinet/images/HunterShield-IPs-valid.png)

---

## 4. Kontakty a podpora

V případě problémů kontaktujte přes e-mail:

```python
help@hunterbox.cz
```

---
