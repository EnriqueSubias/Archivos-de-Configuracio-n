
# Tests principales de nivel 2 y nivel 3

R-EA-PB Robert

R-EA-P1 Adria

R-EA-P2 Enrique

R-EB-P0-0 Victor

R-EB-P0-0 Ruben

R-EB-P1 (Altillo) Ruben


# VLAN 2 Producción - 195.85.72.0/25
| Rack         | Name             | Puerto     | Configurar la interfaz del PC            | Pings al resto     |
|--------------|------------------|------------|------------------------------------------|--------------------|
| R-EA-PB      | Robert (VLAN 14) | puerto 1/1 | `sudo ifconfig enp3s0 195.85.72.2/25 up` | `ping 195.85.72.2` |
| R-EA-P1      | Adria            | puerto 8/1 | `sudo ifconfig enp3s0 195.85.72.3/25 up` | `ping 195.85.72.3` |
| R-EA-P2      | Enrique          | puerto 8/1 | `sudo ifconfig enp3s0 195.85.72.4/25 up` | `ping 195.85.72.4` |
| R-EB-P0-0    | Victor           | puerto 8/1 | `sudo ifconfig enp3s0 195.85.72.5/25 up` | `ping 195.85.72.5` |
| R-EB-P0-1    | Ruben            | puerto 8/1 | `sudo ifconfig enp3s0 195.85.72.6/25 up` | `ping 195.85.72.6` |
| R-EB-P1 (Al) | Ruben            | puerto 1/1 | `sudo ifconfig enp4s0 195.85.72.7/25 up` | `ping 195.85.72.7` |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.1`


# VLAN 3 Comercial - 195.85.72.128/26
| Rack         | Name    | Puerto     | Configurar la interfaz del PC              | Pings al resto        |
|--------------|---------|------------|--------------------------------------------|-----------------------|
| R-EA-PB      | Robert  | puerto 2/1 | `sudo ifconfig enp3s0 195.85.72.130/26 up` | `ping 195.85.72.130`  |
| R-EA-P1      | Adria   | puerto 8/3 | `sudo ifconfig enp3s0 195.85.72.131/26 up` | `ping 195.85.72.131`  |
| R-EA-P2      | Enrique | puerto 8/5 | `sudo ifconfig enp3s0 195.85.72.132/26 up` | `ping 195.85.72.132`  |
| R-EB-P1 (Al) | Ruben   | puerto 1/2 | `sudo ifconfig enp4s0 195.85.72.133/26 up` | `ping 195.85.72.133`  |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.129`


# VLAN 4 Administración - 195.85.72.192/26
| Rack    | Nombre  | Puerto     | Configurar la interfaz del PC              | Pings al resto        |
|---------|---------|------------|--------------------------------------------|-----------------------|
| R-EA-PB | Robert  | puerto 2/5 | `sudo ifconfig enp3s0 195.85.72.194/26 up` | `ping 195.85.72.194`  |
| R-EA-P1 | Adria   | puerto 8/6 | `sudo ifconfig enp3s0 195.85.72.195/26 up` | `ping 195.85.72.194`  |
| R-EA-P2 | Enrique | puerto 8/7 | `sudo ifconfig enp3s0 195.85.72.196/26 up` | `ping 195.85.72.196`  |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.72.193`


# VLAN 5 Calidad - 195.85.73.0/27
| Rack      | Name             | Puerto      | Configurar la interfaz del PC            | Pings al resto     |
|-----------|------------------|-------------|------------------------------------------|--------------------|
| R-EA-PB   | Robert (VLAN 14) | puerto 1/1  | `sudo ifconfig enp3s0 195.85.73.2/27 up` | `ping 195.85.73.2` |
| R-EA-P1   | Adria            | puerto 8/10 | `sudo ifconfig enp3s0 195.85.73.3/27 up` | `ping 195.85.73.3` |
| R-EA-P2   | Enrique          | puerto 8/10 | `sudo ifconfig enp3s0 195.85.73.4/27 up` | `ping 195.85.73.4` |
| R-EB-P0-0 | Victor           | puerto 8/4  | `sudo ifconfig enp3s0 195.85.73.5/27 up` | `ping 195.85.73.5` |
| R-EB-P0-1 | Ruben            | puerto 8/3  | `sudo ifconfig enp3s0 195.85.73.6/27 up` | `ping 195.85.73.6` |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.73.1/27`


# VLAN 6 Expediciones - 195.85.73.32/28
| Rack           | Name             | Puerto     | Comando                                   | Ping                |
|----------------|------------------|------------|-------------------------------------------|---------------------|
| R-EA-PB        | Robert           | puerto 2/8 | `sudo ifconfig enp3s0 195.85.73.34/28 up` | `ping 195.85.73.34` |
| R-EB-P0-0      | Victor           | puerto 8/5 | `sudo ifconfig enp3s0 195.85.73.36/28 up` | `ping 195.85.73.36` |
| R-EB-P0-1      | Ruben            | puerto 8/4 | `sudo ifconfig enp3s0 195.85.73.37/28 up` | `ping 195.85.73.37` |
| R-EB-P1 (Al)   | Ruben            | puerto 1/3 | `sudo ifconfig enp4s0 195.85.73.38/28 up` | `ping 195.85.73.38` |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.73.33`


# VLAN 7 PLC - 195.85.72.0/24
| Rack         | Name     | Puerto     | comando                                  | Pings              |
|--------------|----------|------------|------------------------------------------|--------------------|
| R-EB-P0-0    | Victor   | puerto 8/6 | `sudo ifconfig enp3s0 195.85.74.2/24 up` | `ping 195.85.74.2` |
| R-EB-P0-1    | Ruben    | puerto 8/5 | `sudo ifconfig enp3s0 195.85.74.3/24 up` | `ping 195.85.74.3` |
| R-EB-P1 (Al) | Ruben    | puerto 1/4 | `sudo ifconfig enp4s0 195.85.74.4/24 up` | `ping 195.85.74.4` |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.74.1`

# Show Link Aggregation
-> `show linkagg 2`

# VLAN 8 Seguridad  - 195.85.72.0/24
Importante, hacer las pruebas antes de hacer `port-security`

| Rack         | Name    | Puerto      | Configurar la interfaz del PC             | Pings al resto         |
|--------------|---------|-------------|-------------------------------------------|------------------------|
| R-EA-PB      | Robert  | puerto 2/10 | `sudo ifconfig enp3s0 195.85.74.5/24 up`  | `ping 195.85.74.5/24`  |
| R-EA-P1      | Adria   | puerto 8/12 | `sudo ifconfig enp3s0 195.85.74.6/24 up`  | `ping 195.85.74.6/24`  |
| R-EA-P2      | Enrique | puerto 8/13 | `sudo ifconfig enp3s0 195.85.74.7/24 up`  | `ping 195.85.74.7/24`  |
| R-EB-P0-0    | Victor  | puerto 8/13 | `sudo ifconfig enp3s0 195.85.74.8/24 up`  | `ping 195.85.74.8/24`  |
| R-EB-P0-1    | Ruben   | puerto 8/13 | `sudo ifconfig enp3s0 195.85.74.9/24 up`  | `ping 195.85.74.9/24`  |
| R-EB-P1 (Al) | Ruben   | puerto 1/5  | `sudo ifconfig enp4s0 195.85.74.10/24 up` | `ping 195.85.74.10/24` |

Todos (nivel 3) `sudo route add -net 0.0.0.0 netmask 0.0.0.0 gw 195.85.74.1`

# VLAN 9 Climatizacion  - 10.82.40.128/26
| Rack         | Name     | Puerto     | Configurar la interfaz del PC          | Pings               |
|--------------|----------|------------|----------------------------------------|---------------------|
| R-EB-P0-0    | Victor   | puerto 8/1 | `sudo ifconfig enp3s0 195.85.74.__/24` | `ping 195.85.74.__` |

| Rack         | Name    | Puerto      | Configurar la interfaz del PC             | Pings al resto         |
|--------------|---------|-------------|-------------------------------------------|------------------------|
| R-EA-PB      | Robert  | puerto 2/13 | `sudo ifconfig enp3s0 195.85.74.11/24 up` | `ping 195.85.74.11/24` |
| R-EA-P1      | Adria   | puerto 8/15 | `sudo ifconfig enp3s0 195.85.74.12/24 up` | `ping 195.85.74.12/24` |
| R-EA-P2      | Enrique | puerto 8/16 | `sudo ifconfig enp3s0 195.85.74.13/24 up` | `ping 195.85.74.13/24` |
| R-EB-P1 (Al) | Ruben   | puerto 1/7  | `sudo ifconfig enp4s0 195.85.74.14/24 up` | `ping 195.85.74.14/24` |


# VLAN 10 Puntos-de-acceso  - 195.85.72.0/24


# VLAN 14 Sala Multimedia
TODO: Probar las VLANs 3, 4 y 6
º
# VLAN 15 Controladora  - 195.85.72.0/24


# TESTS de asilamiento de VLANs






# TODO
Hacer ping a la interfaz de los switches desde tu switch
