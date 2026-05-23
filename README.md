# Honda CBR1100XX Super Blackbird
# Standalone ECU project
<p>
This project was spawned as a result of the notorious ECU code 25 fault that various EFI model Blackbirds suffer from. Code 25 alludes to a faulty knock sensor or wiring. However in many cases it is the Keihin ECU itself that has developed internal electronic faults after 20+ years of use. Furthermore, repairing the stock electronics is not a straightforward task due to its sealed format. With new stock becoming increasingly limited & cost prohibitive, this project seeks an alternative option of replacement rather than repair.
</p>
<p>
My particular bike is an Australian 2002 model and has also suffered this issue. Other Honda models from the same era may also exhibit similar issues depending on the year of release. I.e. The ST1300's, Honda Aquatrax which is a jet ski and perhaps some CBR's, all throwing their own version of a knock sensor code. Before continuing it is important to verify that the problem is indeed within the ECU and not the knock sensor.
</p>
<p>
An important motivator for this project is to future proof the motorcycle. Simply put, this motorcycle is capable of running for decades into the future in the hands of a careful owner. It would be a sad state of affairs to see such an iconic machine let down by failing electronics, especially when the fault mode cripples the performance of the bike. The spirit behind this effort is to keep the Blackbird alive and to preserve this legendary motorcycle.
</p>
<p>
This project is not for everyone but may be of interest to individuals with technical aptitude with electronic fuel injection systems that own the Honda Blackbird or similar affected models.
</p>
<p>
This project also attempts be stand alone ECU agnostic, favouring no particular system. In time, it is hoped that configurations become available to suit multiple standalone systems on the market, so collaboration is encouraged.
</p>
<p>
This project is a continual work in progress and aims to have a working system in iterative steps with the final road map being a ‘plug & play’ system (or approaching it).
<br /><br />
To date, my Honda Blackbird is running successfully on RusEFI (I.e. 'microRusEFI' specifically) in conjunction with a Tooth Eater module that I have developed (read below). This tooth eater module should work with any Honda model using the cam 3-spoke trigger pattern and should also work with any stand alone ECU that can be configured to accept a single cam pulse per engine cycle (I.e. most aftermarket systems).
</p>

<p>
The software (firmware), hardware and respective designs are provided “as is” under permissive licences and without any warranty, express or implied. The author has presented this effort in good faith so that it is useful to those interested. In no event shall the author be liable for any damages arising from the use of this material. Please read the licences and only continue if you are comfortable using it on your machinery in accordance with the terms and conditions of the attached licences.
</p>

<br /><br />
# Technical hurdles
<p>
The Honda Blackbird (and other CBR's of that era) has a unique camshaft trigger pattern situated on its exhaust camshaft. It is comprised of a 3-tooth trigger wheel. Two teeth are exactly 180 degrees apart with the remaining tooth being offset by 30 camshaft degrees. Since this pattern is unique to Keihin and not immediately catered for by most ECU systems on the market, a separate repository named ‘ToothEater’ is made available (see link below). The ‘ToothEater’ is a small PCB about the size of a matchbox and is in effect an edge counter that reads incoming positive edges as produced by the camshaft trigger. It works as an intermediary between the camshaft and the standalone ECU by digitally removing (eating) two teeth edges. This allows the single remaining tooth edge to pass through to the standalone ECU. Most standalone systems on the market today are capable of processing a single tooth from the camshaft in their trigger configuration. This effort attempts to widen the choice of ECU for the Blackbird via a kind of 'compatibility mode'.
</p>
<p>
In the past, others have worked around this cam trigger issue by lopping off two teeth using a hacksaw. This works, but it also means that if you want to revert back to using the OEM unit you will need to get into the top end again and re-install part number 14405-MAT-E00' ROTOR PULSE.
</p>

<br />
<table border="1">
<tr>
<td align="center" valign="center">
<img 
    style="display: block; 
           margin-left: auto;
           margin-right: auto;
           width: 100%;"
    src="images/BB_ExhCam.png#center">
</img>

<p style="text-align: center;">TDC cylinder #1 compression stroke shown in red </p>
</table>
</td>
</tr>
<br />

<p>
The Tooth Eater firmware is currently available in the 'ToothEater-Firmware' repository with the official release being 'v1.0'. The through-hole version of the PCB will become available soon (in 2026) as an official release after I have tested it thoroughly on the bike. It is intended to be DIY friendly. Afterward, the plan is to also release an even smaller SMD version of the PCB.
</p>

<br /><br />
# Repositories

<table border="1">

<tr> 
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/AdapterBoard" target="_blank">AdapterBoard</a>
</strong>
</td>

<td width="80%">
The ‘AdapterBoard’ repository provides an interface to connect a standalone system to the bikes stock wiring harness.
</td>
</tr>

<tr>
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/ToothEater-Firmware" target="_blank">ToothEater-Firmware</a></strong>
</td>

<td width="80%">
The Tooth Eater firmware. This repository describes the technical operation of the Tooth Eater and contains the firmware source & simulation files.
</td>
</tr>

<tr>
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/ToothEater-HW-THT" target="_blank">ToothEater-HW-THT</a></strong>
</td>

<td width="80%">
The Tooth Eater hardware (Through-Hole version). This repository contains the through hole version of the tooth eater hardware. It contains schematics, PCB and gerber files. This through hole version is intended with DIY in mind.
</td>
</tr>

<tr>
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/ToothEater-HW-SMD" target="_blank">ToothEater-HW-SMD</a></strong>
</td>

<td width="80%">
The Tooth Eater hardware (SMD version). This repository contains the surface mount version of the tooth eater hardware. It contains schematics, PCB and gerber files. This SMD version is intended to be an completed unit or built as DIY using SMD components.
</td>
</tr>

<tr>
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/Documentation" target="_blank">Documentation</a></strong>
</td>

<td width="80%">
The 'Documentation' repository currently holds the Keihin pinout assignments. In the future, this repository will also hold an open document for standalone ECU conversions.
</td>
</tr>

<tr>
<td width="30%">
<strong><a href="https://github.com/BlackbirdStandalone/microRusEFI-Blackbird" target="_blank">microRusEFI-Blackbird</a></strong>
</td>

<td width="80%">
The 'microRusEFI-Blackbird' repository is currently under construction. The settings are what I'm currently using on my running bike. Its intended as a guide only to help you get your bike running if you decide to use RusEFI or its variants. Many settings will overlap with the other inline-4 within the CBR family. I.e. CBR600, 929, 954 & CBR1000.
</td>
</tr>

</table>

<br /><br />
After the system is up and running, additional repositories will be created for 'Tunes' and specific ECU configurations.

If you wish to contact me, you can do so at: 

    Blackbird-Standalone@proton.me

