#!/bin/bash
#Author: AlexisDuran (knoH4ck)
echo "[!] Comenzando Actualización... {by kn0H4ck}"
echo "Versión del Sistema: $(lsb_release -a 2>/dev/null | grep "Release")"
sleep 6

apt update && apt -y full-upgrade && dist-upgrade -y

apt autoremove -y

echo "[!] A terminado... "
sleep 10
