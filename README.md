import re

def validar_ip(ip):
    # Expressão regular para IPv4
    padrao = re.compile(r'^(\d{1,3}\.){3}\d{1,3}$')
    if not padrao.match(ip):
        return False
    
    partes = ip.split('.')
    for parte in partes:
        if not 0 <= int(parte) <= 255:
            return False
    return True

# Exemplos de uso
ips = ["192.168.0.1", "10.0.0.256", "123.45.67.89", "999.1.1.1", "abc.def.ghi.jkl"]

for ip in ips:
    if validar_ip(ip):
        print(f"{ip} é um IP válido.")
    else:
        print(f"{ip} NÃO é um IP válido.")
