<img width="315" height="104" alt="image" src="https://github.com/user-attachments/assets/dadd0dcf-2471-4a1e-8135-82f2dec5e4f4" />


# Hydro-Core

HydroCore was specifically made for using Ethernet and as well as Pixhawk with my mobile phone, because I was working on an underwater drone project. There, I needed, like, mobile—if I can connect the internet with my mobile phone and the Pixhawk Mavlink telemetry connection with my mobile phone, it will be so good, because mobile phones have better capability—like power capability, processing power, using camera for live feed and above all the low power workload. And from that, I was inspired to make this board, which basically converts Ethernet to USB and converts UART to USB, and those are connected with a USB hub IC, which combines to use one upstream output, which then connects to my mobile phone.

# PCB Design

So I haven't designed my software yet, but this is my PCB design. My PCB design contains:

an Ethernet port with a PHY controller,

necessary components to support this,

the UART controller chip to USB converter,

a USB converter IC,

and the full board is a self-powered board.

All of the power is given by an external power source; it doesn't come from the mobile phone.

# Mobile Charging Feature

Another fun fact is, because my mobile phone will be connected to the board all the time, it will be power draining for most of the time. There was no quite good solution for, like, charging my mobile, so what I did—I made a connection, I made an upstream charger with an upstream charger IC, where it can charge my mobile phone as well as connect to the devices.

# Challenges and Learning

And that is all for this PCB. And in this PCB, it was really a challenge for me, because it was my first time designing such a board, and I wanted it to be a very compact board. So I needed to work with so many connections, because there were so many connections. I had to learn about layers, I had to learn about ground cores, thermal relief pads, thermal relief connections, you know, there are vias, what is the impedance between the wire—I had to learn so many things. So it was quite a learning project for me, and I'm really grateful.

<img width="594" height="378" alt="Screenshot 2025-11-23 150526" src="https://github.com/user-attachments/assets/ccb44061-4ad9-4ee4-943d-7ca2cec28978" />

<img width="784" height="532" alt="Screenshot 2025-11-23 150317" src="https://github.com/user-attachments/assets/fffed834-0739-4b86-b307-1adb39747df8" />

<img width="878" height="686" alt="Screenshot 2025-11-23 150328" src="https://github.com/user-attachments/assets/967b2066-fc77-4833-a972-f7178046001e" />

<img width="683" height="581" alt="Screenshot 2025-11-22 011315" src="https://github.com/user-attachments/assets/4edbb809-cd56-4dc0-b078-950a1e2ba269" />



