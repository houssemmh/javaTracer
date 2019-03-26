# Java Tracer

A tracing tool for Java applications. This tool uses eBPF to hook on USDT tracepoints and generates CTF traces using LTTng.

## Requirements
  - Linux Kernel supporting eBPF
  - Lttng
  - OpenJDK

## Installation

Install BCC
```
echo "deb [trusted=yes] https://repo.iovisor.org/apt/xenial xenial-nightly main" | sudo tee /etc/apt/sources.list.d/iovisor.list
sudo apt-get update
sudo apt install bcc-tools
```
Compile the tracepoints
```
cd traceLib/
./compile.sh
```

## Usage 

```
./java-lttng-tracer.sh $PID
```

## Trace Analysis 
Download Tracecompass source code
```
git clone git://git.eclipse.org/gitroot/tracecompass/org.eclipse.tracecompass.git
```
Download Tracecompass incubator (branch ebpf-support)
```
git clone https://github.com/houssemmh/tracecompass-inclubator-thesis.git 
```
Compile Tracecompass and import the XML Analysis *Jthreads.xml*
