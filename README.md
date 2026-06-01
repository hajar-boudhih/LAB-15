# LAB-15

Lab_15_MobileSecurity
LAB‑15 – Analyse Dynamique Android – Inspection TLS/HTTPS & Gestion du SSL Pinning
Étape 1 – Installer Frida (PC) et démarrer frida‑server (Android)



<img width="1000" height="889" alt="image" src="https://github.com/user-attachments/assets/a0680416-761a-4e07-9dca-c78667303486" />


Étape 2 – Mettre en place le proxy et le certificat CA

2.1 Lancer le proxy sur le PC
Burp : Proxy → Intercept ON/OFF (port ex 127.0.0.1:8080)
mitmproxy : mitmproxy -p 8080
2.2 Installer la CA proxy sur l’appareil
Ouvrez http://burp ou http://mitm.it depuis le téléphone, téléchargez le certificat et installez‑le comme « certificat CA utilisateur ».

Étape 3 – Lancer l’application cible sous Frida
Identifiez le package 


Étape 4 – Script « universel » Java pour bypass SSL pinning

<img width="1026" height="814" alt="image" src="https://github.com/user-attachments/assets/1e864701-a02d-499c-b20a-c91e03d9181f" />



Étape 5 – Variantes et cibles spécifiques


frida -U -f <package_name> -l sslpin_bypass_universal.js -l sslpin_bypass_native.js --no-pause
Étape 7 – Validation et livrables
Vérifiez dans le proxy que les requêtes HTTPS de l’app sont visibles en clair.
Capturez les logs Frida contenant les messages [+] SSL bypass:.
Fournissez :
Capture de frida --version & frida-ps -Uai
Scripts utilisés (sslpin_bypass_universal.js, sslpin_bypass_native.js)
Capture du proxy montrant une requête HTTPS
Journal Frida avec au moins une ligne SSL bypass.
