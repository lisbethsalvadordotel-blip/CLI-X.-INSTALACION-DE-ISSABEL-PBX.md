****************** PRACTICA X: ISSABEL ********************************************

============================================
1) CREAR LA MÁQUINA EN DIGITAL OCEAN
============================================

# Sistema operativo:
Rocky Linux 8

# Conectarse por SSH:

ssh root@IP_DE_LA_VM

------------------------------------------------------------

============================================
2) INSTALAR ISSABEL
============================================

# Actualizar sistema

yum update -y

# Instalar wget

yum install wget -y

# Descargar instalador

wget http://repo.issabel.org/issabel5-netinstall.sh

# Dar permisos

chmod 700 issabel5-netinstall.sh

# Ejecutar instalación

./issabel5-netinstall.sh

------------------------------------------------------------

# CONFIGURACIÓN DURANTE INSTALACIÓN

# Idioma:
English

# Seleccionar:
16

# En "Choose additional packages":

[*] Issabel Network Licensed modules

# (Quitar las demás opciones)

------------------------------------------------------------

# Contraseña solicitada:

XXXXXX

------------------------------------------------------------

# Seleccionar driver SIP:

(*) chan_pjsip   ✔ (IMPORTANTE)

------------------------------------------------------------

# Luego seleccionar:

Naaah, get a real job

------------------------------------------------------------

# NOTA IMPORTANTE

# Si se queda en "Rebooting Server":
# Ir al navegador y probar la IP directamente

------------------------------------------------------------

============================================
3) ACCESO WEB
============================================

# En navegador:

https://IP_DE_LA_VM

# Credenciales:

Usuario: admin  
Contraseña: XXXXX 

------------------------------------------------------------

# Si pide registro:
# Cerrar con la X

------------------------------------------------------------

============================================
4) CREAR EXTENSIONES
============================================

# Ruta:

PBX → Applications → Extensions

------------------------------------------------------------

# EXTENSIÓN PROFESOR

User Extension: 2220  
Display Name: Profesor Adrian  
Secret: Teletubies123$  

# Click:
Submit

------------------------------------------------------------

# IMPORTANTE 

# SIEMPRE hacer esto:

Apply Configuration

# (Si no haces esto → NO FUNCIONA)

------------------------------------------------------------

============================================
5) DESACTIVAR FAIL2BAN (IMPORTANTE)
============================================

systemctl stop fail2ban
systemctl disable fail2ban

------------------------------------------------------------

============================================
6) CONFIGURAR SOFTPHONE (ZOIPER / MICROSIP)
============================================

# (MicroSIP ya instalado según el profe)

# O usar Zoiper en el celular

------------------------------------------------------------

# CONFIGURACIÓN SIP

Account name: cualquiera  
Domain: IP_DE_LA_VM:5060 o 5066  
Username: 2220  
Password: Teletubies123$  

------------------------------------------------------------

============================================
7) PRUEBA
============================================

# Realizar llamada entre extensiones

# RESULTADO ESPERADO:

# - Registro correcto en softphone
# - Se pueden hacer llamadas
# - Audio funcional

------------------------------------------------------------

============================================
COMANDOS CLAVE
============================================

ssh root@IP
yum update -y
wget issabel
chmod +x
./issabel5-netinstall.sh
systemctl stop fail2ban

------------------------------------------------------------

============================================
ERRORES COMUNES
============================================

# No abre la web:
usar http o https
verificar IP

# No funcionan llamadas:
NO diste Apply Configuration 

# Softphone no conecta:
verificar puerto (5060 o 5066)

# Bloqueos:
fail2ban activo 

# Ver puertos:
ss -tuln | grep 506

------------------------------------------------------------

============================================
RESULTADO FINAL
============================================

# - Issabel instalado
# - Acceso web funcional
# - Extensión creada
# - Softphone conectado
# - Llamadas funcionando
