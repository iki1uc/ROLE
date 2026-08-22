# ROLE – NC‑Rolle (Industrie‑6.0 Modul)

ROLE ist das Lage‑ und Funktionsmodul der Industrie‑6.0‑Architektur.
Es definiert die **Rolle**, die ein NC‑Objekt im System einnimmt:

- Bewegung
- Lage
- Aufgabe
- Kraftpunkt
- Segment‑Zuweisung

ROLE verbindet die Module  
**NC**, **NOel**, **SURE**, **ZEN**, **GEO.physik**, **GEO.geo**, **DYN**  
zu einer einheitlichen Funktionsrolle.

---

## NC‑Rolle

Eine NC‑Rolle besteht aus drei Schichten:

1. **Identität**  
2. **Geometrie**  
3. **Kraft**

Diese werden über folgende Module erzeugt:

- **NC.engine** → Bewegung & Kraft  
- **GEO.geo** → Segment‑Geometrie  
- **GEO.physik** → FIRE / WATER / ICE / OVERWATER  
- **DYN** → dynamische Achsen  
- **NOel** → Lage & Raum  
- **SURE** → Stand  
- **ZEN** → Neutralzone  

---

## Rolle‑Aufbau

ROLE erzeugt eine vollständige Funktionsrolle:

```js
{
  id: "NC‑ROLE",
  geo: GEOG.all(v),
  kraft: GEOP.cube(v),
  dyn: DYN.axis("role", v),
  stand: SURE(v),
  neutral: ZEN(v)
}
