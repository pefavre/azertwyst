# Disposition Windows pour Clavier AZERTY Mac 🍏➡️🪟

Un layout Windows (disposition de clavier) personnalisé pour utiliser parfaitement un clavier ISO AZERTY typé "Mac" sur un système Windows. 

Créé initialement pour le **Lofree Flow 2**, ce layout fonctionne pour tout clavier mécanique ou bureautique dont les légendes correspondent à la disposition Apple (Keychron, NuPhy, Logitech MX Keys, etc.).

## ❌ Le problème
Par défaut, Windows ne propose pas de disposition "Français (Apple)". Si vous connectez un clavier AZERTY Mac sur un PC, de nombreuses touches physiques ne correspondent pas à ce qui s'affiche à l'écran :
- Les chiffres `6` et `8` n'affichent pas le `-` et le `_` en appui simple.
- L'arobase `@` n'est pas sur la touche `0`.
- Le point d'exclamation `!` et les symboles spéciaux sont décalés.

## ✅ La solution
Ce dépôt contient un installeur généré via **Microsoft Keyboard Layout Creator (MSKLC)**. Il ajoute une nouvelle disposition native dans Windows qui respecte à 100 % le marquage physique de vos touches Mac, tout en utilisant la touche `AltGr` (ou l'équivalent `Option` droit) pour les symboles comme l'arobase ou l'euro.

## ⚙️ Installation

1. Téléchargez le dossier compressé depuis la section [Releases](../../releases) et extrayez-le.
2. Ouvrez le dossier extrait.
3. **⚠️ Important (Windows 11 / Smart App Control) :** Ne double-cliquez pas sur `setup.exe`, car il risque d'être bloqué par la sécurité de Windows (éditeur non vérifié).
4. Double-cliquez directement sur le fichier **`[NomDuFichier]_amd64.msi`** (le package Windows Installer pour les systèmes 64 bits). L'installation est silencieuse et dure quelques secondes.
5. Allez dans les **Paramètres Windows** > **Heure et langue** > **Langue et région** (ou *Saisie*).
6. Dans la section Français, cliquez sur les trois petits points `...` > **Options linguistiques**.
7. Dans **Claviers**, cliquez sur **Ajouter un clavier** et sélectionnez la nouvelle disposition (ex: *Français - Mac*).
8. Pour éviter les bascules accidentelles, supprimez l'ancien clavier *Français* classique de cette liste.

## 🛠️ Inversion de la touche `< >` et `²` (Optionnel)
En raison de la façon dont Windows gère les scancodes matériels des claviers ISO, il est possible que la touche située sous Échap et celle située à côté de Maj gauche soient inversées. 

Pour corriger cela de manière transparente, utilisez [AutoHotkey v2](https://autohotkey.com/) avec ce simple script :

```autohotkey
#Requires AutoHotkey v2.0
; Inverse la touche sous Echap et la touche à côté de Maj gauche
vkE2::vkC0
vkC0::vkE2
