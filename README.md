# BP — Blueprint WordPress · Webrocket

Base de départ pour tous les projets WordPress de l'agence Webrocket.

---

## Prérequis

- PHP 8.1+
- MySQL 8.0+
- [Local by Flywheel](https://localwp.com/) (recommandé pour le dev local)
- Git
- [Claude Code](https://claude.ai/code) pour les modifications assistées par IA

---

## Démarrer en local

1. Cloner le dépôt dans Local by Flywheel ou ton environnement local
2. Copier `wp-config-sample.php` → `wp-config.php` et renseigner les credentials DB
3. Importer la base de données de référence (partagée en interne)
4. Activer le thème `jimee-theme` dans l'admin WordPress

---

## Créer un nouveau projet client depuis ce Blueprint

```bash
# 1. Cloner BP
git clone https://github.com/hichemhamdani/BP-Webrocket.git nom-du-projet
cd nom-du-projet

# 2. Pointer vers le nouveau dépôt du projet client
git remote set-url origin https://github.com/hichemhamdani/NOM-NOUVEAU-REPO.git

# 3. Pousser
git push -u origin main
```

Ensuite :
- Renommer le dossier du thème (`jimee-theme` → `nom-client-theme`)
- Mettre à jour la référence dans `functions.php` et `style.css`
- Adapter `wp-config.php` pour le nouvel environnement

---

## Structure du projet

```
wp-content/
├── themes/
│   └── jimee-theme/         ← thème principal (à renommer par projet)
├── plugins/                 ← plugins inclus dans le blueprint
└── mu-plugins/              ← plugins chargés automatiquement
```

---

## Stack

| Composant | Technologie |
|-----------|------------|
| CMS | WordPress |
| E-commerce | WooCommerce |
| SEO | Yoast SEO |
| Cache | SG CachePress |
| Sécurité | SG Security |
| Hébergement cible | SiteGround |

---

## Workflow Git

| Branche | Usage |
|---------|-------|
| `main` | État stable, prêt à être cloné |
| `dev` | Développement en cours |
| `feature/xxx` | Nouvelle fonctionnalité |

### Règle : une feature = une branche = une PR vers `dev`

---

## Travailler avec Claude Code

Claude Code lit automatiquement `CLAUDE.md` au démarrage de chaque session.
Tous les commits effectués avec l'aide de Claude portent le tag `Co-Authored-By: Claude`
dans l'historique Git — c'est la traçabilité principale.

Pour démarrer une session :
```bash
claude
```

### Important : Claude ne lit pas l'historique Git automatiquement

Claude connaît le contexte du projet via `CLAUDE.md`, mais il ne sait pas ce qui a été
modifié dans les sessions précédentes. Si tu viens de cloner le projet ou de reprendre
après une pause, commence ta session par cette commande :

```
Lis les 20 derniers commits git et résume ce qui a été fait et pourquoi.
```

Cela permet à Claude de se remettre dans le contexte du travail récent avant de continuer.

---

## Équipe

Projet maintenu par **Webrocket** · [hichemhamdani](https://github.com/hichemhamdani)
