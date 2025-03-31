# Digaminer
A Goldiga CPU miner (rx/0) with Estimated hashrate cap

### ⚠️ Antivirus / False Positive Notice

Some antivirus programs may flag this miner as a **trojan**, **malware**, or **riskware**. This is a **false positive** and is common with mining software due to:

- Low-level CPU access (e.g. MSR instructions)
- Use of hashing algorithms (like RandomX)
- The fact that some malware bundles miners without user consent

This project does **not** contain any malicious code.

If you're unsure or concerned:

- Use something else

> **Reminder:** Always download and build from trusted sources. Mining software is frequently abused by bad actors — be safe and verify.


## License

This project is licensed under the MIT License – see the [LICENSE](./LICENSE) file for details.

## Dependencies

This project uses the following third-party libraries:

- [RandomX](https://github.com/tevador/RandomX) – for proof-of-work hashing (BSD 3-Clause)
- [nlohmann::json](https://github.com/nlohmann/json) – for JSON handling (MIT License)
- [WinRing0](https://openlibsys.org/) – for MSR register access (proprietary license)

See [NOTICE.md](./NOTICE.md) for more information.

See [NOTICE.md](./NOTICE.md) for more information.
