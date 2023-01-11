library IEEE;
use IEEE.std_logic_1164.all;

entity baba2 is
	port(a3,a2,a1,a0,L,clk : in std_logic;
		  s1,s2: inout std_logic;
		  Q3,Q2,Q1,Q0 : out std_logic
		  );
		  signal clk_sig : std_logic;
end baba2;

architecture st1 of baba2 is
begin
	ck: process(clk,S1,S2) is
	variable count:integer :=0;
	begin
		if(rising_edge(clk)) then
			count:=count+1;
			if(count=16666667)then
				clk_sig <=not(clk_sig );
				count:=0;
			end if;
		end if;
		S1<=clk_sig;
		S2<=clk_sig;
	end process;
	
	reg: process(L,a3,a2,a1,a0) is
		begin
			if(L = '0') then
				Q3<='1';
				Q3<=A3;
			end if;
	end process;
end st1;