# Přidání HunterShield feeds do FortiGate firewallu

Tento návod popisuje, jak nakonfigurovat FortiGate firewall pro využití threat security feedu ze vzdálené adresy:

```python
huntershield.hunterbox.cz/IPs
```

---

## 1. Varianty přístupu

- **Pevná IP adresa** – klient musí zajistit, že FortiGate firewall používá pevnou veřejnou IP adresu, která je na whitelistu na straně feedu. Tento způsob nevyžaduje autentizaci.
- **Autentizace uživatel / heslo** – pokud klient nemá pevnou IP, je možné použít Basic Authentication s uživatelským jménem a heslem.

---

## 2. Konfigurace pomocí pevné IP

### Předpoklady

- Vaše veřejná IP adresa je zařazena na whitelistu feedu.
- URL feedu: `http://huntershield.hunterbox.cz/IPs`

### Postup

1. Přihlaste se do FortiGate GUI.
2. Přejděte do sekce **Security Fabric > Fabric Connectors > External Feeds**.
3. Klikněte na **Create New**.
4. Vyplňte následující údaje:

   - **Name:** HunterShield Threat Feed
   - **Type:** HTTP Feed
   - **URL:** `http://huntershield.hunterbox.cz/IPs`
   - **Authentication:** None
   - **Update Interval:** Nastavte dle potřeby (např. 1 hodina)

5. Uložte konfiguraci.
6. Ověřte, že feed je aktivní a data jsou přijímána.

---

## 3. Konfigurace pomocí Basic Authentication (uživatel/heslo)

### Předpoklady

- Přístupová data (uživatelské jméno a heslo) vám byla poskytnuta.
- URL feedu: `http://huntershield.hunterbox.cz/IPs`

### Postup

1. Přihlaste se do FortiGate GUI.
2. Přejděte do sekce **Security Fabric > Fabric Connectors > External Feeds**.
3. Klikněte na **Create New**.
4. Vyplňte následující údaje:

   - **Name:** HunterShield Threat Feed (Authenticated)
   - **Type:** HTTP Feed
   - **URL:** `http://huntershield.hunterbox.cz/IPs`
   - **Authentication:** Basic
   - **Username:** *váš uživatel*
   - **Password:** *vaše heslo*
   - **Update Interval:** Nastavte dle potřeby (např. 1 hodina)

5. Uložte konfiguraci.
6. Ověřte, že feed je aktivní a data jsou přijímána.

---

## 4. Kontakty a podpora

V případě problémů kontaktujte:

- Email: help@hunterbox.cz

---

*Dokumentace je veřejná a slouží jako návod pro rychlé nastavení FortiGate firewallů.*
