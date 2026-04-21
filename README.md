# InkTime v6 - Smartwatch cu E-Paper

**InkTime v6** este un proiect de ceas inteligent "open-source" bazat pe procesorul **nRF52840** (Nordic Semiconductor) și un ecran **E-Paper de 1.54 inch**. Accentul este pus pe eficiență energetică (prin utilizarea tehnologiei E-Ink) și pe un design hardware ultra-compact.



## Pașii de Implementare

### 1. Proiectarea Schemei Electronice (Hardware)
* **Managementul Puterii:** Implementarea unui circuit de încărcare Li-Po via USB-C și reglarea tensiunii la 3.3V pentru procesor și display.
* **Circuitul de Ceas:** Integrarea a două cristale de cuarț (32.768 kHz pentru modul Sleep și 32 MHz pentru funcționarea Bluetooth).
* **Interfața Display:** Proiectarea circuitului de "drive" pentru ecranul E-Paper V2, incluzând inductoarele și condensatorii de filtrare necesari pentru refresh-ul imaginii.

### 2. Layout PCB (Manufacturing)
* **Stackup de 4 Straturi:** S-a optat pentru o placă cu 4 straturi pentru a asigura un plan de masă (GND) solid și continuu pe Layer 15, esențial pentru integritatea semnalului RF (Bluetooth).
* **Miniaturizare:** Utilizarea componentelor SMD de dimensiuni 0402 și 0201 pentru a încadra toată electronica în limitele carcasei de ceas.

### 3. Integrare Mecanică (Mechanical)
* Modelarea 3D a întregului ansamblu în Fusion 360 pentru a verifica toleranțele dintre baterie, PCB și ecran.
* Proiectarea unei carcase care să protejeze ecranul fragil de 1.05mm grosime.

---

## Decizii Tehnice și Compromisuri

În procesul de design, au fost luate câteva decizii critice pentru a menține costurile de producție scăzute fără a sacrifica funcționalitatea:

### Decizia privind Vias (Overlap la nivel de pini)
În timpul rutării procesorului **nRF52840** (pachet aQFN73 cu densitate extremă), s-a decis **acceptarea unor mici overlap-uri între vias și pad-urile pinilor**.
* **Motivul:** Pentru a evita utilizarea tehnologiei "Blind/Buried Vias" (care ar fi triplat costul de fabricare a PCB-ului), s-a lucrat la limita inferioară a capabilităților fabricii (0.15mm clearance).
* **Justificare:** Aceste suprapuneri minore sunt sigure pentru procesul de asamblare industrială și permit rutarea semnalelor critice către straturile interne (Layer 2 și 16) fără a lungi traseele, ceea ce ar fi indus zgomot electric.

---

## Specificații Tehnice

| Componentă | Specificație |
| :--- | :--- |
| **Microcontroler** | Nordic nRF52840 (Bluetooth 5.0, ARM Cortex-M4F) |
| **Display** | 1.54 inch E-Paper V2 (200x200 pixeli) |
| **PCB Stackup** | 4 straturi (Signal/Power/GND/Signal) |
| **Dimensiuni Display** | 37.32mm x 31.80mm x 1.05mm |
| **Încărcare** | USB-C (Battery Management integrat) |

---

## Structura Folderelor

```text
|-- Hardware/       # Fișierele .sch, .brd și PDF-ul schemei
|-- Manufacturing/  # Gerbers.zip, BOM și Pick and Place
|-- Mechanical/     # ModelFinal 3D (.step)
|-- Images/         # Randări și poze cu prototipul
|-- LICENSE         # Licența proiectului
|-- README.md       # Documentația principală
```
