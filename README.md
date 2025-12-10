# SERIAL-IN-SERIAL-OUT-SHIFTREGISTER

**AIM:**

To implement  SISO Shift Register using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**SISO shift Register**

A Serial-In Serial-Out shift register is a sequential logic circuit that allows data to be shifted in and out one bit at a time in a serial manner. It consists of a cascade of flip-flops connected in series, forming a chain. The input data is applied to the first flip-flop in the chain, and as the clock pulses, the data propagates through the flip-flops, ultimately appearing at the output.

The logic circuit provided below demonstrates a serial-in serial-out (SISO) shift register. It comprises four D flip-flops that are interconnected in a sequential manner. These flip-flops operate synchronously with one another, as they all receive the same clock signal.

![image](https://github.com/naavaneetha/SERIAL-IN-SERIAL-OUT-SHIFTREGISTER/assets/154305477/e81c4072-37f9-46c6-8145-566764b74c3a)

Figure 01 4 Bit SISO Register

The synchronous nature of the flip-flops ensures that the shifting of data occurs in a coordinated manner. When the clock signal rises, the input data is sampled and stored in the first flip-flop. On subsequent clock pulses, the stored data propagates through the flip-flops, moving from one flip-flop to the next.
Each D flip-flop in the circuit has a Data (D) input, a Clock (CLK) input, and an output (Q). The D input represents the data to be loaded into the flip-flop, while the CLK input is connected to the common clock signal. The output (Q) of each flip-flop is connected to the D input of the next flip-flop, forming a cascade.

**Procedure**
1.Declare clk, sin, q (register).

2.Use always @(posedge clk).

3.Shift right: q <= {q[n-2:0], sin}.

4.Output serial bit from MSB or LSB.

5.End module.

**PROGRAM**
module shift_register_3bit (
    input  wire clk,     // clock input
    input  wire rst,     // synchronous reset
    input  wire serial_in, // serial data input
    output reg  [2:0] q   // 3-bit register output
);

always @(posedge clk) begin
    if (rst)
        q <= 3'b000;          // reset all bits
    else
        q <= {q[1:0], serial_in}; // shift left
end

endmodule



Developed by:Madhumitha V
RegisterNumber:25016067

**RTL LOGIC FOR SISO Shift Register**
<img width="1919" height="1079" alt="Screenshot 2025-12-05 230503" src="https://github.com/user-attachments/assets/29cc3af6-7738-424f-a48c-956e2ce9c224" />

**TIMING DIGRAMS FOR SISO Shift Register**
<img width="1919" height="1079" alt="Screenshot 2025-12-06 001904" src="https://github.com/user-attachments/assets/73bb0116-87e9-4711-9331-d7c4fd63e704" />

**RESULTS**
The implement of SISO Shift Register using verilog and validating their functionality using their functional tables is verified.
