module aes_main(clk,data_in,key,data_out);
input clk;
input [127:0] data_in,key;
output [127:0] data_out;
wire[127:0] key_s, key_s0, key_s1, key_s2, key_s3, key_s4, key_s5, key_s6, key_s7,
key_s8, key_s9;
wire[127:0] r_data_out, r0_data_out, r1_data_out, r2_data_out, r3_data_out, r4_data_out,
r5_data_out, r6_data_out, r7_data_out, r8_data_out, r9_data_out;
assign r_data_ou t =data_in^key_s;
Aes_key_expand_128 a0(clk,key, key_s, key_s0, key_s1, key_s2, key_s3, key_s4,
key_s5, key_s6, key_s7, key_s8, key_s9);
round r0(clk, r_data_out, key_s0, r0_data_out);
round r1(clk,r0_data_out,key_s1,r1_data_out);
round r2(clk,r1_data_out,key_s2,r2_data_out);
round r3(clk,r2_data_out,key_s3,r3_data_out);
round r4(clk,r3_data_out,key_s4,r4_data_out);
round r5(clk,r4_data_out,key_s5,r5_data_out);
round r6(clk,r5_data_out,key_s6,r6_data_out);
round r7(clk,r6_data_out,key_s7,r7_data_out);
round r8(clk,r7_data_out,key_s8,r8_data_out);
last_round r9(clk,r8_data_out,key_s9,r9_data_out);
assign data_out=r9_data_out;
endmodule
Module aes_key_expand_128(clk,key, key_s0, key_s1, key_s2, key_s3, key_s4, key_s5,
key_s6, key_s7, key_s8, key_s9, key_s10);
input [127:0] key;
input clk;
Output[127:0] key_s0, key_s1 ,key_s2, key_s3, key_s4, key_s5, key_s6, key_s7, key_s8,
key_s9, key_s10;
reg[31:0] w0,w1,w2,w3, w4, w5, w6, w7, w8, w9, w10, w11, w12, w13, w14, w15, w16,
w17,w18, w19, w20, w21, w22, w23, w24, w25, w26, w27, w28, w29, w30, w31, w32,
w33,w34, w35, w36, w37, w38, w39, w40, w41, w42, w43;
wire[31:0]
subword,subword2,subword3,subword4,subword5,subword6,subword7,subword8,
subword9,subword10;
wire [7:0] rcon, rcon2,rcon3,rcon4,rcon5, rcon6, rcon7,rcon8,rcon9,rcon10;
always @*
begin
w0 = key[127:096];
w1 = key[095:064];

w2 = key[063:032];
w3 = key[031:000];
w4 = key[127:096]^subword^{8'h01,24'b0};
w5 = key[095:064]^key[127:096]^subword^{8'h01,24'b0};
w6 = key[063:032]^key[095:064]^key[127:096]^subword^{8'h01,24'b0};
w7 = key[127:096]^key[095:064]^key[063:032]^key[031:000]^subword^{8'h01,24'b0};
w8 = w4^subword2^{rcon2,24'b0};
w9 = w5^w4^subword2^{rcon2,24'b0};
w10 = w6^w5^w4^subword2^{rcon2,24'b0};
w11 = w7^w6^w5^w4^subword2^{rcon2,24'b0};
w12 = w8^subword3^{rcon3,24'b0};
w13 = w8^w9^subword3^{rcon3,24'b0};
w14 = w8^w9^w10^subword3^{rcon3,24'b0};
w15 = w8^w9^w10^w11^subword3^{rcon3,24'b0};
w16 = w12^subword4^{rcon4,24'b0};
w17 = w12^w13^subword4^{rcon4,24'b0};
w18 = w12^w13^w14^subword4^{rcon4,24'b0};
w19 = w12^w13^w14^w15^subword4^{rcon4,24'b0};
w20 = w16^subword5^{rcon5,24'b0};
w21 = w16^w17^subword5^{rcon5,24'b0};
w22 = w16^w17^w18^subword5^{rcon5,24'b0};
w23 = w16^w17^w18^w19^subword5^{rcon5,24'b0};
w24 = w20^subword6^{rcon6,24'b0};
w25 = w20^w21^subword6^{rcon6,24'b0};
w26 = w20^w21^w22^subword6^{rcon6,24'b0};
w27 = w20^w21^w22^w23^subword6^{rcon6,24'b0};
w28 = w24^subword7^{rcon7,24'b0};
w29 = w24^w25^subword7^{rcon7,24'b0};
w30 = w24^w25^w26^subword7^{rcon7,24'b0};
w31 = w24^w25^w26^w27^subword7^{rcon7,24'b0};

w32 = w28^subword8^{rcon8,24'b0};
w33 = w28^w29^subword8^{rcon8,24'b0};
w34 = w28^w29^w30^subword8^{rcon8,24'b0};
w35 = w28^w29^w30^w31^subword8^{rcon8,24'b0};
w36 = w32^subword9^{rcon9,24'b0};
w37 = w32^w33^subword9^{rcon9,24'b0};
w38 = w32^w33^w34^subword9^{rcon9,24'b0};
w39 = w32^w33^w34^w35^subword9^{rcon9,24'b0};
w40 = w36^subword10^{rcon10,24'b0};
w41 = w36^w37^subword10^{rcon10,24'b0};
w42 = w36^w37^w38^subword10^{rcon10,24'b0};
w43 = w36^w37^w38^w39^subword10^{rcon10,24'b0};
end
aes_rcon r1(clk,rcon,rcon2,rcon3,rcon4,rcon5,rcon6,rcon7,rcon8,rcon9,rcon10);
sbox u0(w3[23:16],subword[31:24]);
sbox u1(w3[15:8], subword[23:16]);
sbox u2(w3[7:0], subword[15:8]);
sbox u3(w3[31:24], subword[7:0]);
sbox u4(w7[23:16], subword2[31:24]);
sbox u5(w7[15:08], subword2[23:16]);
sbox u6(w7[7:0], subword2[15:8]);
sbox u7(w7[31:24], subword2[7:0]);
sbox u8(w11[23:16], subword3[31:24]);
sbox u9(w11[15:8], subword3[23:16]);
sbox u10(w11[7:0], subword3[15:08]);
sbox u11(w11[31:24], subword3[7:0]);
sbox u12(w15[23:16], subword4[31:24]);
sbox u13(w15[15:08], subword4[23:16]);
sbox u14(w15[7:0], subword4[15:8]);
sbox u15(w15[31:24], subword4[7:0]);

sbox u16(w19[23:16],subword5[31:24]);
sbox u17(w19[15:8], subword5[23:16]);
sbox u18(w19[7:0], subword5[15:8]);
sbox u19(w19[31:24], subword5[7:0]);
sbox u20(w23[23:16], subword6[31:24]);
sbox u21(w23[15:8], subword6[23:16]);
sbox u22(w23[7:0], subword6[15:8]);
sbox u23(w23[31:24], subword6[7:0]);
sbox u24(w27[23:16], subword7[31:24]);
sbox u25(w27[15:08], subword7[23:16]);
sbox u26(w27[7:0], subword7[15:8]);
sbox u27(w27[31:24], subword7[7:0]);
sbox u28(w31[23:16], subword8[31:24]);
sbox u29(w31[15:08], subword8[23:16]);
sbox u30(w31[7:0], subword8[15:8]);
sbox u31(w31[31:24], subword8[7:0]);
sbox u32(w35[23:16], subword9[31:24]);
sbox u33(w35[15:08], subword9[23:16]);
sbox u34(w35[7:0], subword9[15:8]);
sbox u35(w35[31:24], subword9[7:0]);
sbox u36(w39[23:16], subword10[31:24]);
sbox u37(w39[15:08], subword10[23:16]);
sbox u38(w39[7:0], subword10[15:8]);
sbox u39(w39[31:24], subword10[7:0]);
assign key_s0={w0,w1,w2,w3};
assign key_s1={w4,w5,w6,w7};
assign key_s2={w8,w9,w10,w11};
assign key_s3={w12,w13,w14,w15};
assign key_s4={w16,w17,w18,w19};
assign key_s5={w20,w21,w22,w23};

assign key_s6={w24,w25,w26,w27};
assign key_s7={w28,w29,w30,w31};
assign key_s8={w32,w33,w34,w35};
assign key_s9={w36,w37,w38,w39};
assign key_s10={w40,w41,w42,w43};
endmodule
module aes_rcon(clk,out,out2,out3,out4,out5,out6,out7,out8,out9,out10);
input clk;
output [7:0] out,out2,out3,out4,out5,out6,out7,out8,out9,out10;
assign out = frcon(0);
assign out2 = frcon(1);
assign out3 = frcon(2);
assign out4 = frcon(3);
assign out5 = frcon(4);
assign out6 = frcon(5);
assign out7 = frcon(6);
assign out8 = frcon(7);
assign out9 = frcon(8);
assign out10 = frcon(9);
function [7:0]frcon;
input [3:0] i;
case(i)
4'h0: frcon=8'h01; //1
4'h1: frcon=8'h02; //x
4'h2: frcon=8'h04; //x^2
4'h3: frcon=8'h08; //x^3
4'h4: frcon=8'h10; //x^4
4'h5: frcon=8'h20; //x^5
4'h6: frcon=8'h40; //x^6
4'h7: frcon=8'h80; //x^7
4'h8: frcon=8'h1b; //x^8
4'h9: frcon=8'h36; //x^9
default: frcon=8'h00;

endcase
endfunction
endmodule
module last_round(clk,data_in,key_in,data_out_last);
input clk;
input [127:0]data_in;
input [127:0]key_in;
output [127:0] data_out_last;
wire [127:0] sub_data_out,shift_data_out;
subbytes s1(clk,data_in,sub_data_out);
shiftrows s2(clk,sub_data_out,shift_data_out);
assign data_out_last=shift_data_out^key_in;
endmodule
module mixcolumn(clk,data_in,data_out);
input clk;
input [127:0] data_in;
output [127:0] data_out;
wire [31:0] n1,n2,n3,n4;
wire [31:0] n_tmp_out1, n_tmp_out2, n_tmp_out3, n_tmp_out4;
assign n1 = data_in[127:96];
assign n2=data_in[95:64];
assign n3=data_in[63:32];
assign n4=data_in[31:0];
mul_32 m1 (clk,n1,n_tmp_out1);
mul_32 m2 (clk,n2,n_tmp_out2);
mul_32 m3 (clk,n3,n_tmp_out3);
mul_32 m4 (clk,n4,n_tmp_out4);
assign data_out={n_tmp_out1,n_tmp_out2,n_tmp_out3,n_tmp_out4};
endmodule
module mul_2(clk,data_in,data_out);

input[7:0] data_in;
input clk;
output reg [7:0]data_out;
always@(posedge clk)
data_out<={data_in[6:0],1'b0} ^ (8'h1b & {8{data_in[7]}});
endmodule
module mul_3(clk,data_in,data_out);
input clk;
input [7:0]data_in;
output [7:0] data_out;
wire [7:0]tmp_out;
mul_2 m1(clk,data_in,tmp_out);
assign data_out=tmp_out^data_in;
endmodule
module mul_32(clk,m_data_in,m_data_out);
input clk;
input [31:0]m_data_in;
output [31:0] m_data_out;
wire [7:0] tmp1,tmp2,tmp3,tmp4;
wire [7:0] ma0,ma1,ma2,ma3;
wire [7:0] m2_tmp_out1,m2_tmp_out2,m2_tmp_out3,m2_tmp_out4;
wire [7:0] m3_tmp_out1,m3_tmp_out2,m3_tmp_out3,m3_tmp_out4;
assign tmp1=m_data_in[31:24];
assign tmp2=m_data_in[23:16];
assign tmp3=m_data_in[15:8];
assign tmp4=m_data_in[7:0];
begin
mul_2 m1 (clk,tmp1,m2_tmp_out1);
mul_2 m2 (clk,tmp2,m2_tmp_out2);
mul_2 m3 (clk,tmp3,m2_tmp_out3);
mul_2 m4 (clk,tmp4,m2_tmp_out4);

mul_3 m5( clk,tmp1,m3_tmp_out1);
mul_3 m6( clk,tmp2,m3_tmp_out2);
mul_3 m7( clk,tmp3,m3_tmp_out3);
mul_3 m8( clk,tmp4,m3_tmp_out4);
end
assign ma0 = m2_tmp_out1 ^m3_tmp_out2^tmp3^tmp4;
assign ma1 = tmp1 ^m2_tmp_out2 ^m3_tmp_out3 ^ tmp4;
assign ma2 = tmp1^tmp2 ^ m2_tmp_out3 ^m3_tmp_out4;
assign ma3 = m3_tmp_out1 ^tmp2^tmp3^m2_tmp_out4;
assign m_data_out = {ma0,ma1,ma2,ma3};
endmodule
module round(clk,data_in,key_in,data_out);
input clk;
input [127:0]data_in,key_in;
output [127:0] data_out;
wire [127:0]sub_data_out,shift_data_out,mix_data_out;
subbytes a1(clk,data_in,sub_data_out);
shiftrows a2(clk,sub_data_out,shift_data_out);
mixcolumn a3(clk,shift_data_out,mix_data_out);
assign data_out=mix_data_out^key_in;
endmodule
module sbox(data,dout);
input [7:0] data;
output reg [7:0] dout;
always@(data)
begin
case (data) //substitution table
8'h00 : dout <= 8'h63;
8'h01 : dout <= 8'h7c;
8'h02 : dout <= 8'h77;

8'h03 : dout <= 8'h7b;
8'h04 : dout <= 8'hf2;
8'h05 : dout <= 8'h6b;
8'h06 : dout <= 8'h6f;
8'h07 : dout <= 8'hc5;
8'h08 : dout <= 8'h30;
8'h09 : dout <= 8'h01;
8'h0a : dout <= 8'h67;
8'h0b : dout <= 8'h2b;
8'h0c : dout <= 8'hfe;
8'h0d : dout <= 8'hd7;
8'h0e : dout <= 8'hab;
8'h0f : dout <= 8'h76;
8'h10 : dout <= 8'hca;
8'h11 : dout <= 8'h82;
8'h12 : dout <= 8'hc9;
8'h13 : dout <= 8'h7d;
8'h14 : dout <= 8'hfa;
8'h15 : dout <= 8'h59;
8'h16 : dout <= 8'h47;
8'h17 : dout <= 8'hf0;
8'h18 : dout <= 8'had;
8'h19 : dout <= 8'hd4;
8'h1a : dout <= 8'ha2;
8'h1b : dout <= 8'haf;
8'h1c : dout <= 8'h9c;
8'h1d : dout <= 8'ha4;
8'h1e : dout <= 8'h72;
8'h1f : dout <= 8'hc0;
8'h20 : dout <= 8'hb7;
8'h21 : dout <= 8'hfd;
8'h22 : dout <= 8'h93;
8'h23 : dout <= 8'h26;
8'h24 : dout <= 8'h36;
8'h25 : dout <= 8'h3f;
8'h26 : dout <= 8'hf7;
8'h27 : dout <= 8'hcc;

8'h28 : dout <= 8'h34;
8'h29 : dout <= 8'ha5;
8'h2a : dout <= 8'he5;
8'h2b : dout <= 8'hf1;
8'h2c : dout <= 8'h71;
8'h2d : dout <= 8'hd8;
8'h2e : dout <= 8'h31;
8'h2f : dout <= 8'h15;
8'h30 : dout <= 8'h04;
8'h31 : dout <= 8'hc7;
8'h32 : dout <= 8'h23;
8'h33 : dout <= 8'hc3;
8'h34 : dout <= 8'h18;
8'h35 : dout <= 8'h96;
8'h36 : dout <= 8'h05;
8'h37 : dout <= 8'h9a;
8'h38 : dout <= 8'h07;
8'h39 : dout <= 8'h12;
8'h3a : dout <= 8'h80;
8'h3b : dout <= 8'he2;
8'h3c : dout <= 8'heb;
8'h3d : dout <= 8'h27;
8'h3e : dout <= 8'hb2;
8'h3f : dout <= 8'h75;
8'h40 : dout <= 8'h09;
8'h41 : dout <= 8'h83;
8'h42 : dout <= 8'h2c;
8'h43 : dout <= 8'h1a;
8'h44 : dout <= 8'h1b;
8'h45 : dout <= 8'h6e;
8'h46 : dout <= 8'h5a;
8'h47 : dout <= 8'ha0;
8'h48 : dout <= 8'h52;
8'h49 : dout <= 8'h3b;
8'h4a : dout <= 8'hd6;
8'h4b : dout <= 8'hb3;
8'h4c : dout <= 8'h29;

8'h4d : dout <= 8'he3;
8'h4e : dout <= 8'h2f;
8'h4f : dout <= 8'h84;
8'h50 : dout <= 8'h53;
8'h51 : dout <= 8'hd1;
8'h52 : dout <= 8'h00;
8'h53 : dout <= 8'hed;
8'h54 : dout <= 8'h20;
8'h55 : dout <= 8'hfc;
8'h56 : dout <= 8'hb1;
8'h57 : dout <= 8'h5b;
8'h58 : dout <= 8'h6a;
8'h59 : dout <= 8'hcb;
8'h5a : dout <= 8'hbe;
8'h5b :dout <= 8'h39;
8'h5c : dout <= 8'h4a;
8'h5d : dout <= 8'h4c;
8'h5e : dout <= 8'h58;
8'h5f : dout <= 8'hcf;
8'h60 : dout <= 8'hd0;
8'h61 : dout <= 8'hef;
8'h62 : dout <= 8'haa;
8'h63 : dout <= 8'hfb;
8'h64 : dout <= 8'h43;
8'h65 : dout <= 8'h4d;
8'h66 :dout <= 8'h33;
8'h67 : dout <= 8'h85;
8'h68 : dout <= 8'h45;
8'h69 : dout <= 8'hf9;
8'h6a : dout <= 8'h02;
8'h6b : dout <= 8'h7f;
8'h6c : dout <= 8'h50;
8'h6d : dout <= 8'h3c;
8'h6e : dout <= 8'h9f;
8'h6f : dout <= 8'ha8;
8'h70 : dout <= 8'h51;
8'h71 : dout <= 8'ha3;

8'h72 : dout <= 8'h40;
8'h73 : dout <= 8'h8f;
8'h74 : dout <= 8'h92;
8'h75 : dout <= 8'h9d;
8'h76 : dout <= 8'h38;
8'h77 : dout <= 8'hf5;
8'h78 : dout <= 8'hbc;
8'h79 : dout <= 8'hb6;
8'h7a : dout <= 8'hda;
8'h7b : dout <= 8'h21;
8'h7c : dout <= 8'h10;
8'h7d : dout <= 8'hff;
8'h7e : dout <= 8'hf3;
8'h7f : dout <= 8'hd2;
8'h80 : dout <= 8'hcd;
8'h81 : dout <= 8'h0c;
8'h82 : dout <= 8'h13;
8'h83 : dout <= 8'hec;
8'h84 : dout <= 8'h5f;
8'h85 : dout <= 8'h97;
8'h86 : dout <= 8'h44;
8'h87 : dout <= 8'h17;
8'h88 : dout <= 8'hc4;
8'h89 : dout <= 8'ha7;
8'h8a : dout <= 8'h7e;
8'h8b : dout <= 8'h3d;
8'h8c : dout <= 8'h64;
8'h8d : dout <= 8'h5d;
8'h8e : dout <= 8'h19;
8'h8f : dout <= 8'h73;
8'h90 : dout <= 8'h60;
8'h91 : dout <= 8'h81;
8'h92 : dout <= 8'h4f;
8'h93 : dout <= 8'hdc;
8'h94 : dout <= 8'h22;
8'h95 : dout <= 8'h2a;
8'h96 : dout <= 8'h90;

8'h97 : dout <= 8'h88;
8'h98 : dout <= 8'h46;
8'h99 : dout <= 8'hee;
8'h9a : dout <= 8'hb8;
8'h9b : dout <= 8'h14;
8'h9c : dout <= 8'hde;
8'h9d : dout <= 8'h5e;
8'h9e : dout <= 8'h0b;
8'h9f : dout <= 8'hdb;
8'ha0 : dout <= 8'he0;
8'ha1 : dout <= 8'h32;
8'ha2 : dout <= 8'h3a;
8'ha3 : dout <= 8'h0a;
8'ha4 : dout <= 8'h49;
8'ha5 : dout <= 8'h06;
8'ha6 : dout <= 8'h24;
8'ha7 : dout <= 8'h5c;
8'ha8 : dout <= 8'hc2;
8'ha9 : dout <= 8'hd3;
8'haa : dout <= 8'hac;
8'hab : dout <= 8'h62;
8'hac : dout <= 8'h91;
8'had : dout <= 8'h95;
8'hae : dout <= 8'he4;
8'haf : dout <= 8'h79;
8'hb0 : dout <= 8'he7;
8'hb1 : dout <= 8'hc8;
8'hb2 : dout <= 8'h37;
8'hb3 : dout <= 8'h6d;
8'hb4 : dout <= 8'h8d;
8'hb5 : dout <= 8'hd5;
8'hb6 : dout <= 8'h4e;
8'hb7 : dout <= 8'ha9;
8'hb8 : dout <= 8'h6c;
8'hb9 : dout <= 8'h56;
8'hba : dout <= 8'hf4;
8'hbb : dout <= 8'hea;

8'hbc : dout <= 8'h65;
8'hbd : dout <= 8'h7a;
8'hbe : dout <= 8'hae;
8'hbf : dout <= 8'h08;
8'hc0 : dout <= 8'hba;
8'hc1 : dout <= 8'h78;
8'hc2 : dout <= 8'h25;
8'hc3 : dout <= 8'h2e;
8'hc4 : dout <= 8'h1c;
8'hc5 : dout <= 8'ha6;
8'hc6 : dout <= 8'hb4;
8'hc7 : dout <= 8'hc6;
8'hc8 : dout <= 8'he8;
8'hc9 : dout <= 8'hdd;
8'hca : dout <= 8'h74;
8'hcb : dout <= 8'h1f;
8'hcc : dout <= 8'h4b;
8'hcd : dout <= 8'hbd;
8'hce : dout <= 8'h8b;
8'hcf : dout <= 8'h8a;
8'hd0 : dout <= 8'h70;
8'hd1 : dout <= 8'h3e;
8'hd2 : dout <= 8'hb5;
8'hd3 : dout <= 8'h66;
8'hd4 : dout <= 8'h48;
8'hd5 : dout <= 8'h03;
8'hd6 : dout <= 8'hf6;
8'hd7 : dout <= 8'h0e;
8'hd8 : dout <= 8'h61;
8'hd9 : dout <= 8'h35;
8'hda : dout <= 8'h57;
8'hdb : dout <= 8'hb9;
8'hdc : dout <= 8'h86;
8'hdd : dout <= 8'hc1;
8'hde : dout <= 8'h1d;
8'hdf : dout <= 8'h9e;
8'he0 : dout <= 8'he1;

8'he1 : dout <= 8'hf8;
8'he2 : dout <= 8'h98;
8'he3 : dout <= 8'h11;
8'he4 : dout <= 8'h69;
8'he5 : dout <= 8'hd9;
8'he6 : dout <= 8'h8e;
8'he7 : dout <= 8'h94;
8'he8 : dout <= 8'h9b;
8'he9 : dout <= 8'h1e;
8'hea : dout <= 8'h87;
8'heb : dout <= 8'he9;
8'hec : dout <= 8'hce;
8'hed : dout <= 8'h55;
8'hee : dout <= 8'h28;
8'hef : dout <= 8'hdf;
8'hf0 : dout <= 8'h8c;
8'hf1 : dout <= 8'ha1;
8'hf2 : dout <= 8'h89;
8'hf3 : dout <= 8'h0d;
8'hf4 : dout <= 8'hbf;
8'hf5 : dout <= 8'he6;
8'hf6 : dout <= 8'h42;
8'hf7 : dout <= 8'h68;
8'hf8 : dout <= 8'h41;
8'hf9 : dout <= 8'h99;
8'hfa : dout <= 8'h2d;
8'hfb : dout <= 8'h0f;
8'hfc : dout <= 8'hb0;
8'hfd : dout <= 8'h54;
8'hfe : dout <= 8'hbb;
8'hff : dout <= 8'h16;
default : dout <= 8'h00;
endcase
end
endmodule
module shiftrows(clk,data_in,data_out);

input clk;
input [127:0]data_in;
output reg [127:0]data_out=128'b0;
always@(posedge clk)
begin
data_out[127:120]<=data_in[95:88];
data_out[119:112]<=data_in[55:48];
data_out[111:104]<=data_in[15:8];
data_out[103:96]<= data_in[103:96];
data_out[95:88]<=data_in[63:56];
data_out[87:80]<=data_in[23:16];
data_out[79:72]<=data_in[111:104];
data_out[71:64]<=data_in[71:64];
data_out[63:56]<=data_in[31:24];
data_out[55:48]<=data_in[119:112];
data_out[47:40]<=data_in[79:72];
data_out[39:32]<=data_in[39:32];
data_out[31:24]<=data_in[127:120];
data_out[23:16]<=data_in[87:80];
data_out[15:8]<= data_in[47:40];
data_out[7:0]<=data_in[7:0];
end
endmodule
module subbytes(clk,data,s_data_out);
input clk;
input [127:0]data;
output reg [127:0]s_data_out;
wire [127:0] tmp_out;
sbox q0(data[127:120],tmp_out[127:120] );
sbox q1( data[119:112],tmp_out[119:112] );
sbox q2( data[111:104],tmp_out[111:104] );
sbox q3( data[103:96],tmp_out[103:96] );

sbox q4( data[95:88],tmp_out[95:88] );
sbox q5( data[87:80],tmp_out[87:80] );
sbox q6( data[79:72],tmp_out[79:72] );
sbox q7( data[71:64],tmp_out[71:64] );
sbox q8( data[63:56],tmp_out[63:56] );
sbox q9( data[55:48],tmp_out[55:48] );
sbox q10(data[47:40],tmp_out[47:40] );
sbox q11(data[39:32],tmp_out[39:32] );
sbox q12(data[31:24],tmp_out[31:24] );
sbox q13(data[23:16],tmp_out[23:16] );
sbox q14(data[15:8],tmp_out[15:8] );
sbox q15(data[7:0],tmp_out[7:0] );
always@(posedge clk)
begin
s_data_out<=tmp_out;
end
endmodule


//testbench
module aes_main_tb();
reg clk;
reg [127:0] data_in,key;
wire [127:0] data_out;
aes_main test(clk,data_in,key,data_out);
always #5 clk = ~clk;
initial begin
$monitor("clk=%b,data_in=%b,key=%b,data_out=%b",clk,data_in,key,data_out);
clk=1;
data_in=0123456789;key=0000000000987654321;
end
endmodule
