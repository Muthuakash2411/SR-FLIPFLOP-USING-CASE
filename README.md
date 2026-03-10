# SR-FLIPFLOP-USING-CASE

**AIM:**

To implement  SR flipflop using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

SR Flip-Flop SR flip-flop operates with only positive clock transitions or negative clock transitions. Whereas, SR latch operates with enable signal. The circuit diagram of SR flip-flop is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/0f710028-ad52-4d3e-9276-8714cf023a25)

 
This circuit has two inputs S & R and two outputs Qtt & Qtt’. The operation of SR flipflop is similar to SR Latch. But, this flip-flop affects the outputs only when positive transition of the clock signal is applied instead of active enable. The following table shows the state table of SR flip-flop.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dabfc4f4-87e3-4cbc-9472-f89ee1b5ed30)

 
Here, Qtt & Qt+1t+1 are present state & next state respectively. So, SR flip-flop can be used for one of these three functions such as Hold, Reset & Set based on the input conditions, when positive transition of clock signal is applied. The following table shows the characteristic table of SR flip-flop. Present Inputs Present State Next State

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/dd90d16c-aec5-4290-a586-e2346b1e9eb5)

 
By using three variable K-Map, we can get the simplified expression for next state, Qt+1t+1. The three variable K-Map for next state, Qt+1t+1 is shown in the following figure.

![image](https://github.com/naavaneetha/SR-FLIPFLOP-USING-CASE/assets/154305477/473efad6-d70b-4ca7-aeb7-898bbfca319f)

 
The maximum possible groupings of adjacent ones are already shown in the figure. Therefore, the simplified expression for next state Qt+1t+1 is Q(t+1)=S+R′Q(t)Q(t+1)=S+R′Q(t)

**Procedure**

Define Inputs/Outputs: Inputs: S (Set), R (Reset), c1k (clock); Outputs: Q, Qbar.

Initialization: Set Q = 0 and Qbar = 1 at the start of the simulation.

SR Flip-Flop Logic: On posedge c1k, compute Q = S | (~R & Q).

Complementary Output: Update Qbar = R | (~S & Qbar) to maintain SR Flip-Flop behavior.

Testbench: Test with combinations of S, R, and c1k to ensure proper Set-Reset functionality.


**PROGRAM**

 Program for flipflops and verify its truth table in quartus using Verilog programming.
 ````
Developed by:MUTHUAKASH M
RegisterNumber:212225230194

module sr(s,r,clk,q,qbar);
input s,r,clk;
output reg q;
output qbar;
assign qbar=~q;
always@(posedge clk)
begin
if(s==0&&r==0)
q<=q;
else if(s==0&&r==1)
q<=0;
else if(s==1&&r==0)
q<=1;
else
q<=1'bx;
end
endmodule

````
**RTL LOGIC FOR FLIPFLOPS**


<img width="1169" height="407" alt="image" src="https://github.com/user-attachments/assets/57d27a58-ca5d-4d0b-a5f6-795dc6f194b2" />


**TIMING DIGRAMS FOR FLIP FLOPS**


<img width="1919" height="568" alt="image" src="https://github.com/user-attachments/assets/3336ebe1-7730-436c-8707-cc79ccfea99f" />



**RESULTS**

Thus the SR flipflop is implemented and verified.

