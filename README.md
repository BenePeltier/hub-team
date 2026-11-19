# Hub APOLLO Team

Site statique de **https://team.apollo-business.com** (GitHub Pages), le hub de l'équipe APOLLO : CEO, Directeurs nationaux, Directeurs régionaux et Consultants.

## L'accès
La page demande une connexion avec le compte de l'app APOLLO (mot de passe ou code reçu par e-mail).
Le contenu du hub est chiffré dans `docs/hub.bin` (AES-256-GCM) : la clé de lecture est remise par la fonction
`public.team_cle()` de la base APOLLO France, aux seuls comptes de l'équipe APOLLO France (niveaux d'accès 0 à 4, fiche active).

## L'annuaire
Les groupes du périmètre et l'équipe APOLLO sont lus en direct dans la base, avec la session de la personne connectée.

## Une mise à jour
La page est générée depuis le projet « Support Plaquette Formation APOLLO » (hub-team : template_team.html et build_team_site.py) :
le montage chiffre le contenu et met à jour son adresse dans `index.html`. Une mise à jour = un commit sur `main`.
