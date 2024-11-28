En aquest fitxer es detalla els passos a seguir per a configurar Godot per a l'exportació de projectes a les ulleres Meta Quest 3.
En aquest cas concret desplegarem les aplicacions a les ulleres mitjançant un cable USB, gràcies a que el mode desenvolupador és habilitat a les ulleres.

Per a arribar a tenir un entorn de desenvolupament, haurem de tenir els següents elements:

- Android SDK amb les eines adients.
- JDK amb la versió adeqüada.
- Godot:
    - Amb l'exportació a Android configurada per a les Meta Quest 3.
    - Amb les extensions necessàries instal·lades.
 
## Instal·lació i configuració d'Android

Seguirem aquests passos per a configurar correctament l'Android SDK al nostre equip:

1. Instal·lar [Android Studio](https://developer.android.com/studio).
2. Executar Android Studio.
3. Obrir les preferències (no és necessari crear un projecte).
4. Navegar a les opcions d'Android SDK -> Eines SDK.
5. Instal·lar els [paquets requerits](https://developer.android.com/studio/intro/update#required).

És important que anotem ón és al nostre equip l'Android SDK. Ho necessitarem per a indicar-li la ruta a Godot.
Un cop fets aquests passos, ja podem tancar Android Studio.

## Instal·lació de JDK

JDK és l'SDK de java. En el moment d'escriure aquesta guia, el JDK que es necessita per a Godot és la versió 17.

1. Instal·lar JDK. Es pot fer des de la línia de comandes d'Ubuntu.

Igual que per l'SDK d'Android, és important que anotem ón es troba JDK al nostre sistema de fitxers.

## Instal·lació i configuració de Godot

1. Instal·lar [Godot](https://godotengine.org/).
2. Executar Godot.
3. Crear un projecte de tipus Mobile. Això farà el projecte més adient per a ser executat a les ulleres directament.
4. Un cop tenim el projecte obert, obrim la configuració de l'editor.
    - Canviem la configuració d'Export -> Android
       - Definim l'ubicació de l'SDK d'Android.
       - Definim l'ubicació de la clau de debug d'Android (debug keystore). Si no la tenim la creem amb la comanda:
      
              keytool -keyalg RSA -genkeypair -alias androiddebugkey -keypass android -keystore debug.keystore -storepass android -dname "CN=Android Debug,O=Android,C=US" -validity 9999 -deststoretype pkcs12
       - Definim l'ubicació del JDK.
5. Crear una exportació a Android.
    - Configurar-la amb el tipus OpenXR.
    - Activar la opció d'extensió de Meta.
    - La pantalla de creació de la exportació ens presentarà uns errors. Seguint les indicacions dels errors aplicarem els canvis demanats fins a que no n'hi hagi cap.
6. Instal·lar les extensions de Godot (mitjançant el buscador d'extensions de Godot):
    - godot xr tools
    - godot openxr vendors plugin
7. Seguir les indicacions d'[aquest tutorial](https://docs.godotengine.org/en/stable/tutorials/xr/setting_up_xr.html).
