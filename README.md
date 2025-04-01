# Digaminer – Hashrate limited RandomX Miner
**Digaminer** is a lightweight, configurable CPU miner designed for coins using the **RandomX** algorithm – primarily optimized for the [Goldiga (GDG)](http://www.goldi.ga) coin.

Goldiga has a built-in maximum hashrate limit per device, enforced by the protocol.  
The cap is set at **950 H/s**.

This application automatically adjusts its performance to stay **just below the 950 H/s threshold**, ensuring compliance while maximizing mining efficiency.
---

## Antivirus / False Positive Notice

Some antivirus software may flag this miner as **trojan/malware/riskware**.  
This is a **false positive** and common with mining tools due to:

- Use of low-level CPU operations (e.g., MSR register access)
- High-performance hashing routines
- Association with mining software bundled in malware

**This miner does not contain malicious code.**  
Feel free to inspect the `.pdb` (debug symbols) included in the release.

---

##  Features

- Fast RandomX hashing
- Adjustable thread count and hashrate limit
- Real-time hashrate monitoring (10s / 60s / 5m)
- Optional MSR register tweaks for Intel/AMD CPUs
- Configurable via CLI or config file
- Minimal dependencies

---

## What is RandomX?

**RandomX** is a CPU-optimized proof-of-work hashing algorithm used primarily by [Monero (XMR)](https://www.getmonero.org). It is designed to:

- Be **memory hard**, to reduce GPU/ASIC advantage
- Use **random code execution and math-heavy operations**
- Favor **general-purpose CPUs** over specialized hardware

[Read more about RandomX](https://github.com/tevador/RandomX)

---

## What is Goldiga (GDG)?

[Goldiga](https://www.goldi.ga) is an inclusive, CPU-mining-friendly cryptocurrency built on a **RandomX-based Proof of Work** consensus. It is designed to be accessible, fair, and community-driven – inspired by the privacy of Monero and the decentralization of Bitcoin, with a touch of meme culture.

### Key Goals

- **Fair mining**: Maximum hashrate per miner enforced to prevent centralization
- **Device-friendly**: Optimized for mobile phones, low-power CPUs and hobbyist hardware
- **DAO governance**: Every GDG coin equals one vote on network decisions
- **Privacy-first**: Monero-style RingCT keeps transactions secure and private

### Technology Highlights

- **Algorithm**: RandomX (`rx/0`), CPU-only
- **Block time**: 2 minutes
- **Initial reward**: 40 GDG per block
- **Total supply**: 21 million GDG
- **Halving**: Every 210,000 blocks
- **Tail emission**: 0.1 GDG/block (once supply cap is reached)

### Use Cases

- Secure, private digital payments
- Community governance via DAO (1 GDG = 1 vote)
- Fair and inclusive mining for everyone

🔗 More info: [goldi.ga](http://www.goldi.ga)


---

## Dependencies

This project uses the following third-party libraries:

- [RandomX](https://github.com/tevador/RandomX) – BSD 3-Clause License
- [nlohmann::json](https://github.com/nlohmann/json) – MIT License
- [WinRing0](https://openlibsys.org/) – Proprietary license (used for MSR tuning on Windows)

See [`NOTICE.md`](./NOTICE.md) for full license info.

---

## Usage

You can run the miner either via command-line arguments or using a config file.

### Basic CLI example:

```bash
DigaMiner.exe --login 53YourGoldigaWallet --url smartpool.goldi.ga:7272 --threads 3 --max-hashrate 900
```

### Available options:

| Option                 | Description                                 |
|------------------------|---------------------------------------------|
| `--login <wallet>`     | Your Monero/Goldiga wallet address          |
| `--pass <password>`    | Pool password (default: `x`)                |
| `--url <pool:port>`    | Mining pool address                         |
| `--threads <n>`        | Number of miner threads (default: `4`)      |
| `--max-hashrate <hps>` | Limit total hash rate (default: `900.0`)    |
| `--dataset <0/1>`      | Use ~2GB RandomX dataset (default: 1)       |
| `--msr <0/1>`          | Apply msr tweak (default: 1)                |
| `--config <path>`      | Load config from JSON file                  |
| `--help`               | Show help                                   |

---

## 📄 Example `config.cfg`

```conf
# Example config file for Digaminer
# Lines starting with # are comments

# Required
login=AnVU1o1VM3LdEs1WrxDbfqakkHxkkX7sbgBzdcqGuGi1Kr1YmvHRdym1FjoJ8oBGLn1AgJsP1z7uXNmFn1WVqxL5UFb4zTv
url=smartpool.goldi.ga:7272
pass=x

# Optional
threads=3
max-hashrate=900.0
devdonate=1.0
dataset=1
msr=1
```

CLI flags override values in the config file.

---

## License

This project is licensed under the **MIT License**.  
See [`LICENSE`](./LICENSE) for full terms.

---

## Related files

- [`NOTICE.md`](./NOTICE.md) – licenses for included third-party libraries
- `LICENSE` – your MIT license
- `.pdb` file (optional) – included for debug/symbol transparency

---

## Credits

- RandomX by tevador & contributors
- JSON for Modern C++ by Niels Lohmann
- WinRing0 by OpenLibSys (Windows MSR tuning)

---

*Built with ❤️ for the Goldiga network.*
