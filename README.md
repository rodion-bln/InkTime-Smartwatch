# InkTime Smartwatch - Project Progress

## Status Curent: Work in Progress (WIP)
În acest moment, etapa de **Placement** este finalizată, respectând regulile de integritate a semnalului și management termic.

### Realizări actuale:
* **Așezarea componentelor critice:** Microcontroller-ul BGA (U1) a fost plasat central, cu condensatorii de decuplare poziționați cât mai aproape de pini.
* **Optimizare RF:** Antena Bluetooth a fost plasată pe marginea plăcii, cu o zonă de **Keep-out** (fără cupru) pe toate straturile pentru a asigura emisia corectă.
* **Power Management:** Blocurile pentru LiPo Charger (IC1) și Regulatorul DC/DC de 3.3V au fost grupate logic pentru a minimiza zgomotul și pierderile de tensiune.
* **Planul de Masă (GND):** Au fost generate poligoanele de masă pe ambele straturi (Top și Bottom) și a fost efectuată verificarea inițială a Ratsnest-ului.

## Structura Proiectului
* **Hardware/**: Conține fișierele sursă Eagle/Fusion360 (`.sch` și `.brd`).
* **Manufacturing/**: (Urmează să fie generat) Fișiere Gerber, BOM și Pick-and-Place.
* **Mechanical/**: (Urmează să fie generat) Modelul 3D al dispozitivului complet (PCB + Carcasă + Baterie).
* **Images/**: Capturi de ecran cu stadiul actual al plăcii.

## Tehnologii folosite
* Microcontroller: nRF52840 (BGA Package)
* Display: E-Paper FPC Connector
* Software design: Autodesk Fusion 360 / Eagle
* Anul: 2026
