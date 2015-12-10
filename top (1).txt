`timescale 1ns / 1ps
////////////////////
module top(input r_enable,
input [0:95] m_data,
output reg R1, G1, B1, R2, G2, B2,
output reg [2:0] linesel_out,
output reg data_clk,
output reg regclk_out,
output reg output_en,
output reg ready
    );
	 Data_codec Data(r_enable, m_data, linesel, linesel_en, red, red2, send, enable);
	 linesel_count line(linesel_en, linesel);
	 DriverRGB Driver(red, green, blue, red2, green2, blue2, linesel, rst,
	 enable, R1, G1, B1, R2, G2, B2, linesel_out, regclk_out,
	 data_clk, output_en, ready);


endmodule
