# Mise en ligne du site Pelican Muay Thai (OVH)

> Hébergeur : OVH (mutualisé) — dossier racine du site = **`www`** (PAS `public_html`).
> Accès aux fichiers = **FTP** (logiciel FileZilla) avec les identifiants FTP OVH.

---

## 1) Activer le SSL (À FAIRE EN PREMIER)
Notre `.htaccess` force le HTTPS : sans certificat, le site serait inaccessible.
- Espace client OVH → **Hébergements** → ton hébergement → onglet **"SSL"** (ou "Multisite").
- Activer le certificat **SSL gratuit (Let's Encrypt)**.
- Attendre qu'il soit **"Actif"** (quelques minutes à quelques heures).

## 2) Créer la propriété Google Search Console
- Aller sur **search.google.com/search-console** → se connecter avec un Gmail.
- Choisir **"Préfixe de l'URL"** → saisir `https://www.pelicanmuaythai.fr` → Continuer.
- **Télécharger le fichier de vérification `.html`** (on l'ajoutera au site à l'étape 4).
- ⚠️ Ne pas cliquer "Vérifier" maintenant → on le fera APRÈS la mise en ligne (étape 7).

## 3) Sauvegarder l'ancien WordPress (sécurité)
- **Fichiers** : via FTP (FileZilla), télécharger tout le dossier `www` sur le PC.
- **Base de données** : OVH → section **Bases de données** → **phpMyAdmin** → onglet **Exporter** → télécharger le fichier `.sql`.
- Garder ces 2 fichiers précieusement (permet de revenir en arrière si besoin).

## 4) Préparer le ZIP du nouveau site
- Sur GitHub : bouton vert **Code → Download ZIP**.
- **Dézipper** sur le PC (le contenu est dans un sous-dossier `…-master/`).
- **Supprimer** les fichiers inutiles en ligne : `.claude/`, `.gitignore`, `MISE-EN-LIGNE.md`.
- **Ajouter** le fichier de vérification Google `.html` (téléchargé à l'étape 2) à la racine.
- ✅ Déjà présents (ne pas toucher) : `index.html`, `assets/`, `.htaccess`, `sitemap.xml`, `robots.txt`.
- ⚠️ Le `.htaccess` est un fichier **caché** → activer "afficher les fichiers cachés" pour ne pas l'oublier.

## 5) Déployer sur OVH
- Via FTP (FileZilla), ouvrir le dossier **`www`** sur le serveur OVH.
- **Supprimer tout le contenu WordPress** dans `www`.
- **Uploader le contenu** du nouveau site dans `www` (les fichiers, pas le dossier `…-master`).
- Vérifier que **`index.html`** et **`.htaccess`** sont bien **directement dans `www`** (à la racine).

## 6) Vérifier que tout fonctionne
- [ ] `https://www.pelicanmuaythai.fr` s'affiche, cadenas 🔒 présent.
- [ ] Les liens du menu marchent (toutes les pages).
- [ ] Une ancienne URL WordPress redirige, ex. `…/tarif/` → page Cotisations & Formules.
- [ ] Une ancienne page download, ex. `…/download/categories-de-poids-ffkmda/` → adhesion.html.
- [ ] Affichage mobile OK.
- [ ] Page 404 (taper une URL au hasard) → page 404 personnalisée.

## 7) Valider Search Console
- Retourner sur Search Console → cliquer **"Vérifier"** (le fichier `.html` est maintenant en ligne). ✅

## 8) Soumettre le sitemap
- Search Console → **Sitemaps** → Ajouter → `https://www.pelicanmuaythai.fr/sitemap.xml`.

## 9) Demander l'indexation des 4 pages principales
Outil **"Inspection d'URL"** → entrer chaque URL → "Demander une indexation" :
- `https://www.pelicanmuaythai.fr/`
- `https://www.pelicanmuaythai.fr/adhesion.html`
- `https://www.pelicanmuaythai.fr/cotisations-formules.html`
- `https://www.pelicanmuaythai.fr/sections.html`
(Mentions légales / politique de confidentialité = inutile, elles sont en noindex.)

## 10) Donner l'accès au client
- Search Console → **Paramètres → Utilisateurs et autorisations** → ajouter son Gmail en **"Propriétaire"**.

---

## Encore à compléter dans le code (avant publication idéalement)
- [ ] Mentions légales : RNA/SIRET, nom du président, hébergeur (OVH), siège social.
- [ ] (Optionnel) En-têtes de sécurité dans le `.htaccess`.
- [ ] (Optionnel) Garder les PDF FFKMDA (catégories de poids, règlement) sur le nouveau site.

Tél. VEGAS (crédit footer) : 07 50 53 78 10
