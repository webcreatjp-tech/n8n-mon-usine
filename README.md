# 🏭 Mon Usine — Automatisation Industrielle n8n

Plateforme complète de gestion industrielle construite sur **n8n + PostgreSQL**. Automatise l'ensemble du cycle : réception de factures PDF → extraction IA → validation → gestion de stock → dashboard → comptabilité.

## 🏗️ Architecture

```
📄 PDF Upload → 🔍 OCR / QR Code (Ollama minicpm-v) → ✅ Validation → 📦 Stock → 📊 Dashboard
```

## 📋 Workflows (17)

| # | Workflow | Description |
|---|----------|-------------|
| 00 | Import PDF | Réception et stockage des fichiers PDF |
| 01 | Extraction Factures + QR | OCR IA + lecture QR Code → structuration données |
| 02 | Production Webhooks | Déclencheurs de production en temps réel |
| 03 | Validation Commandes | Validation et approbation des commandes |
| 04 | Notifications & Alertes | Alertes Telegram pour événements critiques |
| 05 | Expédition & Suivi | Gestion des expéditions |
| 06 | Dashboard Stats | Statistiques temps réel |
| 07 | Auto Process PDFs | Traitement automatique planifié |
| 08 | Auth Login | Authentification sécurisée |
| 09 | User Management | Gestion des utilisateurs |
| 10 | Portail Home | Page d'accueil du portail web |
| 11 | Upload Facture | Interface d'upload de factures |
| 12 | Serve Files | Serveur de fichiers statiques |
| 13 | Bon de Production | Génération des bons de production |
| 14 | Comptabilité | Suivi comptable automatisé |
| 15 | Gestion Stock | Inventaire et mouvements de stock |
| 16 | Stock Dashboard | Visualisation du stock en temps réel |

## 🛠️ Stack

- **Orchestration** : n8n self-hosted
- **IA / Vision** : Ollama local (`minicpm-v` pour OCR, `qwen2.5:14b` pour extraction)
- **Base de données** : PostgreSQL local (`monusine`)
- **Notifications** : Telegram Bot
- **Auth** : HTTP Basic Auth

## 📊 Base de données

Tables PostgreSQL :
- `uploads` — fichiers reçus
- `clients` — répertoire clients
- `factures` — factures traitées
- `produits` — catalogue produits
- `utilisateurs` — comptes utilisateurs
- `mouvements_stock` — historique des stocks

## 🚀 Import dans n8n

1. Dans n8n → **Workflows** → **Import**
2. Importer les fichiers JSON du dossier `workflows/` dans l'ordre numérique
3. Configurer les credentials PostgreSQL et Telegram
4. Activer les workflows dans l'ordre
