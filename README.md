# 📩 Template Email - Rapport Goodforest

Ce dépôt contient le code HTML/CSS du template d’email envoyé aux clients Goodforest. Il a été conçu pour être **responsive**, **compatible multi-clients** (Outlook, Gmail, Apple Mail…) et simple à maintenir.

---

## ✅ Points validés

### 📐 Taille du container
- La largeur est fixée à `850px` max.
- 👉 **Raison :** certains clients de messagerie comme Outlook rencontrent des problèmes d’affichage au-delà de `900px`.

### 💅 Propriétés CSS supportées
- Les propriétés modernes comme `flex`, `display: none`, `border-radius`, `gap`, etc. sont utilisées **avec précaution** et **testées** sur plusieurs clients.
- Le style du bouton utilise `inline-block` + centrage via `text-align: center` dans le parent — ✅ compatible Outlook.

### 📱 Responsive design
- Pas de `vw/vh` : ces unités sont **mal supportées** en email.
- À la place, plusieurs breakpoints sont définis (`800px`, `600px`, `500px`, etc.) pour s’adapter à la majorité des appareils.

### 📦 Bouton CTA
- Le bouton `.btn` utilise :
  - `display: inline-block`
  - `mso-padding-alt` pour Outlook
  - `line-height: 100%` pour éviter les bugs verticaux
- Il est **centré via un conteneur** avec `text-align: center;`.

---

## ⚠️ Points de vigilance

### 🧱 Variables CSS (`--color`)
- Utilisées dans le `<style>` pour clarté et réutilisabilité.
- ⚠️ Pas toujours supportées dans les clients mails. **Des fallbacks sont définis juste avant chaque `var(...)`.**
- Exemple :
  ```css
  color: #3d5a40; /* fallback */
  color: var(--green);

🔒 Iframe (Carte Foursquare)
L’iframe peut être bloquée dans certains clients (Gmail, Outlook).

➕ Un bouton cliquable (<a class="btn">) renvoie vers la carte en pleine page pour assurer l’accès.

