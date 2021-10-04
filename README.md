Optimus Crypter
=======
Utilise AES pour exécuter un shellcode crypté en utilisant Python et ctypes.

`CodeSection.py` 
Contient le shellcode crypté (crypté par ShellcodeEncrypter.py) et les fonctions ctypes nécessaires pour l'exécuter. Il est détecté par l'antivirus s'il n'est pas crypté par...

`EncryptCodeSection.py`
Appelle une fonction encryptFile (dans crypt.py) qui dépose le fichier "CodeSection". Ce fichier est crypté et n'est pas détecté par l'AV.

`ShellcodeEncrypter.py`
Utilisé pour crypter le shellcode. Pas vraiment nécessaire, mais utile si vous êtes paranoïaque à propos de l'analyse statique.

`stub.py`
Décrypte le "CodeSection" et exécute le fichier retourné en mémoire. 

Tout ceci peut être empaqueté dans un exécutable avec PyInstaller. Soyez avertis que ceci est indétectable au moment du scan, PAS au moment de l'exécution. Le shellcode actuel dans les scripts exécute calc.exe. N'hésitez pas à le changer pour ce que vous voulez.

NOTE : C'est juste un PoC, les fonctions cryptographiques utilisent une chaîne statique avec une valeur aléatoire qui est intégrée dans le shellcode. 
