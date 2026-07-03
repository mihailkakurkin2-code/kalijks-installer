#!/bin/bash

clear                                                                                             B='\033[1;34m'
G='\033[1;32m'
W='\033[0m'

echo -e "${G}"
cat << "EOF"
    ╔═══════════════════════════════════════════╗
    ║  ██╗  ██╗ █████╗ ██╗     ██╗███████╗    ║
    ║  ██║ ██╔╝██╔══██╗██║     ██║██╔════╝    ║
    ║  █████╔╝ ███████║██║     ██║███████╗    ║
    ║  ██╔═██╗ ██╔══██║██║     ██║╚════██║    ║
    ║  ██║  ██╗██║  ██║███████╗██║███████║    ║
    ║  ╚═╝  ╚═╝╚═╝  ╚═╝╚══════╝╚═╝╚══════╝    ║
    ╚═══════════════════════════════════════════╝

EOF
echo -e "${W}"

echo -e "  OS: ${G}KALIS v1.0${W}"
echo -e "  User: ${B}$(whoami)${W}"
echo "  Host: $(hostname)"
echo "  Kernel: $(uname -r)"
echo "  Shell: $(basename $SHELL)"
echo "  Uptime: $(uptime -p | sed 's/up //')"
echo "  Memory: $(free -h | grep Mem | awk '{print $3 "/" $2}')"
echo "  Disk: $(df -h / | tail -1 | awk '{print $3 "/" $2}')"
echo ""
echo ""
echo -ne "\033[1;34m$(realpath "$0")\033[0m\033[1;37m  >\033[0m "
read c