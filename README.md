# 🖧 MSTP + HSRP/VRRP High Availability Lab in GNS3

Projekt przedstawia implementację **topologii wysokiej dostępności** w środowisku **GNS3** z wykorzystaniem **routerów Cisco 7200**, **przełączników Cisco IOU L2** oraz **hostów VPCS**.

W laboratorium pokazano mechanizmy redundancji zarówno w:

- **warstwie 2** z użyciem **MSTP**
- **warstwie 3** z użyciem **HSRP/VRRP**

Projekt obejmuje również **testy failover** oraz **analizę pakietów w Wiresharku**.

---

## 📌 Cel projektu

Głównym celem projektu było zaprojektowanie i przetestowanie sieci odpornej na awarie pojedynczych łączy i urządzeń.

Projekt obejmuje:

- implementację **MSTP** w celu zapewnienia redundancji w warstwie 2,
- implementację **HSRP/VRRP** w celu zapewnienia redundantnej bramy domyślnej,
- konfigurację **VLAN-ów** i łączy **trunk 802.1Q**,
- wykonanie **testów failover** dla przełączania i routingu,
- **analizę ruchu protokołów** w Wiresharku.

---

## 🧠 Wykorzystane technologie

- **GNS3**
- **Cisco 7200**
- **Cisco IOU L2**
- **VPCS**
- **MSTP**
- **HSRP / VRRP**
- **VLAN**
- **trunking 802.1Q**
- **Wireshark**

---

## 🏗️ Przegląd topologii

Topologia zawiera:

- **2 routery Cisco 7200**
- **2 przełączniki Cisco IOU L2**
- **2 hosty VPCS**
- redundantne łącza między przełącznikami
- łącza krzyżowe między routerami i przełącznikami
- opcjonalne połączenia **Cloud/NAT**

### Główne założenia
- każdy router jest połączony z oboma przełącznikami,
- przełączniki są połączone **dwoma równoległymi trunkami**,
- hosty pracują w osobnych VLAN-ach,
- urządzenia końcowe korzystają z **wirtualnej bramy dostarczanej przez HSRP/VRRP**.

---

## 🧪 Zakres testów

W projekcie wykonano następujące testy:

1. **Test komunikacji między hostami**
2. **Test failover MSTP** – aktywacja łącza zapasowego po wyłączeniu jednego aktywnego połączenia między przełącznikami
3. **Test failover HSRP/VRRP** – przejęcie ruchu przez router zapasowy po awarii routera aktywnego
4. **Analiza pakietów w Wiresharku** dla ruchu HSRP i MSTP

---

## 📷 Zawartość repozytorium

- [`docs/full-documentation.md`](docs/full-documentation.md) — pełna dokumentacja projektu
- [`docs/addressing-plan.md`](docs/addressing-plan.md) — adresacja i projekt logiczny
- [`docs/test-results.md`](docs/test-results.md) — wyniki testów failover
- [`configs/`](configs/) — konfiguracje urządzeń
- [`captures/`](captures/) — zrzuty z Wiresharka i analiza protokołów
- [`images/`](images/) — topologia i zrzuty diagnostyczne

---

## ✅ Najważniejsze rezultaty

- MSTP poprawnie blokuje redundantne łącza i aktywuje ścieżki zapasowe po awarii,
- HSRP/VRRP zapewnia ciągłą dostępność bramy domyślnej,
- sieć pozostaje operacyjna po awarii routera lub łącza,
- połączenie redundancji w warstwie 2 i 3 znacząco zwiększa dostępność sieci.

---

## 👤 Autor

**Błażej Osowski**
