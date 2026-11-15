# Diagnostico-Conectividad
Codigo para solucionar el problema de conectividad hecho como una guia
Algoritmo Diagnostico_Conectividad
    // Definición de variables
    Definir opcionMenu Como Entero
    Definir resp1, resp2, resp3 Como Caracter
    Definir continuar Como Caracter
    
    continuar <- "S"
    
    Mientras Mayusculas(continuar) = "S" Hacer
        Limpiar Pantalla
        Escribir "======================================================="
        Escribir "   SISTEMA DE DIAGNOSTICO DE PROBLEMAS DE CONECTIVIDAD "
        Escribir "======================================================="
        Escribir "Seleccione el sintoma principal que presenta su equipo:"
        Escribir "1. Sin acceso a Internet (icono de red con alerta o desconectado)"
        Escribir "2. Conectado a la red Wi-Fi, pero las paginas no cargan"
        Escribir "3. Conexion muy lenta o intermitente"
        Escribir "4. Salir del programa"
        Escribir "-------------------------------------------------------"
        Escribir Sin Saltar "Ingrese una opcion (1-4): "
        Leer opcionMenu
        
        Segun opcionMenu Hacer
            1:
                Escribir ""
                Escribir "--- DIAGNOSTICO: SIN ACCESO A INTERNET ---"
                Escribir Sin Saltar "¿El cable de red esta conectado o el Wi-Fi esta encendido? (S/N): "
                Leer resp1
                
                Si Mayusculas(resp1) = "N" Entonces
                    Escribir ""
                    Escribir ">> DIAGNOSTICO: Adaptador de red desactivado o cable desconectado."
                    Escribir ">> SOLUCION: Active el interruptor Wi-Fi de su equipo o verifique que el cable Ethernet este bien conectado."
                SiNo
                    Escribir Sin Saltar "¿Otros dispositivos (celular, tablet) tienen internet en la misma red? (S/N): "
                    Leer resp2
                    
                    Si Mayusculas(resp2) = "N" Entonces
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Falla general en el router o en el proveedor de Internet (ISP)."
                        Escribir ">> SOLUCION: Reinicie el router (desconectelo 30 segundos). Si el problema persiste, contacte a su operador."
                    SiNo
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Falla de configuracion IP o controlador en este equipo."
                        Escribir ">> SOLUCION: Desactive y vuelva a activar el Wi-Fi del equipo o ejecute el solucionador de problemas de Windows."
                    FinSi
                FinSi
                
            2:
                Escribir ""
                Escribir "--- DIAGNOSTICO: CONECTADO PERO SIN NAVEGACION ---"
                Escribir Sin Saltar "¿Aparece un mensaje de error de DNS en el navegador? (S/N): "
                Leer resp1
                
                Si Mayusculas(resp1) = "S" Entonces
                    Escribir ""
                    Escribir ">> DIAGNOSTICO: Falla en la resolucion de nombres de dominio (DNS)."
                    Escribir ">> SOLUCION: Cambie los servidores DNS de su adaptador a los de Google (8.8.8.8 y 8.8.4.4) o reinicie la cache DNS."
                SiNo
                    Escribir Sin Saltar "¿El problema ocurre en todos los navegadores (Chrome, Edge, etc.)? (S/N): "
                    Leer resp2
                    
                    Si Mayusculas(resp2) = "S" Entonces
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Posible bloqueo de Firewall, Antivirus o Proxy mal configurado."
                        Escribir ">> SOLUCION: Revise la configuracion de Proxy del sistema y verifique que el antivirus no bloquee la salida a Internet."
                    SiNo
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Falla especifica del navegador web."
                        Escribir ">> SOLUCION: Borre el historial y la cache del navegador afectado o reinstalelo."
                    FinSi
                FinSi
                
            3:
                Escribir ""
                Escribir "--- DIAGNOSTICO: CONEXION LENTA O INTERMITENTE ---"
                Escribir Sin Saltar "¿Se encuentra lejos del router o hay varias paredes de por medio? (S/N): "
                Leer resp1
                
                Si Mayusculas(resp1) = "S" Entonces
                    Escribir ""
                    Escribir ">> DIAGNOSTICO: Atenuacion y baja intensidad de señal Wi-Fi."
                    Escribir ">> SOLUCION: Acerquese al punto de acceso, conectese a la banda 2.4 GHz (mayor alcance) o use un repetidor."
                SiNo
                    Escribir Sin Saltar "¿Hay muchos dispositivos conectados descargando archivos o viendo video? (S/N): "
                    Leer resp2
                    
                    Si Mayusculas(resp2) = "S" Entonces
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Saturacion del ancho de banda."
                        Escribir ">> SOLUCION: Pause descargas pesadas en segundo plano y desconecte dispositivos que no esten en uso."
                    SiNo
                        Escribir ""
                        Escribir ">> DIAGNOSTICO: Interferencia de canal Wi-Fi o saturacion del router."
                        Escribir ">> SOLUCION: Reinicie el router para liberar memoria y reasignar un canal menos congestionado."
                    FinSi
                FinSi
                
            4:
                Escribir ""
                Escribir "Saliendo del sistema de diagnostico. ¡Hasta pronto!"
                continuar <- "N"
                
            De Otro Modo:
                Escribir ""
                Escribir "ERROR: Opcion no valida. Por favor seleccione un numero del 1 al 4."
        FinSegun
        
        Si opcionMenu <> 4 Entonces
            Escribir ""
            Escribir "-------------------------------------------------------"
            Escribir Sin Saltar "¿Desea realizar otro diagnostico? (S/N): "
            Leer continuar
        FinSi
    FinMientras
FinAlgoritmo
