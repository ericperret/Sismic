# Sismic

[![License: CC BY-NC 4.0](https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc/4.0/)

Simulateur sismique interactif pour structures avec isolation LRB et amortisseurs de masse accordés (TMD).

## Fonctionnalités

### Modélisation

- **3 degrés de liberté couplés** : Structure (M1), TMD liquide (M2), TMD pendulaire (M3)
- **Isolation LRB bilinéaire** : Modèle hystérétique réaliste avec paramètres Ki, Kd, Qd, Dy
- **Intégration Newmark-β** : γ=0.5, β=0.25 (accélération moyenne)

### Séismes

Base de données de 20 séismes historiques avec paramètres réels :
- Japon : Kobe 1995, Tōhoku 2011, Kumamoto 2016
- USA : Northridge 1994, Loma Prieta 1989, Alaska 1964
- Autres : Christchurch 2011, Chi-Chi 1999, Turquie 2023...

Paramètres ajustables : magnitude, distance épicentrale, fréquence dominante, type de sol (A/B/C/D selon Eurocode 8).

### Dispositifs de protection

| Dispositif | Description |
|------------|-------------|
| **LRB** | 16 isolateurs plomb-caoutchouc (Ø400 à Ø1000mm), courbe hystérésis visualisable |
| **TMD Piscine** | Amortisseur liquide par sloshing, fréquence calculée automatiquement |
| **TMD Pendule** | Big-bag suspendu, longueur de câble ajustable (10-60 cm) |

### Outils

- **Auto-accordage** : Calcul automatique de la longueur de câble optimale
- **Export CSV** : Historique temporel des déplacements
- **Visualisation hystérésis** : Boucle force-déplacement du système LRB
- **Interface bilingue** : Français / Anglais

## Utilisation

1. Ouvrir `simulateur_sismique_TMD_v11_final.html` dans un navigateur
2. Sélectionner un séisme de référence ou paramétrer manuellement
3. Configurer les dispositifs (LRB, piscine, pendule)
4. Cliquer sur **SIMULATION**
5. Analyser les résultats (déplacements max, énergie dissipée, verdict)

## Critères de performance

| Déplacement structure | Verdict |
|-----------------------|---------|
| < 2 cm | ✅ Objectif atteint |
| 2-10 cm | ⚠️ Dommages mineurs |
| > 10 cm | ❌ Dommages importants |

## Technique

- HTML/JS pur, aucune dépendance
- Résolution système 3×3 par élimination de Gauss avec pivot
- Pas de temps : 2 ms

## Licence

CC BY-NC 4.0 — Usage non-commercial, attribution requise.
