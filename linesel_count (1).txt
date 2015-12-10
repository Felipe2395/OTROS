`timescale 1ns / 1ps

module linesel_count(

	input linesel_en,
	output reg linesel
    );
integer j;
initial begin
	while(linesel_en==1)begin
		linesel=0;
		for(j=0;j<=7;j=j+1) begin
			linesel=j;
		end
		linesel=0;
	end
end
endmodule
