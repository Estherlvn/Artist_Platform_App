# # Récapitulatif des entités et de leurs relations basé sur le modèle conceptuel de données (MCD)

## Entités et Relations

### Utilisateur

- **Attributs** : `id_utilisateur`, `name`, `email`, `password`, `role`
- **Relations** :
  - Un utilisateur peut être un artiste, un auditeur ou un admin (relation d'héritage).

### Artist (Extension de Utilisateur)

- **Attributs** : `id_artist`, `bio`, `profilePicture`, `location`, `socialLink`
- **Relations** :
  - Un artiste peut uploader plusieurs morceaux (`Track`).
  - Un artiste peut programmer plusieurs événements (`Event`).

### Auditeur (Extension de Utilisateur)

- **Attributs** : `id_auditeur`
- **Relations** :
  - Un auditeur peut suivre plusieurs artistes.
  - Un auditeur peut créer plusieurs playlists (`Playlist`).
  - Un auditeur peut participer à plusieurs événements (`Event`).

### Admin (Extension de Utilisateur)

- **Attributs** : `id_admin`
- **Relations** :
  - Un admin peut gérer les comptes des utilisateurs, modérer le contenu, et accéder aux statistiques de la plateforme.

### Track

- **Attributs** : `id_track`, `trackName`, `audioFile`, `duration`, `uploadDate`
- **Relations** :
  - Un morceau appartient à un artiste (`Artist`).
  - Un morceau peut être ajouté à plusieurs playlists (`Playlist`).
  - Un morceau peut appartenir à plusieurs genres (`Genre`).

### Genre

- **Attributs** : `id_genre`, `genreName`
- **Relations** :
  - Un genre peut contenir plusieurs morceaux (`Track`).

### Playlist

- **Attributs** : `id_playlist`, `playlistName`
- **Relations** :
  - Une playlist appartient à un auditeur (`Auditeur`).
  - Une playlist contient plusieurs morceaux (`Track`).

### Event

- **Attributs** : `id_event`, `eventTitle`, `eventDate`, `eventLocation`, `description`
- **Relations** :
  - Un événement est associé à un artiste (`Artist`).
  - Un événement peut avoir plusieurs participants (`Auditeur`).

## Résumé des Relations

- **Utilisateur** est la classe de base avec des rôles spécifiques (artiste, auditeur, admin).
- **Artist** upload des morceaux (`Track`) et programme des événements (`Event`).
- **Auditeur** suit des artistes, crée des playlists (`Playlist`), et participe à des événements (`Event`).
- **Admin** gère les utilisateurs et le contenu de la plateforme.
- **Track** est lié à un artiste et peut être inclus dans plusieurs playlists et genres.
- **Genre** regroupe plusieurs morceaux.
- **Playlist** est créée par un auditeur et contient plusieurs morceaux.
- **Event** est programmé par un artiste et peut avoir plusieurs participants.
  
(MCD_Artist_Platform.png)
