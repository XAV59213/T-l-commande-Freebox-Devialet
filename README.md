# 📡 Télécommande Freebox Devialet pour Home Assistant  

Ce projet permet d'intégrer une **télécommande virtuelle Freebox Devialet** dans le **tableau de bord Home Assistant**, en utilisant une carte **Picture Elements** pour une interaction intuitive.  

---

## 🚀 Installation  

### 📂 Ajouter l’image de la télécommande  
1. **Téléchargez l’image** `512x512.jpg`.  
2. **Déplacez-la** dans le dossier `config/www/` de Home Assistant.  
3. **Vérifiez son accessibilité** en utilisant l'URL :  
   ```
   /local/freebox_remote.png
   ```
   (Si nécessaire, ajustez le chemin dans le code YAML).  

### 📋 Créer une nouvelle vue  
1. **Ouvrez Home Assistant** → **Tableau de bord**.  
2. **Cliquez sur "Modifier le tableau de bord"**.  
3. **Ajoutez une nouvelle vue** et nommez-la `"Télécommande Freebox"`.  

### 🎛 Ajouter une carte "Picture Elements"  
1. **Passez en mode Éditeur YAML**.  
2. **Copiez-collez** le code suivant :  

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

  # Ajoutez les autres boutons ici...
```

---

## ✅ Fonctionnalités  
✔️ **Contrôle total de la Freebox Devialet** (alimentation, volume, navigation...)  
✔️ **Boutons interactifs sur l’image de la télécommande**  
✔️ **Intégration native avec Home Assistant**  

---

## 🔧 Personnalisation  
- **Modifiez les icônes et les positions** en ajustant les valeurs `top` et `left` dans le YAML.  
- **Ajoutez d'autres boutons** pour enrichir la télécommande.  

---

## 🛠️ Dépendances  
- **Home Assistant** avec l'intégration **`freebox_player.remote`**  

---

## 📷 Aperçu  
Une fois installé, votre télécommande apparaîtra ainsi dans Home Assistant :  

![Télécommande Freebox Devialet](512x512.jpg)  

---

## 🌟 Contribuer  
Vous pouvez contribuer en proposant des **améliorations**, en signalant des **problèmes** ou en partageant vos **retours d'expérience** !  

📩 **Contact** : @XAV59213  

---

## 📜 Licence  
🔓 Ce projet est sous **licence MIT**. Vous êtes libre de l'utiliser, de le modifier et de le partager.  


