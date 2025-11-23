# Initial Concept Research (1.5 hours)
I began exploring the initial idea by studying various YouTubers and technical websites to understand different design approaches. I noticed that using separate controllers required excessive wiring and physical space. My first plan was to combine open-source Ethernet-to-USB and UART-to-USB schematics and merge them using a USB hub IC.

(Ethernet to Usb0 https://www.olimex.com/Products/USB-Modules/Ethernet/USB-GIGABIT/open-source-hardware
(Ethernet to Usb) https://github.com/OLIMEX/USB-GIGABIT/blob/master/HARDWARE/USB-GIGABIT-Rev.E/USB-GIGABIT_Rev_E.pdf
(Uart to Usb-C) https://github.com/SolderedElectronics/USB-UART-CH340C-converter-board-hardware-design


# Studying Open-Source Schematics (2 hours)

I followed open-source hardware designs, but discovered that many components were unavailable, back-stocked, or incompatible. For the Ethernet port, the magnetic-shielded connector required four differential TX/RX pairs, and I found mismatches between open-source examples and my needs. Still, the reference schematics helped a lot.
<img width="668" height="556" alt="Screenshot 2025-11-10 231110" src="https://github.com/user-attachments/assets/e09036eb-3e2a-4f74-9c8d-63ed6a1440b7" />

# First Schematic Attempt & Failure Realization (1.5 hours)

After around five hours of work integrating open-source parts into my schematic, I realized the design would fail. The referenced example used USB-C-to-UART only, creating back-feed issues. The PHY controller I picked was too powerful and poorly matched because everything had to operate over USB 2.0 to match my mobile phone’s OTG limitations.
<img width="896" height="557" alt="Screenshot 2025-11-13 230238" src="https://github.com/user-attachments/assets/fce23906-79ff-4195-a503-d583e3c9fe9b" />

# Learning Datasheets for the First Time (2 hours)

I began reading datasheets seriously for the first time in my life. I learned that datasheets include example circuits that were more helpful than any online answer or AI suggestion. ChatGPT was not reliable for exact electrical values. Going through LCSC, I finally discovered the correct controller IC that matched my USB 2.0 requirements.
<img width="822" height="759" alt="Screenshot 2025-11-13 230936" src="https://github.com/user-attachments/assets/473cf60e-9904-4e06-9029-e616717a83d6" />
<img width="784" height="746" alt="Screenshot 2025-11-13 231221" src="https://github.com/user-attachments/assets/1ca143e1-8d7d-4380-8976-2c17f4c1d14c" />
<img width="1295" height="598" alt="Screenshot 2025-11-15 002058" src="https://github.com/user-attachments/assets/be7e8b95-fc2b-43e8-92da-2ab9986af3c6" />

# Day 2

## Restarting the Entire Schematic (5.5 hour)

I restarted my schematic from scratch. The earlier open-source designs still helped because some connections matched. Missing passive component values were found from Google searches, not ChatGPT. The UART-to-USB section was easy because the chip had a simple example diagram. The Ethernet controller was extremely difficult. It had so many complex connections that I nearly had to pull an all-nighter to finish it. I had to stay focused because if I left it halfway, I would forget the connection logic. I had to select a hub IC capable of upstreaming data reliably. FE1.1 was an option but had too many ports. I ultimately chose SL1.1 because its specs matched my project’s data flow requirements. I designed the AC input section that steps down to 5V. The example power circuits in the datasheet were extremely useful. Component sourcing was difficult because LCSC filtering takes practice. I added the upstream charging IC, letting the mobile phone charge while connected. LED indicators were integrated to show phone charging/battery status. I also built the 3V and 1V converters.
<img width="647" height="535" alt="Screenshot 2025-11-15 231905" src="https://github.com/user-attachments/assets/4f67cdca-4031-47d2-b86a-de96c23c860f" />

## Beginning PCB Layout (4.5)
After completing the schematic, I started PCB layout work. This was the most time-consuming stage. I tested several board outlines and dimensions to fit all components properly. Autoroute failed every time. Proper component placement became critical. I had to switch to full manual routing. I learned about impedance, trace gaps, crosstalk, thermal vias, and multilayer routing through Altium Academy and PCB guru videos. I switched between 4-layer and 6-layer designs until I understood how to use bias and planes properly. After several routing revisions and placement adjustments, I finished the board. I ran DRC checks, ensured power traces were thicker, fixed clearances, and finally completed the PCB.

Initial Layout 
<img width="504" height="556" alt="Screenshot 2025-11-18 231723" src="https://github.com/user-attachments/assets/464b5819-b1d9-4e7b-b243-caec9bc35035" />

Designing Back & Forth 
<img width="364" height="543" alt="Screenshot 2025-11-19 234145" src="https://github.com/user-attachments/assets/bde226c0-ee5b-44da-a82a-a24d02726537" />

Final Layout 
<img width="693" height="483" alt="Screenshot 2025-11-21 233110" src="https://github.com/user-attachments/assets/394a9a6b-66d0-4b37-8d2b-6031425f745f" />

Completed One 
<img width="734" height="500" alt="Screenshot 2025-11-22 133838" src="https://github.com/user-attachments/assets/6ab9550a-0ac1-40e6-82c3-1c43b2ba1d57" />

Final PCB - Pretty Clean; Proud of Myself
<img width="594" height="378" alt="Screenshot 2025-11-23 150526" src="https://github.com/user-attachments/assets/182005ed-e56d-41be-bc0b-baed7e5db49c" />
<img width="784" height="532" alt="Screenshot 2025-11-23 150317" src="https://github.com/user-attachments/assets/22688d73-3ad8-4d46-8d18-82264aefe2b6" />
<img width="497" height="469" alt="Screenshot 2025-11-23 150215" src="https://github.com/user-attachments/assets/26dc1e56-5fe8-4b73-b058-3ef21a29651a" />






