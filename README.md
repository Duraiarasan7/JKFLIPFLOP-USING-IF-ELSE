JKFLIPFLOP-USING-IF-ELSE
AIM:

To implement JK flipflop using verilog and validating their functionality using their functional tables

SOFTWARE REQUIRED:

Quartus prime

THEORY

JK Flip-Flop

JK flip-flop is the modified version of SR flip-flop. It operates with only positive clock transitions or negative clock transitions. The circuit diagram of JK flip-flop is shown in the following figure.

image

This circuit has two inputs J & K and two outputs Qtt & Qtt’. The operation of JK flip-flop is similar to SR flip-flop. Here, we considered the inputs of SR flip-flop as S = J Qtt’ and R = KQtt in order to utilize the modified SR flip-flop for 4 combinations of inputs. The following table shows the state table of JK flip-flop.

image

Here, Qtt & Qt+1t+1 are present state & next state respectively. So, JK flip-flop can be used for one of these four functions such as Hold, Reset, Set & Complement of present state based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of JK flip-flop. Present Inputs Present State Next State

image

By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. Three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

image

The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=JQ(t)′+K′Q(t)Q(t+1)=JQ(t)′+K′Q(t)

Procedure 1.type the program in quartus software. 2.compiler run the program. 3.generate RTL schematic and save the logic diagram. 4.creates nodes for input and output to generate the timing diagram. 5.for different input combinations generates the timing diagram

PROGRAM

module exp7(J,K,clk,q,qbar);
input J,K,clk;
output reg q;
output reg qbar;
initial q=0;
initial qbar=1;
always @(posedge clk)
begin
q=((J&(~q))|((~K)&q));
qbar=~q;
end
endmodule
/* Program for flipflops and verify its truth table in quartus using Verilog programming. Developed by:MANIKANDAN M RegisterNumber:212224040183 */ RTL LOGIC FOR FLIPFLOPS exp7 TIMING DIGRAMS FOR FLIP FLOPS Screenshot (112) RESULTS Thus the JK flipflop using verilog and validating their functionality using their functional tables implemented.
