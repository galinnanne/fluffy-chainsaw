# Avantages de Claude Code

## Intégration profonde avec le terminal
- Fonctionne directement dans votre shell, sans changer d'environnement
- Accès natif aux fichiers, git, et commandes système

## Compréhension du codebase
- Navigation intelligente via Glob, Grep et Read
- Maintient le contexte sur de grandes bases de code (fenêtre jusqu'à 1M tokens sur Opus)

## Exécution autonome de tâches
- Édition multi-fichiers, refactoring, debugging
- Lance des tests, crée des commits git, ouvre des pull requests
- Sous-agents spécialisés (Explore, Plan, etc.) pour paralléliser le travail

## Extensibilité
- Hooks pour automatiser des comportements (pre/post tool use)
- Serveurs MCP pour connecter des outils externes (GitHub, Notion, etc.)
- Slash commands et skills personnalisables
- Settings granulaires (permissions, variables d'environnement)

## Multi-plateforme
- CLI terminal, app desktop (Mac/Windows), web (claude.ai/code)
- Extensions IDE (VS Code, JetBrains)

## Modèles Claude 4.x de pointe
- Opus 4.7, Sonnet 4.6, Haiku 4.5 selon le besoin (puissance vs vitesse/coût)

## Sécurité
- Modes de permission configurables
- Sandboxing optionnel pour les commandes bash
- Revue de code et audit de sécurité intégrés via skills
