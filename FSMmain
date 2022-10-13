library ieee;
use ieee.std_logic_1164.all;
entity FSM is
  port(
    clk, rst,carew,carns: in std_logic := '0';
    nsg,nsy,nsr,ewg,ewy,ewr: out std_logic := '0'
  );
end FSM;

architecture arch of FSM is
type stateMoore_type is (GNS, YNS, GEW,YEW);
signal stateMoore_reg, stateMoore_next : stateMoore_type;

begin
  process(clk,rst)

begin
  if (rst = '1') then
    stateMoore_reg <= GNS;
    elsif (clk'event and clk = '1') then
      stateMoore_reg <= stateMoore_next;
    else
      null;
  end if;
  end process;

process(stateMoore_reg,carew,carns)
  begin
  stateMoore_next <= stateMoore_reg;
  case stateMoore_reg is
  when GNS =>
    nsg<='1';
    nsy<='0';
    nsr<='0';
    ewg<='0';
    ewy<='0';
    ewr<='1';

  if carew='0' then
    stateMoore_next <= GNS;
  else
    stateMoore_next <= YNS;
  end if;

  when YNS =>
    nsg<='0';
    nsy<='1';
    nsr<='0';
    ewg<='0';
    ewy<='0';
    ewr<='1';
  stateMoore_next <= GEW;
  when GEW =>
    nsg<='0';
    nsy<='0';
    nsr<='1';
    ewg<='1';
    ewy<='0';
    ewr<='0';
  if carns='0' then
  stateMoore_next <= GEW;
  else
  stateMoore_next <= YEW;
  end if;
  when YEW =>
    nsg<='0';
    nsy<='0';
    nsr<='1';
    ewg<='0';
    ewy<='1';
