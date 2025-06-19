# FortiGate – Přidání externího IP feedu (huntershield.hunterbox.cz)

Tento návod popisuje, jak přidat externí IP seznam z Huntershield do FortiGate pomocí External Connector.

## Požadavky

- FortiGate s firmwarem **6.4 nebo novějším**
- Přístup k webovému rozhraní FortiGate
- Přístup k IP feedu: `https://huntershield.hunterbox.cz/IPs.json`
- Uživatelské jméno a heslo pro přístup k feedu

## Omezující faktory FortiGate

- **FortiGate neumí zpracovat JSON** jako formát pro IP feedy – očekává čistý **textový seznam IP adres** (1 IP na řádek).
- **HTTP autentizace (Basic Auth)** není oficiálně podporována pro External Connectors ve většině verzí.

## Doporučené řešení

### 1. Převod feedu na čistý text

Pokud to je možné, připrav si URL, která poskytne IP adresy v čistém formátu `.txt`, např.:
