# Hardwired vs. Microprogrammed Control Units
A central processing unit (CPU) relies on a control unit to manage the execution of instructions. The control unit interprets instructions fetched from memory and directs the necessary hardware components using control signals to execute them. This process ensures the correct sequence of operations within a computer system. Control units are broadly classified into two types: hardwired and microprogrammed. Each type has its advantages and is suited for different applications. 

## Hardwired Control Unit 

A hardwired control unit is a sequential circuit that generates control signals using combinational logic. It consists of logic gates, flip-flops, and decoders to produce specific signals for executing instructions. Since the control logic is physically wired, modifications require redesigning the circuit, making it less flexible. However, hardwired control units offer faster instruction execution because signals propagate through dedicated paths without additional interpretation. These units are ideal for applications requiring high-speed processing, such as embedded systems and specialized processors. Despite their speed, the complexity of adding new instructions limits their scalability and adaptability in modern processors.

## Microprogrammed Control Unit

A microprogrammed control unit is a type of control unit in the central processing unit (CPU) that stores binary control values as words in memory and uses a microcode to execute instructions. The microcode is a set of microinstructions that can be modified or changed allowing for more flexibility. This defines how the machine level instructions are to be executed. It is a relatively simple logic circuit that is capable of handling complex instructions typically used in computers that make use of Complex Instruction Set Computers (CISC). It is usually stored in the control memory of a microprogrammed CPU. 


## Decoding in Control Units 

Both types of control units use decoding as a way to interpret instructions. Once the decoding process is complete, each unit can generate the appropriate control signal and execute it. In hardwired control units decoding is more direct, while in microprogrammed control units decoding can be more complex.

### Hardwired Decoding

To start the process of decoding first the CPU fetches an instruction from memory and stores it in the Instruction Register (IR). This instruction consists of an operation code, also known as opcode, and operands. The decoder then generates a set of signals based on the opcode. These signals generated for:  
* Register Selection (Which registers to read and write to)
* ALU Operation (ADD, SUB, AND, OR, etc.)
* Memory Access (Load, Store)
* Instruction Sequencing (Fetch, Decode, Execute, Write-back)

Once these signals are made, they are then sent to the CPU to perform the set of instructions. A clock and a finite state machine is used to ensure the signals are performed in the correct order. 

### Microprogrammed decoding

In microprogrammed decoding the Control Address Register (CAR) provides an address to the Control Memory (CM), a component that stores microinstructions in a structured format. The microinstruction is then fetched and temporarily stored in the Control Data Register (CDR). The microinstruction is then sent to a   decoder circuit to generate control signals. Unlike in hardwired decoding where instructions are direct and take one step to decode, in microprogrammed decoding decoding is broken up into two steps. First, the decoder takes the microinstruction and splits it into fields. Once the microinstruction is decoded, the decoded information is then sent out to generate control signals. 


## Horizontal and Vertical Microprogrammed Control Units 

A horizontal microprogrammed control unit uses wider instructions where each bit directly controls a CPU component. This allows for faster execution due to the lack of decoding. A vertical microprogrammed control unit uses more compact encoded microinstructions to reduce memory; however it requires a decoder to expand microinstructions into signals. The advantage of a horizontal control unit is faster execution compared to a vertical horizontal control unit. A disadvantage is it requires more memory due to longer microinstructions and less flexibility because it is harder to modify the longer microinstructions. Horizontal control unit is able to support longer control words while a vertical control unit is able to support shorter code words.

## Pros and Cons (Hardwired vs Microprogrammed)

An advantage of a microprogrammed control unit is that it is easier to modify and update compared to a hardwired control unit. This allows manufacturers the ability to fix bugs, add instruction, or optimize execution. However, a microprogrammed control unit often runs slower in speed compared to its counterpart due to having to fetch the microinstructions from the control memory. It also has to put aside extra memory for the storage of the microinstructions. 

On the other hand, a hardwired control unit excels in speed because it directly generates control signals using combinational logic, eliminating the need to fetch microinstructions. This makes it well-suited for high-performance applications that require fast instruction execution. However, its primary drawback is its lack of flexibility. Any modifications, such as adding new instructions or fixing errors, require redesigning the circuit, which is complex and time-consuming. As a result, while hardwired control units are advantageous for specialized processors with fixed instruction sets, they are less adaptable to evolving computing needs.

Microprogrammed control unit’s ability to be easily modified made it a popular choice in early hardware components like the Motorola 86000 and the PDP-11. Despite being slower, the ability to fix bugs on the fly was of paramount value, especially in an era where verification methods were suboptimal and bugs were common. Nowadays, speed is much more important. And with better verification techniques, hardwired control units are much more prevalent in modern systems. 

## 

In summary, hardwired and microprogrammed control units each have their own use cases and provide different benefits. While hardwired control units are great for speed and efficiency, microprogrammed control units are useful in their flexibility and adaptability.
