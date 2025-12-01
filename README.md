# FieldForce360
Application complète de gestion d’interventions terrain destinée aux techniciens, commerciaux itinérants et leurs managers.


## Fonctionnalités principales

| Fonctionnalité                                   | Mobile (iOS / Android)                  | Desktop (Windows / Mac)                  |
|--------------------------------------------------|-----------------------------------------|------------------------------------------|
| Authentification sécurisée (JWT + Azure AD B2C ready) | Implémentée                            | Implémentée                              |
| Géolocalisation et carte interactive            | Mapsui + OpenStreetMap, suivi en temps réel | Plein écran avec zoom et couches multiples |
| Scan QR Code et NFC                              | Camera.MAUI + Plugin.NFC                | Webcam + lecteur NFC externe             |
| Checklist dynamique avec pièces jointes          | Photos, annotations, commentaires       | Même interface, édition groupée          |
| Signature client (dessin tactile ou souris)      | SkiaSharp.Views.Maui                    | Support stylet et souris                 |
| Mode hors-ligne complet                          | SQLite local + stockage fichiers        | Identique, synchronisation en arrière-plan |
| Synchronisation intelligente                    | Automatique dès retour connexion        | Manuelle ou automatique + file d’attente |
| Planning manager avec drag & drop                | Non disponible                          | Syncfusion Scheduler (licence communautaire) |
| Génération de rapports d’intervention PDF        | QuestPDF, modèle personnalisable        | Prévisualisation et impression directe   |
| Notifications push                               | Firebase / simulation locale            | Non applicable (notifications système possibles) |
| Tableau de bord statistiques en temps réel       | Vue synthétique                         | Graphiques détaillés (LiveCharts2)       |
| Gestion multi-utilisateurs et rôles              | Technicien / Manager / Admin            | Identique                                |
| Export Excel/CSV des interventions               | Depuis l’app                            | Bouton dédié + planification             |


## Stack technique (100 % Microsoft / .NET 9)

| Couche               | Technologie                                | Version |
|----------------------|--------------------------------------------|---------|
| UI / Framework       | .NET MAUI + MAUI Community Toolkit         | 9.0     |
| Architecture         | MVVM + CommunityToolkit.Mvvm               | 8.3+    |
| Cartographie         | [Mapsui](https://github.com/Mapsui/Mapsui) (OpenStreetMap) | 5.x     |
| Scan QR/NFC          | Camera.MAUI + Plugin.NFC                   | Latest  |
| Annotations photo    | SkiaSharp + Paint.NET-like controls        | 3.x     |
| Signature            | SkiaSharp.Views.Maui                       |         |
| Base locale          | SQLite-net + SQLite-net-extensions         | 2.x     |
| Synchronisation      | Refit + Polly + BackgroundSync (custom)    |         |
| Backend démo         | ASP.NET Core Web API + Azure SQL (optionnel) | .NET 9  |
| PDF                  | QuestPDF                                   | 2024.x  |
| Planning desktop     | Syncfusion Community License               | 26.x    |
| DI / Logging         | Microsoft.Extensions.DependencyInjection + Serilog |     |


## Architecture du projet

FieldForce360/
├── src/
│   ├── FieldForce360.Maui/              ← Projet MAUI principal
│   │   ├── Platforms/                  ← Code spécifique plateforme
│   │   ├── Resources/
│   │   ├── Models/
│   │   ├── ViewModels/
│   │   ├── Views/
│   │   ├── Services/                   ← Sync, Auth, Location, NFC, etc.
│   │   └── Converters/
│   ├── FieldForce360.Api/               ← Web API démo (optionnelle)
│   └── FieldForce360.Shared/            ← DTOs & constantes partagées
├── tests/
│   └── FieldForce360.Tests/             ← xUnit + CommunityToolkit.SourceGenerators tests
└── Screenshots/                         ← Captures iOS, Android, Windows, Mac


Compte de démonstration :
Login : technicien@demo.com
Mot de passe : Demo123!

