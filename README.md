# 🌡️ Smart Industry SCADA: Sistem de Monitorizare Parcare și Control HVAC

Acest proiect reprezintă o soluție completă de automatizare și monitorizare realizată în platforma **Ignition 8.1 (Vision Module)**. Proiectul integrează managementul unei parcări inteligente cu un sistem avansat de control al climatizării industriale, punând accent pe eficiență energetică și animații dinamice.

---

## 📸 Prezentare Vizuală

### Interfața Principală (Dashboard)
> [!TIP]
> *Inserează aici o poză de ansamblu cu ecranul tău principal.*
![HMI Main Screen](URL_POZA_PRINCIPALA_AICI)

---

## 🚗 1. Sistem de Monitorizare Parcare (Smart Parking)

Această fereastră gestionează starea locurilor de parcare și timpul de ocupare. Include o logică de securitate care monitorizează cât timp un vehicul staționează într-un loc rezervat.

**Funcționalități cheie:**
* **Timer Ocupare:** Calculul în timp real al duratei de staționare.
* **Alarme Critice:** Declanșarea unei alerte vizuale în tabelul de avarii dacă timpul de ocupare depășește pragul setat.
* **Interfață Intuitivă:** Schimbarea dinamică a stării vizuale a locurilor de parcare.

#### 🎥 Demo: Logica de Timp și Alarma de Ocupare
> [!IMPORTANT]
> *Aici încarcă GIF-ul în care se vede cum crește timpul pe locul de parcare și cum apare alarma în tabel.*
![Demo Parcare](URL_GIF_PARCARE_AICI)

---

## ❄️ 2. Control HVAC și Automatizare Temperatură

Sistemul de climatizare funcționează complet automat, utilizând un algoritm de tip **Hysteresis (Deadband)** pentru a proteja echipamentele împotriva pornirilor/opririlor repetate.

**Logica de Operare:**
* **Ventilație (Răcire):** Pornește automat la **>25°C** și se oprește doar când temperatura scade sub **22°C**.
* **Încălzire (Frost Protection):** Activare automată la **<7°C** pentru prevenirea înghețului, cu oprire la **10°C**.

#### 🎥 Demo: Animații Dinamice și Reacția la Temperatură
> [!IMPORTANT]
> *Aici încarcă GIF-ul cu flacăra, ventilatorul care se învârte și particulele de aer care apar doar când sistemul este activ.*
![Demo HVAC Animații](URL_GIF_HVAC_AICI)

---

## 🛠️ Detalii Tehnice (Tech Stack)

### 🐍 Programare și Logică
* **Python Scripting:** Implementat pe evenimente de tip `valueChanged` la nivel de Tag pentru controlul proceselor.
* **Expression Language:** Utilizat pentru animații fluide și vizibilitate condiționată.
* **Hysteresis Logic:** Algoritm de control industrial pentru eficiența consumului.

### 🎨 Design și Animații (Advanced Math)
În loc să folosim animații predefinite, am utilizat funcții matematice pentru o redare fluidă:
* **Flacăra Pulsantă:** Implementată printr-o funcție liniară de tip Triangle Wave:  
    `397.48 - abs(((Timer % 80) - 40) * 0.1)`
* **Flux de Aer (Particule):** Vizibilitate condiționată bazată pe starea booleană a sistemului:  
    `{[default]Pornire_stare_ventilatie} = 1`

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
