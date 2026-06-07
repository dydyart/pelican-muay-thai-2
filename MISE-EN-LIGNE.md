# Mise en ligne du site Pelican Muay Thai (OVH)

## Avant de commencer
- [ ] **Activer le SSL** sur OVH (Espace client → Hébergement → onglet "SSL") → attendre qu'il soit "actif" (cadenas/https).
- [ ] **Sauvegarder l'ancien WordPress** (au cas où) :
  - Télécharger tout le dossier `/www` via FTP sur le PC.
  - Exporter la base de données (phpMyAdmin → Exporter).

## Déployer le nouveau site
- [ ] Sur GitHub : bouton vert **Code → Download ZIP**.
- [ ] **Dézipper** sur le PC. ⚠️ Prendre les fichiers DEDANS le dossier
      `pelican-muay-thai-2-maquette-master/` (index.html, assets/, .htaccess…),
      PAS le dossier lui-même.
- [ ] Via FTP OVH : **vider le `/www`** (supprimer les fichiers WordPress).
- [ ] **Uploader les nouveaux fichiers** dans `/www` (faire les 2 étapes à la suite).
- [ ] Vérifier que `.htaccess` est bien présent dans `/www` (fichier caché → activer
      "afficher les fichiers cachés" dans le client FTP).

## Vérifier que tout marche
- [ ] Ouvrir `https://www.pelicanmuaythai.fr` → le nouveau site s'affiche, cadenas présent.
- [ ] Tester une ancienne URL, ex. `https://www.pelicanmuaythai.fr/tarif/`
      → doit rediriger vers la page Cotisations & Formules.
- [ ] Cliquer dans le menu : toutes les pages s'ouvrent.

## SEO (après la mise en ligne)
- [ ] Google Search Console → ajouter le site (validation via domaine).
- [ ] Soumettre `https://www.pelicanmuaythai.fr/sitemap.xml`.
- [ ] Demander l'indexation des 4 pages principales.

## Encore à compléter dans le code (avant publication idéalement)
- [ ] Mentions légales : RNA/SIRET, nom du président, hébergeur (OVH), siège social.
- [ ] (Optionnel) En-têtes de sécurité dans le `.htaccess`.

---
Tél. VEGAS (crédit footer) : 07 50 53 78 10
