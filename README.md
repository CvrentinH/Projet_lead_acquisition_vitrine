# LeadScanner – SEO Automated & Lead Acquisition Toolkit

![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.109-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-3.41-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-FF0000?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![React](https://img.shields.io/badge/React-18.2-61DAFB?style=for-the-badge&logo=react&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.3-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-4.12-FF9900?style=for-the-badge&logo=python&logoColor=white)

**LeadScanner** est un outil d’analyse SEO et de prospection automatisée conçu pour identifier rapidement des opportunités commerciales à partir de n’importe quelle URL.

---

## À propos

**LeadScanner** combine un backend performant en Python/FastAPI et un frontend moderne en React pour offrir une suite d'audit complète.

L'objectif du projet est de :
* **Analyser** automatiquement un site web pour détecter ses faiblesses techniques (SEO).
* **Identifier** des opportunités et menaces pour l'acquisition de leads.
* **Historiser** les audits en base de données pour suivre l'évolution.
* **Générer** des rapports exploitables pour freelances, growth hackers et data analysts.

---

## Fonctionnalités

### Analyse SEO Complète
L'outil scanne l'URL cible et vérifie plus de 15 points de contrôle :

| Catégorie | Vérifications effectuées |
| :--- | :--- |
| **Méta & Contenu** | Titre, Description, Balises H1, Langue, Charset |
| **Technique** | Robots.txt, Sitemap.xml, HTTPS, Structure URL, Canonical |
| **Performance** | Temps de réponse du serveur, Poids de la page |
| **Social & Mobile** | OpenGraph (og:title, og:desc), Twitter Cards, Viewport |
| **Off-Page** | Détection Favicon, Backlinks (via API ou méthode gratuite) |

### Scoring & Reporting
* **Scoring Global :** Calcul d'une note de santé SEO avec pondération.
* **Points Critiques :** Génération automatique d'un résumé des erreurs bloquantes.
* **Historique :** Sauvegarde automatique dans SQLite (Tables `Company` et `SEOAudit`).

---

## Architecture Technique

Le projet repose sur une architecture découplée (Headless) :

* **Backend :** Python 3.11+, FastAPI, SQLAlchemy.
* **Frontend :** React 18, TailwindCSS, Framer Motion.
* **Base de données :** SQLite (léger et portable).
* **Moteur d'analyse :** BeautifulSoup4 & Requests (scripts situés dans `backend/scripts/seo_analyzer/`).

**Flux de données :**
1.  L’utilisateur envoie une URL depuis le Frontend.
2.  FastAPI déclenche le module `seo_analyzer`.
3.  Le script télécharge la page, extrait les balises, détecte les erreurs et calcule le score.
4.  Les résultats sont stockés en base de données.
5.  Le Frontend récupère le JSON complet pour l'affichage.

---

## Utilisation

    Assurez-vous que le backend tourne sur http://localhost:8000 et le frontend sur http://localhost:3000.

    Ouvrez votre navigateur sur le port 3000.

    Entrez une URL (ex: https://www.google.com) et lancez l'analyse.

    Consultez le score, les erreurs critiques et les détails techniques.

## Endpoints API Principaux

    POST /analyze-url : Lance une analyse et stocke le résultat.

    GET /audit/{company_id} : Récupère les détails d'un audit spécifique.

---

## Images
