# Honda CBR1100XX Super Blackbird
# Standalone ECU project

This project was spawned as a result of the notorious ECU code 25 fault that various EFI model Blackbirds suffer from. Code 25 alludes to a faulty knock sensor or wiring. However in many cases it is the Keihin ECU itself that has developed internal electronic faults after 20+ years of use. Furthermore, repairing the stock electronics is not a straightforward task due to its sealed format. With new stock becoming increasingly limited & cost prohibitive, this project seeks an alternative option of replacement rather than repair.

My particular bike is an Australian 2002 model and has also suffered this issue.

An important motivator for this project is to future proof the motorcycle. Simply put, this motorcycle is capable of running for decades into the future in the hands of a careful owner. It would be a sad state of affairs to see such an iconic machine let down by failing electronics, especially when the fault mode cripples the performance of the bike. The spirit behind this effort is to keep the Blackbird alive.

This project is not for everyone, but will be of interest to individuals that own the Honda Blackbird with technical aptitude with electronic fuel injection systems.

This project also attempts be stand alone ECU agnostic, favouring no particular system. In time, it is hoped that configurations become available to suit multiple standalone systems on the market, so collaboration is encouraged.

This project is a continual work in progress and aims to have a working system in iterative steps. The final road map is the availability of a drop in ‘plug & play’ system.


# Technical hurdles
The Honda Blackbird (and other CBR's of that era) has a unique camshaft trigger pattern situated on its exhaust camshaft. It is comprised of a 3-tooth trigger wheel. Two teeth are exactly 180 degrees apart with the remaining tooth being offset by 30 camshaft degrees. Since this pattern is unique to Keihin and not immediately catered for by most ECU systems on the market, a separate up-coming repository named ‘ToothEater’ will be available during sometime in 2026. The ‘ToothEater’ is a small PCB about the size of a matchbox and is in effect an edge counter that reads incoming positive edges as produced by the camshaft trigger. It works as an intermediary between the camshaft and the standalone ECU by digitally removing (eating) two teeth edges. This allows the single remaining tooth edge to pass through to the standalone ECU. Most standalone systems on the market today are capable of processing a single tooth from the camshaft in their trigger configuration. This effort attempts to widen the choice of ECU for the Blackbird via a kind of 'compatibility mode'.

In the past, others have worked around this cam trigger issue by lopping off two teeth using a hacksaw. This works, but it also means that if you want to revert back to using the OEM unit you will need to get into the top end again and re-install part number 14405-MAT-E00' ROTOR PULSE.

</br>
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
</br>

The Tooth-Eater firmware is in its final stages of development and shown to work well in bench testing up to 20,000 RPM. After it is proven to work on the motorcycle, it will be made available in the 'ToothEater' repository.

# Repositories

<table border="1">

<tr> 

<td width="20%">
<strong>AdapterBoard</strong>
</td>

<td width="80%">
The ‘AdapterBoard’ repository provides an interface to connect a standalone system to the bikes stock wiring harness.
</td>

</tr>


<tr>

<td width="20%">
<strong>Documentation</strong>
</td>

<td width="80%">
The 'Documentation' repository currently holds the Keihin pinout assignments. In the future, this repository will also hold an open document for standalone ECU conversions.
</td>

</tr>


<tr>

<td width="20%">
<strong>ToothEater</strong>
</td>

<td width="80%">
Coming sometime in 2026.
</td>

</tr>

</table>

After the system is up and running, additional repositories will be created for 'Tunes' and specific ECU configurations.

If you wish to contact me, you can do so at: 

    Blackbird-Standalone@proton.me

