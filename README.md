# TwinCAT 3 MC3 FluidPower (TF5560) - Samples 
This repository contains official sample code for the product **TF5560 | TwinCAT 3 MC3 FluidPower** offered by [Beckhoff Automation](https://www.beckhoff.com). The sample code is provided as-is under the Zero-Clause BSD license.

TwinCAT 3 MC3 FluidPower extends [TF5500 | TwinCAT 3 MC3 Base](https://www.beckhoff.com/en-en/products/automation/twincat/tfxxxx-twincat-3-functions/tf5xxx-motion/tf5500.html) with control of hydraulic and pneumatic (fluid power) axes.

## Requirements and installation
TwinCAT 3 MC3 requires **TwinCAT 3.1 Build >= 4026.23.1** and **TE1300.ScopeViewProfessional.XAE** is recommended.

> These samples were created with **TwinCAT 3 MC3 version 4.0.6**.

Make sure to install the following packages for engineering system:
- TwinCAT.Standard.XAE
- TE1300.ScopeViewProfessional.XAE
- **TF5560.MC3.FluidPower.XAE** (no runtime installation required - automatic deployment of runtime components to the target system during activation of configuration)
- Some samples use 'Preview Libraries' from Preview feed. Add this feed to your TcPkg sources (URL: https://public.tcpkg.beckhoff-cloud.com/api/v1/feeds/Preview/) and install packages TwinCAT.XAE.PLC.Lib.Motion.MC3.Tc3_Mc3FluidPower_Preview. 

Make sure to install the following packages for runtime system:
- TwinCAT.Standard.XAR (Windows)
- TF3300.ScopeServer.XAR (Windows)
- tc31-xar-um (Beckhoff RT Linux&reg; Runtime)

## Samples
| Sample | What it shows |
| --- | --- |
| [ValveCharacterization/ValveCharactBasic](ValveCharacterization/ValveCharactBasic) | Automated valve characterization that maps spool position to axis velocity using `MC_ValveCharacterization` and `MC_ValveCharacteristicCurve` (`ValveCharacteristicPoint` with `SpoolPosition`/`Velocity`). The axis is moved through its range to record the valve response; a separate `Simu` program provides a realistic non-linear (cosine) valve model to demonstrate the workflow without hardware. |
| [ValveCharacteristicCurve/ReadWriteCsvFile](ValveCharacteristicCurve/ReadWriteCsvFile) | Persisting valve characteristic curve data (`ValveCharacteristicPoint` spool-position/velocity pairs) to and from CSV files with `MC_ValveCharacteristicCurve_WriteToCsv` and `MC_ValveCharacteristicCurve_ReadFromCsv`. Supports configurable field separators (comma/semicolon) for locale-specific formatting, enabling data exchange with external analysis tools. |

## Getting started

Each folder contains a self-contained TwinCAT solution (`.sln`) that can be opened and run independently:

1. Open the sample's `.sln` file in TwinCAT XAE (Visual Studio / TcXaeShell).
2. Select your target system (local runtime or a remote target) via **TwinCAT > Choose Target System**.
3. Build the solution (**Build > Build Solution**) and activate the configuration (**TwinCAT > Activate Configuration**), confirming the switch to Run mode.
4. Log in and start the PLC (**PLC > Login**, then **Start**). The axes run in simulation by default, so no physical hardware is required.
5. Open the `MAIN` program and use the declared trigger/command variables to step through the sample. In most cases set `bStart` to `TRUE` to start the sample. Some samples provide a selection of different use cases or commands to be executed.
6. Where included, open the Scope/Measurement project to visualize the motion.

> The samples use the included trial/simulation axis licenses. To run on real hardware, adapt the axis and drive configuration to your setup.

## How to get support

Should you have any questions regarding the provided sample code, please contact your local Beckhoff support team. Contact information can be found on the official Beckhoff website at https://www.beckhoff.com/contact/.

## Further information

Further information about this sample code can be found on the [Beckhoff Information System](https://infosys.beckhoff.com) in the [TF55xx | TwinCAT 3 MC3 documentation](https://infosys.beckhoff.com/content/1031/tf55xx_tc3_mc3/index.html?id=6887785203859632625).