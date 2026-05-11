# 🌡️ Smart Industry SCADA: Sistem de Monitorizare Parcare și Control HVAC

Acest proiect reprezintă o soluție completă de automatizare și monitorizare realizată în platforma **Ignition 8.1 (Vision Module)**. Proiectul integrează managementul unei parcări inteligente cu un sistem avansat de control al climatizării industriale, punând accent pe eficiență energetică și animații dinamice.

---

## 📸 Prezentare Vizuală

### Interfața Principală 
<img width="1378" height="492" alt="image" src="https://github.com/user-attachments/assets/4f02b2d8-77ec-4f85-9f50-f8c56dd14b74" />

---

## 🚗 1. Monitorizare Parcare Inteligentă (Smart Parking)

**Această fereastră oferă o imagine de ansamblu asupra disponibilității parcării, integrând monitorizarea timpului de staționare și alerte automate.**

* **Simulare prin Timer Script:** Am utilizat un script de tip timer pentru a simula creșterea timpului în timp real. Această soluție înlocuiește necesitatea unui PLC fizic, făcând proiectul ușor de prezentat și foarte user-friendly.
* **Arhitectură bazată pe UDT:** Fiecare loc de parcare este definit printr-un **UDT (User Defined Type)**. Am creat o singură structură pe care am instanțiat-o ulterior, demonstrând o abordare scalabilă și organizată.
* **Alarme Dinamice:** Am configurat alarme personalizate pentru fiecare loc folosind parametrul `{Loc_parcare_numar}`. Astfel, mesajele de eroare sunt generate automat cu numărul corect al locului de parcare.
* **Feedback Vizual :** Culoarea indicatorului de stare se schimbă dinamic (Verde pentru liber / Roșu pentru ocupat) în funcție de prezența vehiculului.
* **Navigare Rapidă:** Include un buton de acces direct către fereastra de control HVAC pentru o gestionare eficientă a întregului sistem SCADA.
#### 🎥 Demo: Logica de Timp și Alarma de Ocupare

https://github.com/user-attachments/assets/caa5317b-7175-4fa8-a9f7-c89e6f56b212

---

## ❄️ 2. Automatizare HVAC și Monitorizare Temperatură

**Această fereastră este responsabilă pentru controlul automat al climatizării, asigurând menținerea temperaturii în parametri optimi prin procese de răcire și încălzire.**

* **Simulare prin Slider:** Am integrat un slider pentru controlul temperaturii, oferind o metodă **user-friendly** de a simula variațiile de mediu și de a testa reacția sistemului în timp real, fără a depinde de senzori externi.
* **Logică de Operare (Protecție Echipamente):** Sistemul utilizează praguri diferențiate pentru a asigura stabilitatea procesului și a evita pornirile/opririle repetate:
    * **Ventilație (Răcire):** Activare automată la **>25°C** și oprire la **<22°C**.
    * **Încălzire (Frost Protection):** Activare sub **7°C** și oprire la atingerea pragului de **10°C**.
* **Animații Avansate:** Am utilizat **formule matematice** corelate cu un timer pentru a genera mișcarea fluidă a simbolurilor. Pentru o interfață curată, am setat vizibilitatea condiționată: animațiile (flacăra sau fluxul de aer) devin vizibile pe ecran doar atunci când sistemul respectiv este activ.
* **Monitorizare Avarii:** Include un tabel de evenimente configurat cu alarme specifice pentru pragurile critice, permițând identificarea rapidă a problemelor de temperatură.
* **Navigare:** Fereastra este prevăzută cu un buton de întoarcere rapidă către modulul de monitorizare a parcării.
#### 🎥 Demo: Animații Dinamice și Reacția la Temperatură

https://github.com/user-attachments/assets/e5575098-49b7-4dec-bee7-592605666bfe

---

## 📂 Structura Fișierelor din Repository

| Fișier | Descriere |
| :--- | :--- |
| `Ignition_Backup.gwbk` | **Gateway Backup:** Salvarea completă a serverului (include configurări, tag-uri și proiecte). |
| `Proiect_Parcare_Final.zip` | **Project Export:** Ferestrele Vision, pop-up-urile și resursele grafice. |
| `tags_logic.json` | **Tag Export:** Structura de tag-uri, scripturile Python și configurările de alarme. |

---

## 🚀 Cum se rulează acest proiect
1.  Instalați **Ignition 8.1** (Maker, Edge sau Standard Edition).
2.  Accesați Gateway-ul (`localhost:8088`) și restaurați fișierul `.gwbk` SAU:
3.  Importați `tags_logic.json` în Tag Browser.
4.  Importați `Proiect_Parcare_Final.zip` în Designer.

---
*Proiect realizat în scop academic pentru demonstrarea competențelor de integrare SCADA și programare industrială.*
