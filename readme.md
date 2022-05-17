Tests de nivel 2

R-EA-PB Robert
R-EA-P1 Adria
R-EA-P2 Enrique

R-EB-P0-0 Victor
R-EB-P0-0 Ruben
R-EB-P1 (Altillo) Ruben


# VLAN 2 Producción - 195.85.72.0/25
(R-EA-PB Robert Con VLAN 14 Dinámica)

R-EA-PB Robert(VLAN 14) puerto 1/1 <code>sudo ifconfig enp3s0 195.85.72.2/25 up</code><br>
R-EA-P1 Adria           puerto 8/1 <code>sudo ifconfig enp3s0 195.85.72.3/25 up</code><br>
R-EA-P2 Enrique         puerto 8/1 <code>sudo ifconfig enp3s0 195.85.72.4/25 up</code><br>
R-EB-P0-0 Victor        puerto 8/1 <code>sudo ifconfig enp3s0 195.85.72.5/25 up</code><br>
R-EB-P0-1 Ruben         puerto 8/1 <code>sudo ifconfig enp3s0 195.85.72.6/25 up</code><br>
R-EB-P1 (Al) Ruben      puerto 1/1 <code>sudo ifconfig enp4s0 195.85.72.7/25 up</code><br>

P1&P2       (nivel 3) : <code>sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.1</code>

PINGS AL RESTO (nivel 2):
R-EA-PB Robert          $ ping 195.85.72.2
R-EA-P1 Adria           $ ping 195.85.72.3
R-EA-P2 Enrique         $ ping 195.85.72.4
R-EB-P0-0 Victor        $ ping 195.85.72.5
R-EB-P0-1 Ruben         $ ping 195.85.72.6
R-EB-P1 (Al) Ruben      $ ping 195.85.72.7



# VLAN 3 Comercial - 195.85.72.128/26

R-EA-PB Robert          puerto 2/1      $ sudo ifconfig enp3s0 195.85.72.130/26 up
R-EA-P1 Adria           puerto 8/3      $ sudo ifconfig enp3s0 195.85.72.131/26 up
R-EA-P2 Enrique         puerto 8/5      $ sudo ifconfig enp3s0 195.85.72.132/26 up
R-EB-P1 (Al) Ruben      puerto 1/2      $ sudo ifconfig enp4s0 195.85.72.133/26 up

P1&P2              (nivel 3) : $ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.129

PINGS AL RESTO (nivel 2):
R-EA-PB Robert          $ ping 195.85.72.130
R-EA-P1 Adria           $ ping 195.85.72.131
R-EA-P2 Enrique         $ ping 195.85.72.132
R-EB-P1 (Al) Ruben      $ ping 195.85.72.133



# VLAN 4 Administración - 195.85.72.192/26

R-EA-PB Robert                        (nivel 2) : $ sudo ifconfig enp3s0 195.85.72.194/25 up
R-EA-P1 Adria                         (nivel 2) : $ sudo ifconfig enp3s0 195.85.72.195/25 up
R-EA-P2 Enrique                       (nivel 2) : $ sudo ifconfig enp3s0 195.85.72.196/25 up

P1&P2              (nivel 3) : $ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.193 

PINGS AL RESTO (nivel 2):
R-EA-PB Robert                        $ ping 195.85.72.194/25 up
R-EA-P1 Adria                         $ ping 195.85.72.195/25 up
R-EA-P2 Enrique                       $ ping  95.85.72.196/25 up





# TODO
Hacer ping a la interfaz de los switches desde tu switch 



------------------
P2 Y P1 en VLAN 2 (administración) (Hace ping)
P2: 	$ sudo ifconfig enp3s0 38.17.33.34/28 up (nivel 2)
P1: 	$ sudo ifconfig enp3s0 38.17.33.35/28 up (nivel 2)
P1&P2:	$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.33.33 (nivel 3)

P2, P1 Y PB en VLAN 3 (atención al cliente) (Hace ping)
P2: 	$ sudo ifconfig enp3s0 38.17.32.130/26 up
P1: 	$ sudo ifconfig enp3s0 38.17.32.131/26 up
PB: 	$ sudo ifconfig enp3s0 38.17.32.132/26 up

$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.32.129
P2, P1, PSC, PSCA en VLAN 4 (almacén)
P2: 	$ sudo ifconfig enp3s0 38.17.32.194/27 up
P1: 	$ sudo ifconfig enp3s0 38.17.32.195/27 up
PSC: 	$ sudo ifconfig enp3s0 38.17.32.196/27 up
PSCA:	$ sudo ifconfig enp3s0 38.17.32.197/27 up

$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.32.193
P2, PB, PSC en VLAN 5 (postventa)
P2: 	$ sudo ifconfig enp3s0 38.17.32.226/27 up
PB: 	$ sudo ifconfig enp3s0 38.17.32.227/27 up
PSC: 	$ sudo ifconfig enp3s0 38.17.32.228/27 up
# PSCA:$ sudo ifconfig enp3s0 38.17.32.229/27 up

$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.32.225
P2, P1, PB, PSC, en VLAN 6 (servicio técnico)
P2: 	$ sudo ifconfig enp3s0 38.17.33.2/27 up (No tengo puertos)
P1:	$ sudo ifconfig enp3s0 38.17.33.3/27 up
PB:	$ sudo ifconfig enp3s0 38.17.33.4/27 up
PSC:	$ sudo ifconfig enp3s0 38.17.33.5/27 up

$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.33.1
P2, P1, PB, en VLAN 7 (ventas)
P2: 	$ sudo ifconfig enp3s0 38.17.32.2/25 up (No tengo puertos)
P1: 	$ sudo ifconfig enp3s0 38.17.32.3/25 up
PB: 	$ sudo ifconfig enp3s0 38.17.32.4/25 up

$ sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 38.17.32.1
Todos en VLAN 8 (climatización)
P2: 	$ sudo ifconfig enp3s0 38.17.33.81/28 up
P1: 	$ sudo ifconfig enp3s0 38.17.33.82/28 up
PB: 	$ sudo ifconfig enp3s0 38.17.33.83/28 up
PSC: 	$ sudo ifconfig enp3s0 38.17.33.84/28 up
PSCA:	$ sudo ifconfig enp3s0 38.17.33.85/28 up

P2,P1,PB,PSC en VLAN 9 (puntos de acceso)
P2:	$ sudo ifconfig enp3s0 38.17.33.65/28 up
P1: 	$ sudo ifconfig enp3s0 38.17.33.66/28 up
PB: 	$ sudo ifconfig enp3s0 38.17.33.67/28 up
PSC: 	$ sudo ifconfig enp3s0 38.17.33.68/28 up

Todos en VLAN 10 (seguridad) (Hace ping antes de poner el filtro, y luego no)
P2: 	$ sudo ifconfig enp3s0 38.17.33.97/28 up
P1: 	$ sudo ifconfig enp3s0 38.17.33.98/28 up
PB: 	$ sudo ifconfig enp3s0 38.17.33.99/28 up
PSC: 	$ sudo ifconfig enp3s0 38.17.33.100/28 up
PSCA:	$ sudo ifconfig enp3s0 38.17.33.101/28 up




