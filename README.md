📡 Télécommande Freebox Devialet pour Home Assistant

Ce projet permet d'intégrer une télécommande virtuelle Freebox Devialet dans le tableau de bord Home Assistant, en utilisant une carte Picture Elements.

🚀 Installation
Ajouter l’image de la télécommande

Placez l'image 512x512.jpg dans le dossier config/www/ de Home Assistant.
Assurez-vous qu’elle soit accessible via /local/freebox_remote.png (ou changez le chemin dans le YAML).
Créer une nouvelle vue

Ouvrez Home Assistant → Tableau de bord
Cliquez sur Modifier le tableau de bord
Ajoutez une nouvelle vue nommée "Télécommande Freebox"
Ajouter une carte "Picture Elements"

Passez en mode Éditeur YAML et copiez ce code :
```yaml
type: picture-elements
image: /local/freebox_remote.png
elements:
  - type: icon
    icon: mdi:power
    title: Power
    tap_action:
      action: call-service
      service: freebox_player.remote
      service_data:
        code: power
    style:
      top: 10%
      left: 77%

  - type: icon
    icon: mdi:volume-mute
    title: Mute
    tap_action:
      action: call-service
      service: freebox_player.remote
      service_data:
        code: mute
    style:
      top: 66%
      left: 52.5%

  - type: icon
    icon: mdi:home
    title: Home
    tap_action:
      action: call-service
      service: freebox_player.remote
      service_data:
        code: home
    style:
      top: 59%
      left: 54%
```


### Ajoutez les autres boutons ici...
Sauvegarder et vérifier
Rechargez votre interface Home Assistant
Testez les boutons

📌 Fonctionnalités

✅ Contrôle total de la Freebox Devialet
✅ Boutons interactifs sur l’image de la télécommande
✅ Intégration native avec Home Assistant

🔧 Personnalisation
Vous pouvez changer les icônes et positions en ajustant les valeurs top et left dans le YAML.
Ajoutez d'autres boutons selon vos besoins.
🛠️ Dépendances
Home Assistant avec l'intégration freebox_player.remote
📷 Aperçu
Une fois installé, votre télécommande ressemblera à ceci dans Home Assistant :


🌟 Contribuer
Vous pouvez contribuer en proposant des améliorations ou en partageant vos retours !

📩 Contact : @XAV59213

📜 Licence
Ce projet est sous licence MIT. Vous êtes libre de l'utiliser et de le modifier.

