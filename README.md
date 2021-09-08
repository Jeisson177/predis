--Codigo creado para aplicar el signo menos o negativo de la resta

LIBRARY IEEE;
USE ieee.std_logic_1164.all;
--------------------------------------------------
ENTITY predis IS
 PORT(    decena : IN  STD_LOGIC_VECTOR(3 DOWNTO 0);--Parte de las decenas
            aux  : IN  STD_LOGIC;--Primer auxiliar de 1 bit
				auxi : IN  STD_LOGIC;--Segundo auxiliar de 1 bit
	   out_decena : OUT STD_LOGIC_VECTOR(3 DOWNTO 0);--Parte de las decenas despues de analizar el negativo
			 swA    : IN  STD_LOGIC_VECTOR(3 DOWNTO 0);--Switchs para definir el numero A
			 swB    : IN  STD_LOGIC_VECTOR(3 DOWNTO 0);--Switchs para definir el numero B
			 sws    : IN  STD_LOGIC_VECTOR(1 DOWNTO 0));--Switchs para definirla operacion a realizar
END ENTITY predis;
--------------------------------------------------
ARCHITECTURE operation OF predis IS

BEGIN
	
	predis1:PROCESS (aux, auxi ,decena)--Se inicializa el proceso con las variables
	                                   -- a usar para el IF
	BEGIN
	
	IF ((aux AND auxi) = '1') THEN--Se realiza el IF para verificar el cumplimiento de ambas condiciones
	out_decena <= "1111";--Se le asigna el valor de "1111" para las decenas y asi obtener el menos del negativo
	ELSE 
	out_decena <= decena;--Si no se cumplen las condiciones, se mantiene el valor de las decenas 
	
	END IF;--Se finalia el IF
	END PROCESS predis1;--Se finaliza el proceso
	
	END ARCHITECTURE operation;
