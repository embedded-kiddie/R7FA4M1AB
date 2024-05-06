# R7FA4M1AB
System View Description file for Arduino UNO R4 Minima/WiFi

## Objective of this repository
- Resolve the following issue in [arduino/ArduinoCore-renesas][1].
    - ["Unable to parse SVD file" error when starting debugger #276][2]

- Make Arduino UNO R4 Minima/WiFi users around the world happy who want to debug their source code.

## Resources
### Documentation
- [Renesas RA4M1 Group User's Manual: Hardware][3]  
    - R01UH0887EJ0110 Rev.1.10 Sep 29, 2023

### SVD file
- [RA_DFP][4] for [R7FA4M1AB][5]
    - Version 5.3.0: April 18, 2024
    - Version 5.2.0: Feb. 19, 2024

## Check list for revised SVD

| Port  | Registers                      | &lt;derivedFrom&gt;     | &lt;resetValue&gt; | Check                      | 
| ----- | ------------------------------ | ----------------------- | ------------------ | -------------------------- | 
| PORT0 | P000                           | —                       | 0x00000000         | [x] ~Note 1.               | 
| ^     | P001 to P008,<br>P010 to P015  | P000                    | ^                  | [x] ~Note 1.               | 
| PORT1 | P100                           | —                       | 0x00000000         | [x] Note 1.                | 
| ^     | P101 to P107,<br>P111 to P115  | <del>P000</del><br>P100 | 0x00000000         | [x] Note 1.                | 
| ^     | P108                           | —                       | 0x00010010         | [x] Note 1.<br>[x] Note 2. | 
| ^     | P109                           | —                       | 0x00010000         | [x] Note 1.<br>[x] Note 2. | 
| ^     | P110                           | P108                    | 0x00010010         | [x] Note 1.<br>[x] Note 2. | 
| PORT2 | P200                           | <del>P000</del><br>P100 | 0x00000000         | [x] Note 1.                | 
| ^     | P201                           | —                       | 0x00000010         | [x] Note 1.<br>[x] Note 2. | 
| ^     | P202 to P206,<br>P212 to P215  | P200                    | 0x00000000         | [x] Note 1.                | 
| PORT3 | P300                           | P108                    | 0x00010010         | [x] Note 1.<br>[x] Note 2. | 
| ^     | P301 to P307                   | P100                    | 0x00000000         | [x] Note 1.                | 
| PORT4 | P400 to P407                   | P100                    | 0x00000000         | [x] Note 1.                | 
| ^     | P408                           | —                       | ^                  | [x] Note 1.<br>[x] Note 3. | 
| ^     | P409                           | <del>P000</del><br>P100 | ^                  | [x] Note 1.                | 
| ^     | P410 to P415                   | <del>P000</del><br>P100 | ^                  | [x] Note 1.                | 
| PORT5 | P500 to P505                   | P000                    | 0x00000000         | [x] ~Note 1.               | 
| PORT6 | P600 to P603,<br>P608 to P610  | P000                    | 0x00000000         | [x] ~Note 1.               | 
| PORT7 | P708                           | P000                    | 0x00000000         | [x] ~Note 1.               | 
| PORT8 | P808, P809                     | P000                    | 0x00000000         | [x] ~Note 1.               | 
| PORT9 | P914, P915                     | P109                    | 0x00010000         | [x] ~Note 1.<br>[x] Note 2.| 

- For Note 1, Note 2 and Note3, please refer to [the user manual][3].
- "~Note 1" indicates that the inverse of "Note 1.".

<!-- References -->
[1]: https://github.com/arduino/ArduinoCore-renesas "arduino/ArduinoCore-renesas"
[2]: https://github.com/arduino/ArduinoCore-renesas/issues/276 "&quot;Unable to parse SVD file&quot; error when starting debugger · Issue #276 · arduino/ArduinoCore-renesas"
[3]: https://www.renesas.com/us/en/document/mah/renesas-ra4m1-group-users-manual-hardware?r=1054146 "RA4M1 - 32-bit Microcontrollers with 48MHz Arm® Cortex®-M4 and LCD Controller and Cap Touch for HMI | Renesas"
[4]: https://www.keil.arm.com/packs/ra_dfp-renesas/devices/ "Arm Keil | Renesas RA_DFP"
[5]: https://www.keil.arm.com/devices/renesas-r7fa4m1ab/features/ "Arm Keil | Renesas R7FA4M1AB"
