# FPGA Lab 2.1 — Counter and LED Toggle

**Verilog · Counters · Sequential Logic · Reset**

Former repository name: `FPGA2-1`.

A parameterized counter toggles an LED and demonstrates sequential logic and asynchronous active-low reset. 时钟计数与 LED 翻转实验。

[counter.v](counter.v) contains `counter` and the original `tb_counter` testbench. `CNT_MAX` defaults to 24, so the LED toggles every 25 input clock cycles. At a 50 MHz input, the complete LED waveform has a 1 microsecond period; the small count is suitable for simulation rather than a visible board blink.

## Run

With Icarus Verilog installed:

```bash
mkdir -p build
iverilog -g2012 -s tb_counter -o build/counter.vvp counter.v
vvp -n build/counter.vvp
```

The testbench prints the count and LED state. `vvp -n` terminates at the original `$stop` instead of entering an interactive prompt. The testbench is observational and contains no assertions. Board use requires an appropriate count parameter and pin constraints.

[FPGA lab index](https://github.com/chengmiao2005/FPGA-Labs) · [Original-to-current file map](docs/FILE_MAP.md)

[Validation record](docs/VALIDATION.md)
