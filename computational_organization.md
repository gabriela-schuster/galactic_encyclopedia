#+TITLE:computational organization

* hardware

** CPU :alu:clock:cache:smart_cache:
+ ALU: arithimetic logical unity: mathematical operations
+ clock: period which info are processed inside the ALU
+ cache: fastest and smallest memory, inside the CPU
at first, companies focused in increasing clock, as it measured the quality,
(an 1800MHz was better than a 1600MHz),
but after sometime, other things were put in balance

*** smart cache
as CPUs grew more complex, a more efficient form of storing data in cache was necessary,
with smart cache, it became possible to store most frequently used data as close to the
CPU as possible

*** example of a CPU instruction
[[./images/cpu_instruction.jpg]]
=C. op: Operation code (ADD in this case)=

*** CPU parts
+ control
  + control unit (controls I/O data)
  + instruction decodificator (decodes what a bunch of 0s and 1s mean [value? operation?])
    see IR in [[*registers][registers]]
+ processing

*** registers
+ IR (instruction register): stores executing instruction
+ PC (program counter): stores address to load next instruction
+ MAR (memory address register): external memory transference adress
+ MBR (memory buffer register): external memory data to transfer
+ PSW: detects anything wrong


** RAM memory :memory:calculate:DRAM:SRAM:
+ stores apps and info loaded by the CPU
+ stores data used while processing other data
+ not sequencial, you can access an address at any given time, (Random Access Memory)
+ only works if has electrical currency
+ has storage (4MB) and velocity (1600mhz)

*** SRAM or DRAM:
| SRAM                     | DRAM                                                   |
| 1b = 5/7 transistors     | 1b = 1 transistor AND 1 capacitor                      |
| don't require recharging | uses capacitor to store value, so it needs to recharge |
| used as cache memory     | used as main memory                                    |

**** DRAM can be:
+ synchronous
  synchronized with CPU (SDRAM, DDR, DDR2)
+ asynchronous
  not synchronized with CPU (DRAM, FPM, EDO, BEDO)

*** classification according to the module type
+ SIMM (single In line Memory Module): one electrical contact is equal to the another
+ DIMM (Dual In line Memory Module): two sides are independent

*** calculate total adresses in memory
*N = 2^E*
=E = adress band=
=N = number of adresses=
ex: if the memory stores 6 bits in each adress
  + N = 2^6
  + N = 64 adresses


** permanent memory
+ RAM only stores data if it's provided with energy, if not, all data is lost
+ actually, HDs and SSDs lead this market


** motherboard :bus:DB:AB:CB:
+ provides inergy
+ periferals, CPU and memory are attached to it (system bus [barramento em português])

*** bus
+ DB (data bus): CPU <-> component
+ AB (address bus): CPU -> RAM
+ CB (control bus): anything <-comunication-> anything

[[./images/bus.jpg]]
=BC = CB, BE = AB, BD = DB=

*example case*: CPU nedds data stored at memory adress 37, a BE with 10 "wires"
would carry the value 0000100101, after the memory retrieves the value at adress 37,
the data "7510" would be carried by the DB, the data about clock (it is necessary to make it synchronous),
and other things are carried by the CB

*fun fact*: the amount of all the bus wires is equal to the CPU pins

**** find the number of addresses addressed by the bus :address:AD:convert:binary:
*N = 2^L*
=N = addressable memory addressed=
=L = DB band=

*or be: find a number that 2^it is equal to the supported addresses*

ex: a CPU adresses 4MB of adresses, whats the band of the AB?
+ 4MB = 2^L
  + 4MB = 2^2 (4) + 2^20 (MB)
+ 4MB = 2^22 (22 bits)

table of conversion
| unity | value |
| 1k    |   2^10 |
| 1M    |   2^20 |
| 1G    |   2^30 |
| 1T    | 2^40   |



** CISC vs RISC computers :CISC:RISC:
+ cisc are the machines we use normally
+ risc are expensive

| CISC                                         | RISC                                |
|----------------------------------------------+-------------------------------------|
| complex instructions taking multiple cycles  | simple instructions taking 1 cycles |
| any instruction may reference memory         | only LOADS/STORES reference memory  |
| not pipelined or less pipelined              | highly pipelined                    |
| instructions interpreted by the microprogram | instructions executed by hardware   |
| variable format instructions                 | fixed format instructions           |
| many instructions and models                 | few instructions and models         |
| complexity is in the microprogram            | complexity is in the compiler       |
| single register set                          | multiple register set               |
|----------------------------------------------+-------------------------------------+


* software

** OS (operating system) :batch:real-time:time-sharing:
+ abstraction so apps run above it don't need to know what's below (hardware)
+ alocates memory in main memory (RAM)
+ gives processes access to CPU
+ history
  + in the 70s, UNIX is created
  + in the 80s, Ms DOS is created
  + the feature of windows in OSs made a big difference in the market
  + actually, embedded systems are the news
+ are classified in *batch*, *real-tme* and *time-sharing*
  + batch: manages multiple jobs in parallel
  + real-time (RTOS): a large number of events are processed in a short time (ex: airline traffic control)
  + time sharing: CPU performs many tasks by switches are so frequent that
    the user can interact with each program while it is running, allows multiple users (ex: linux)


** internet
+ in the 70s, the americans connected many computers so they could comunicate (ARPANET)
+ many networks quickly emerged, becoming the internet


** drivers
+ code to control a specific device
+ can be serial or paralel
  [[./images/paralel_serial_drivers.jpg]]
