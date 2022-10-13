library IEEE;
use IEEE.Std_logic_1164.all;
use IEEE.Numeric_Std.all;

entity FSM is
end;

architecture bench of Lab_8_tb is
  type stateMoore_type is (GNS, YNS, GEW, YEW);
  signal stateMoore_reg, statemoore_next : stateMoore_type;
  component traffic_light
  port(
  clk,rst,carew,carns: in std_logic;
  nsg,nsy,nsr,ewg,ewy,ewr: out std_logic
);
end component;

signal inputs_tb: std_logic_vector(2 downto 0);
signal clk_tb: std_logic;
signal outputs_tb: std_logic_vector(5 downto 0);
constant clock_period: time := 10 ns;

begin
uut: traffic_light port map (
  carew => inputs_tb(0),
  carns => inputs_tb(1),
  rst => inputs_tb(2),
  clk => clk_tb,
  nsg => outputs_tb(0),
  nsy => outputs_tb(1),
  nsr => outputs_tb(2),
  ewg => outputs_tb(3),
  ewy => outputs_tb(4),
  ewr => outputs_tb(5)
);

stimulus: process
   begin
    inputs_tb = “000”;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
    wait for 10ns;
    inputs_tb <= inputs_tb + '1';
end process stimulus;

clk_process:process
  begin
    clk <= '0';
    wait for 10ns;
    clk <= '1';
    wait for 10ns;
end process clk_process;
end;
