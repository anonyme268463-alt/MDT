# MDT France RP — Firebase

Application MDT multi-institutions et multi-serveurs pour GitHub Pages.

## Installation Firebase

1. Dans Firebase Console, ouvrez **Authentication > Sign-in method** et activez **E-mail/Mot de passe**.
2. Ouvrez **Firestore Database**, créez la base en mode production et choisissez une région européenne.
3. Dans **Firestore Database > Règles**, remplacez les règles par le contenu de `firestore.rules`, puis publiez.
4. Dans **Authentication > Settings > Authorized domains**, ajoutez votre domaine GitHub Pages, par exemple `anonyme268463-alt.github.io`.
5. Déposez `index.html` à la racine de votre dépôt GitHub Pages.
6. Ouvrez le site, choisissez **Créer un serveur**, puis créez le compte propriétaire. Les registres de démonstration seront initialisés automatiquement dans votre organisation.

## Fichiers

- `index.html` : application complète autonome.
- `firestore.rules` : séparation des organisations, institutions et rôles.
- `firebase.json` : configuration facultative pour Firebase CLI/Hosting.

## Sécurité

La configuration Firebase présente dans `index.html` identifie le projet mais ne constitue pas un mot de passe. La protection réelle repose sur Firebase Authentication et `firestore.rules`. Ne publiez jamais de clé de compte de service ou de clé Admin SDK dans ce dépôt.

## Modèle de données

- `organizations/{orgId}` : client/serveur RP et offre.
- `users/{uid}` : profil, institution, rôle et organisation.
- `organizations/{orgId}/citizens`, `vehicles`, `interventions`, `reports`, `cases`, `patrols`, `medicalRecords`, `weaponPermits`, `deaths`, `civilDocuments`, `justiceCases`, `prisonTransfers`, `staff`, `emergencyCalls`, `transmissions`, `tasks`, `audit`.
