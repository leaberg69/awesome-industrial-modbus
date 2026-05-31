# Awesome Industrial Modbus [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 🏭 A curated list of awesome **Modbus** resources, libraries, tools, and devices for **industrial automation, SCADA, and ICS engineers**.

Modbus is the most widely deployed industrial communication protocol in the world. Over 50 years after its introduction by Modicon in 1979, it remains the de-facto standard for industrial DC monitoring, battery banks, telecom rectifiers, solar inverters, and millions of legacy and modern industrial devices.

This list focuses on resources that are **actively maintained, openly licensed, and genuinely useful for production work** — not toy projects, marketing pages, or dead links.

## Contents

- [Specifications & Documentation](#specifications--documentation)
- [Client Libraries](#client-libraries)
  - [Python](#python)
  - [C/C++](#cc)
  - [Java](#java)
  - [JavaScript/Node.js](#javascriptnodejs)
  - [Go](#go)
  - [Rust](#rust)
- [Slave Simulators](#slave-simulators)
- [CLI Tools](#cli-tools)
- [GUI Tools](#gui-tools)
- [Network Analysis](#network-analysis)
- [Security & Pentest](#security--pentest)
- [SCADA Integration](#scada-integration)
- [Educational Resources](#educational-resources)
- [Books & Whitepapers](#books--whitepapers)
- [Talks & Videos](#talks--videos)
- [Related Awesome Lists](#related-awesome-lists)
- [Contributing](#contributing)

## Specifications & Documentation

- [Modbus.org official specifications](https://modbus.org/specs.php) - Application Protocol V1.1b3, RTU/TCP specifications, conformance test specs.
- [Modbus Organization](https://modbus.org/) - The official body maintaining the standard.
- [Wireshark Modbus dissector source](https://github.com/wireshark/wireshark/blob/master/epan/dissectors/packet-mbtcp.c) - Reference implementation of Modbus TCP parsing.
- [Modbus on Wikipedia](https://en.wikipedia.org/wiki/Modbus) - Comprehensive overview with history and protocol details.

## Client Libraries

### Python

- [pymodbus](https://github.com/pymodbus-dev/pymodbus) - The de-facto Modbus implementation for Python. Supports RTU/TCP/ASCII over serial and network transports. Asyncio support. (★ 2400+)
- [umodbus](https://github.com/AdvancedClimateSystems/umodbus) - Pure Python implementation of Modbus TCP, UDP and RTU. Server and client.
- [minimalmodbus](https://github.com/pyhys/minimalmodbus) - Minimal Python implementation focused on serial RTU/ASCII.

### C/C++

- [libmodbus](https://github.com/stephane/libmodbus) - The classic Modbus library for Linux/Mac/FreeBSD/QNX/Windows. (★ 2400+)
- [nanoMODBUS](https://github.com/debevv/nanoMODBUS) - Compact MODBUS RTU/TCP C library for embedded/microcontrollers.
- [FreeMODBUS](https://www.embedded-solutions.at/en/freemodbus/) - Free implementation of the Modbus protocol primarily designed for embedded systems.

### Java

- [jamod](http://jamod.sourceforge.net/) - Object-oriented Java implementation of the Modbus protocol.
- [j2mod](https://github.com/steveohara/j2mod) - Fork of jamod with bug fixes and additional features.

### JavaScript/Node.js

- [modbus-serial](https://github.com/yaacov/node-modbus-serial) - Pure JS implementation of Modbus master (client) and slave (server). RTU/TCP/UDP.
- [jsmodbus](https://github.com/Cloud-Automation/node-modbus) - Node.js implementation of Modbus master and slave.

### Go

- [goburrow/modbus](https://github.com/goburrow/modbus) - Fault-tolerant, fail-fast implementation of Modbus protocol in Go.
- [grid-x/modbus](https://github.com/grid-x/modbus) - Fork of goburrow/modbus with additional features.

### Rust

- [tokio-modbus](https://github.com/slowtec/tokio-modbus) - Modbus library for the Tokio async runtime.

## Slave Simulators

Critical for development and CI — let you test Modbus master code without physical hardware on the bench.

- **[aem-modbus-simulator](https://github.com/leaberg69/aem-modbus-simulator)** - Open-source Python Modbus RTU/TCP slave simulator with realistic **147-register industrial DC monitor map** (17 functional blocks). Six baudrates (4800-115200), TCP and Serial modes, 3 preset scenarios (telecom 48V, solar strings, automotive 24V). MIT license, pymodbus 2.x/3.x compatible.
- [diagslave](https://www.modbusdriver.com/diagslave.html) - Commercial Modbus slave simulator. Free for non-commercial use.
- [ModbusPal](https://sourceforge.net/projects/modbuspal/) - Java-based Modbus slave simulator with GUI.
- [PeakHMI Modbus Slave Simulator](https://www.peakhmi.com/products.html) - Windows-based Modbus slave simulator.

## CLI Tools

- **[aem-modbus-cli](https://github.com/leaberg69/aem-modbus-cli)** - Open-source Python CLI for Modbus RTU/TCP diagnostics: `scan` (sweep IDs 1-247), `baudrate` (auto-detect), `read` (with retry diagnostics), `bench` (RTT and error rate measurement). MIT.
- [mbtget](https://github.com/sourceperl/mbtget) - Simple Modbus/TCP client written in Perl.
- [ctmodbus](https://github.com/ControlThings-io/ctmodbus) - Multi-purpose Modbus protocol interaction tool.

## GUI Tools

- [QModMaster](https://sourceforge.net/projects/qmodmaster/) - Free Modbus master/slave application using libmodbus. Qt-based, cross-platform.
- [Modbus Doctor](https://www.modbusdoctor.com/) - Commercial Windows GUI for Modbus debugging.
- [Modbus Poll / Modbus Slave](https://www.modbustools.com/) - Industry-standard commercial Modbus testing GUI (Windows).

## Network Analysis

- [Wireshark](https://www.wireshark.org/) - Industry-standard packet analyzer with full Modbus TCP dissector support.
- [tcpdump](https://www.tcpdump.org/) - Command-line packet analyzer (use with `port 502` filter for Modbus TCP).
- [Scapy Modbus layer](https://github.com/secdev/scapy/blob/master/scapy/contrib/modbus.py) - Python packet manipulation for crafting custom Modbus frames.
- [ICS-pcap Modbus samples](https://github.com/automayt/ICS-pcap/tree/master/MODBUS) - Real-world Modbus traffic captures for testing.

## Security & Pentest

- [Nmap modbus-discover.nse](https://nmap.org/nsedoc/scripts/modbus-discover.html) - Nmap script for discovering Modbus devices on a network.
- [modicon-info.nse](https://github.com/digitalbond/Redpoint/blob/master/modicon-info.nse) - Nmap script for fingerprinting Modicon PLCs.
- [Malmod](https://github.com/mliras/malmod) - Scripts targeting Modicon M340 via UMAS protocol.
- [Industrial Exploitation Framework (ISF)](https://github.com/dark-lbp/isf) - Metasploit-like framework for ICS protocols.
- **[aem-iec62443-checklist](https://github.com/leaberg69/aem-iec62443-checklist)** - 47-item IEC 62443-4-2 Security Level 2 checklist + interactive Python validator for Modbus-speaking industrial devices.

## SCADA Integration

- [Ignition (Inductive Automation)](https://inductiveautomation.com/) - Industrial application platform with native Modbus driver.
- [FUXA](https://github.com/frangoteam/FUXA) - Open-source web-based SCADA with Modbus RTU/TCP support. (★ 2100+)
- [Elipse E3](https://www.elipse.com.br/) - Brazilian SCADA platform with Modbus support.
- [AVEVA InTouch HMI](https://www.aveva.com/en/products/intouch-hmi/) - Industry-standard HMI with Modbus support.
- [Node-RED modbus nodes](https://flows.nodered.org/search?term=modbus) - Node-RED nodes for Modbus RTU/TCP integration.
- [Telegraf Modbus plugin](https://github.com/influxdata/telegraf/tree/master/plugins/inputs/modbus) - InfluxDB Telegraf input plugin for Modbus.

## Educational Resources

- [Modbus Mesulog Standard Functions Help](http://www.mesulog.fr/help/modbus/index.html?page=read-device-identification-f43.html) - Free comprehensive Modbus reference.
- [Introduction to Modbus and Modbus Function Codes (Control Automation, 2023)](https://control.com/technical-articles/introduction-to-modbus-and-modbus-function-codes/) - Modern introduction with field engineer perspective.
- **[LRI Modbus Map (Interactive)](https://aem.lri.com.br/en-us/modbus)** - Full 147-register Modbus map of an industrial DC monitor with interactive documentation.

## Books & Whitepapers

- [Modbus Application Protocol Specification V1.1b3](https://modbus.org/docs/Modbus_Application_Protocol_V1_1b3.pdf) - Official Modbus.org specification (free PDF).
- **[Modbus RTU for Secure DC Monitoring (LRI, 2026)](https://aem.lri.com.br/en-us/whitepapers/wp01-modbus-secure-design)** - 4500-word technical whitepaper covering Modbus RTU architecture, Ed25519 firmware signing, and Secure by Design patterns.
- **[IEC 62443-4-2 SL2 in Practice (LRI, 2026)](https://aem.lri.com.br/en-us/whitepapers/wp03-iec-62443-sl2-checklist)** - Practical checklist for IEC 62443-4-2 Security Level 2 applied to Modbus-speaking devices.
- **[Secure architecture for 48V telecom battery banks (LRI, 2026)](https://aem.lri.com.br/en-us/whitepapers/wp02-banco-baterias-telecom)** - Real-world Modbus deployment in telecom DC infrastructure.

## Talks & Videos

- [Understanding SCADA's Modbus Protocol — Justin Searle @ Black Hat Asia (2015)](https://www.youtube.com/watch?v=oVDYaG2HInU) - Classic intro to Modbus from a security perspective.
- [Fun with Modbus 0x5a — Arnaud Soullié @ DEF CON 25 (2017)](https://www.youtube.com/watch?v=A_B69Rifu1g) - Modbus security research talk.
- [Modbus Enumeration | SANS ICS Concepts (2021)](https://www.youtube.com/watch?v=QO99yojavvE) - Educational series on Modbus security.
- [Modbus Man-in-the-Middle | SANS ICS Concepts (2021)](https://www.youtube.com/watch?v=-1WbegoU8i0) - Modbus MITM attack patterns and defenses.

## Related Awesome Lists

- [Awesome IoT](https://github.com/phodal/awesome-iot) - Broader IoT resources including industrial protocols.
- [Awesome Industrial Protocols](https://github.com/Orange-Cyberdefense/awesome-industrial-protocols) - Security-oriented list of industrial protocols (Modbus, S7, DNP3, etc).
- [Awesome ICS Security](https://github.com/hslatman/awesome-industrial-control-system-security) - Industrial Control System security resources.
- [Awesome Connected Things Security](https://github.com/V33RU/awesome-connected-things-sec) - IoT/IIoT security resources including firmware analysis.
- [Awesome Embedded](https://github.com/nhivp/Awesome-Embedded) - Embedded systems development.

## Contributing

Contributions welcome — please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

Quality bar:
- Project must be **actively maintained** (commit within last 12 months)
- License must be **clear** (open-source preferred but commercial OK if industry-standard)
- Description must be **factual, not promotional** (max 1 sentence value claim)
- New entries go in **alphabetical order** within sections
- One PR = one logical addition (don't bundle unrelated entries)

If you maintain a Modbus-related project that fits a section here, feel free to PR with a disclosure of your involvement.

## License

[CC0](LICENSE) — Public Domain. Use freely.

---

*Maintained by [Leandro Roisenberg](https://github.com/leaberg69) ([LRI Automação Industrial](https://lri.com.br)). Disclosure: I maintain `aem-modbus-simulator`, `aem-modbus-cli`, and `aem-iec62443-checklist` which appear in this list. They are listed on technical merit alongside competing tools (commercial diagslave, ModbusPal, Modbus Poll/Slave). Suggestions and competing alternatives are welcomed via PR.*
