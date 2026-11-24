# Hub APOLLO Team

Site statique de **https://team.apollo-business.com** (GitHub Pages), le hub de l'équipe APOLLO : CEO, Directeurs nationaux, Directeurs régionaux et Consultants.

## L'accès
La page demande une connexion avec le compte de l'app APOLLO (mot de passe ou code reçu par e-mail).
Le contenu du hub est chiffré dans `docs/hub.bin` (AES-256-GCM) : la clé de lecture est remise par la fonction
`public.team_cle()` de la base APOLLO France, aux seuls comptes de l'équipe APOLLO France (niveaux d'accès 0 à 4, fiche active).

## L'annuaire
Les groupes du périmètre et l'équipe APOLLO sont lus en direct dans la base, avec la session de la personne connectée.

## L'espace Recrutement
Le parcours Consultant (accord de confidentialité, dossier, contrat, accès, bienvenue) vit dans `recrutement/` (espace de la direction),
`dossier/` (lien personnel du candidat) et `bienvenue/` (activation de la boîte mail), avec la fonction Supabase `Recrutement`.
Dans le hub, la tuile « Recrutement des Consultants » est ajoutée par `index.html` (fonction `showRecrutement`, après l'appel
à `public.recrutement_hub()`), à la suite du tableau de suivi des postulations : seuls les comptes de la table `recrutement_acces` la voient.
Elle s'ouvre dans le même onglet, avec la même session.

## Une mise à jour
La page est générée depuis le projet « Support Plaquette Formation APOLLO » (hub-team : template_team.html et build_team_site.py) :
le montage chiffre le contenu et met à jour son adresse dans `index.html`. Une mise à jour = un commit sur `main`.
Avant un nouveau montage, reporter dans template_team.html la tuile Recrutement de `index.html` (24 novembre 2026), sinon elle disparaît.
