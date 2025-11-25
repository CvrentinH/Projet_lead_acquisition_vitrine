# LeadScanner – Automated SEO & Lead Acquisition Toolkit

LeadScanner est un outil d’analyse SEO et de prospection automatisée conçu pour identifier rapidement des opportunités commerciales à partir de n’importe quelle URL.  
Il combine un backend Python/FastAPI, une base SQLite, un frontend React et plusieurs scripts d’audit SEO avancé.

## 🎯 Objectif du projet

L'objectif de LeadScanner est de :
- analyser automatiquement un site web pour détecter ses faiblesses SEO
- identifier des opportunités et menaces (lead acquisition)
- conserver les audits en base pour créer un historique
- générer des rapports exploitables
- préparer un outil complet pour freelances / growth hackers / data analysts

## 🚀 Fonctionnalités principales

- Analyse SEO complète d’une URL :
- Récupération du titre, description, H1
- Vérification du fichier robots.txt
- Vérification du sitemap.xml
- Présence du HTTPS
- Temps de réponse du site
- Favicon détectée ou non
- Structure de l’URL
- Lang, charset, viewport
- Balises sociales : og:title, og:description, twitter:card
- Balise canonical
- Détection du nombre de backlinks (via API ou méthode gratuite)
- Scoring SEO global avec pondération

- Génération d’un résumé des points critiques (critical_issues)

- Stockage automatique dans la base SQLite :
- Table Company (site analysé)
- Table SEOAudit (résultats complets)

- API REST via FastAPI
- POST /analyze-url → lance une analyse et stocke en base
- GET /audit/{company_id} → retourne les résultats stockés

- Interface front-end en React pour afficher :
- la liste des audits
- le détail complet des analyses
- les scores et les erreurs SEO

## 🏗️ Architecture technique

- Backend : FastAPI (Python)
- Frontend : React + Tailwind + Framer Motion
- Base de données : SQLite + SQLAlchemy
- Scripts SEO dans backend/scripts/seo_analyzer/
- Déploiement possible via Netlify (front) et Railway/Render/Fly.io (back)

## 🧠 Comment ça fonctionne ?

1. L’utilisateur envoie une URL au backend via le frontend.
2. FastAPI appelle le module seo_analyzer.
3. Ce module :
- télécharge la page
- extrait les balises importantes
- détecte les erreurs SEO
- calcule un score
- exécute les sous-scripts (https, favicon, performance, backlinks…)
4. Les résultats sont insérés dans la base SQLite.
5. Le frontend appelle ensuite l’API pour afficher les résultats.

.## 📂 Organisation du code

- backend/
- main.py → endpoints FastAPI
- models/ → modèles SQLAlchemy
- scripts/seo_analyzer/ → modules spécialisés
- seo_analyzer.py → pipeline global

- frontend/
- pages/ → pages React
- components/ → UI
- services/ → appels API

## 🧪 Exemple de résultat d’analyse

- Score global : 72/100
- Critical issues :
- Absence de meta description
- Pas de balise canonical
- Sitemap introuvable
- Backlinks détectés : 14
- Temps de réponse : 340 ms

## 🛠️ Technologies utilisées

- Python 3
- FastAPI
- SQLAlchemy + SQLite
- Requests / BeautifulSoup
- React
- TailwindCSS
- Framer Motion
- Netlify (front)
- API externe pour les backlinks (optionnel)

## 📌 Objectifs futurs

- Génération automatique d’un PDF d’audit
- Tableau de bord complet (graphes + historique)
- Suggestions SEO automatiques via LLM
- Mode “scan de masse” pour analyser plusieurs sites en batch
- Authentification utilisateur

## 📄 Licence

Projet personnel, non destiné à un usage commercial pour l’instant.
