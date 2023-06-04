# 2_Bit_Multiplier
A two-bit multiplier is a digital circuit that multiplies two two-bit binary numbers. It generates a four-bit output by multiplying the corresponding bits and adding them together. It's a basic component in digital systems for binary multiplication.

## Program code

module two_mult(a,b,o);   
input[1:0] a,b;   
output[4:1] o;  
wire [4:1] w;  
assign o[1]=a[0]&b[0];   
assign w[1]=a[1]&b[0];   
assign w[2]=a[0]&b[1];  
assign w[3]=a[1]&b[1];   
 
half ha1(w[1],w[2],o[2],w[4]);   
half ha2(w[3],w[4],o[3],o[4]);   
    
endmodule   

module half(a,b,sum,carry);  
input a,b;  
output sum,carry;    
xor(sum,a,b);   
and(carry,a,b);   
endmodule   
