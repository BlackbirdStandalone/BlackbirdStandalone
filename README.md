# Honda CBR1100XX Super Blackbird
# Standalone ECU project

This project was spawned as a result of the notorious ECU code 25 fault that various EFI model Blackbirds suffer from. Code 25 alludes to a faulty knock sensor or wiring, however many times it is not the knock sensor or wiring, but the Keihin ECU that has developed internal electronic faults after 20+ years of use. Furthermore, repairing the stock electronics is also not a straightforward option due to its package format. This project seeks an alternative option of replacement rather than repair.

My particular bike is an Australian 2002 model and has also suffered this issue.

An important motivator for this project is to future proof the motorcycle. Simply put, this motorcycle is capable of running for decades into the future. It would be a sad state of affairs to see such an iconic machine let down by failing electronics, especially when the fault mode cripples the performance of the bike. The spirit behind this effort is to keep the Blackbird alive.

This project is not for everyone, but will be of interest to individuals that own the iconic Honda Blackbird with technical aptitude with electronic fuel injection systems.

This project also attempts be stand alone ECU agnostic, favouring no particular system.

This project is a continual work in progress and aims to have a working system in iterative steps. The final road map is the availability of a full ‘plug & play’ system.

In time, it is hoped that several configurations are developed, so collaboration is encouraged.


# Technical hurdles
The blackbird has a unique camshaft trigger pattern situated on its exhaust camshaft. It is comprised of a 3-tooth trigger wheel. Two teeth are exactly 180 degrees apart with the remain spoke being offset by 30 camshaft degrees. Since this pattern is unique to Keihin and not immediately catered for by most ECU systems on the market, a separate up-coming repository of a ‘Tooth-Eater’ will be available. The ‘Tooth-Eater’ is in effect an edge counter that reads incoming positive edges as produced by the camshaft trigger. In effect, it removes (eats) two of the teeth edges and allows the single remaining edge to pass through to the standalone ECU. Most systems on the market today are available to process a single tooth from the camshaft in their configuration.

The repository named ‘AdapterBoard’ aims to connect a standalone system to the bikes stock wiring harness. 

