#!/bin/bash
#Author: AlexisDuran (knoH4ck)
#Colours
greenColour="\e[0;32m\033[1m"
endColour="\033[0m\e[0m"
redColour="\e[0;31m\033[1m"
blueColour="\e[0;34m\033[1m"
yellowColour="\e[0;33m\033[1m"
purpleColour="\e[0;35m\033[1m"
turquoiseColour="\e[0;36m\033[1m"
grayColour="\e[0;37m\033[1m"
trap ctrl_c INT 
function ctrl_c(){
    echo -e "\n${redColour}[!] Saliendo...\n${endColour}"
	tput cnorm; exit 1
}
if [ "$(id -u)" == "0" ]; then
    echo -e "${purpleColour}[!] Comenzando Actualización... {by kn0H4ck}${endCOlour}"
	echo -e "${yellowColour}Versión del Sistema: $(lsb_release -a 2>/dev/null | grep "Release")${endColour}"
	sleep 6
	apt update && apt -y full-upgrade && dist-upgrade -y; apt autoremove -y
	echo -e "${blueColour}[!] A terminado... ${endColour}"; sleep 10; exit 0
else
    echo -e "\n${redColour}[!] No eres ROOT; Saliendo...\n${endColour}"
	tput cnorm; exit 1
fi
