# Mufal pour Codex — manuel d'utilisation

Mufal pour Codex donne à Codex le contexte réel de vos projets à partir des réunions synchronisées dans Mufal Cloud. L'intégration est en lecture seule : elle peut consulter et analyser vos données, mais ne peut ni modifier ni supprimer un projet ou un meeting.

## 1. Préparer Mufal

1. Connectez-vous à l'application Mufal.
2. Créez un projet avec un nom explicite, un objectif et, si utile, une mémoire persistante.
3. Associez chaque meeting au bon projet.
4. Vérifiez que les meetings sont synchronisés dans Mufal Cloud.

Les meetings ou documents uniquement stockés sur l'appareil ne sont pas accessibles à Codex.

## 2. Installer et connecter l'intégration

Installez le plugin **Mufal Meetings** depuis votre marketplace Codex, puis authentifiez votre compte Mufal lorsque Codex ouvre la page de connexion.

Depuis le terminal, la connexion peut être relancée avec :

```bash
codex mcp login mufal
```

Après l'installation ou une mise à jour du plugin, ouvrez une nouvelle tâche Codex pour charger la version la plus récente du skill et des outils.

## 3. Poser des questions dans Codex

Vous pouvez parler naturellement. Mentionnez le nom du projet, la période et le résultat attendu lorsque cela aide à limiter la recherche.

Exemples :

- « Donne-moi le statut du projet Atlas à partir de tous ses meetings, avec les dates et les actions encore ouvertes. »
- « Construis la chronologie des décisions du projet Atlas depuis le 1er juin. »
- « Quelles exigences discutées dans les meetings du projet Atlas concernent ce repository ? »
- « Retrouve qui s'est engagé sur la migration et dans quel meeting. »
- « Prépare mon prochain meeting : dernières décisions, risques, actions et questions non résolues. »
- « Compare ce que nous avons décidé dans les deux derniers meetings et signale les contradictions. »

Codex commence par identifier le projet, charge son objectif et sa mémoire, puis parcourt les meetings liés. Pour une preuve précise, il peut rechercher les transcripts et ouvrir le meeting correspondant.

## 4. Ce que Codex peut consulter

- le nom, l'objectif et la mémoire persistante du projet ;
- le nombre de meetings et la période couverte ;
- le titre, la date, la durée et le résumé de chaque meeting ;
- les points clés, actions, speakers et interactions IA disponibles ;
- des extraits de transcript ou le transcript complet lorsqu'il est nécessaire ;
- l'historique de chat sauvegardé dans un meeting.

Les réponses doivent citer les titres et dates des meetings. Mufal distingue les paroles du transcript, les résumés générés par IA et la mémoire du projet afin que vous puissiez évaluer la source de chaque conclusion.

## 5. Utilisation avec un repository

Ouvrez le repository dans Codex puis demandez, par exemple :

> Analyse le contexte du projet Mufal « Atlas », identifie les exigences décidées dans les meetings, puis compare-les à l'implémentation actuelle de ce repository. Cite les meetings et dates pour chaque écart.

Codex combine alors deux sources différentes : les fichiers réellement présents dans le repository et le contexte conversationnel récupéré depuis Mufal. Une décision de meeting n'est pas considérée comme déjà implémentée tant que le code ne le confirme pas.

## 6. Confidentialité et contrôle

- OAuth protège la connexion ; Codex ne reçoit jamais votre mot de passe Mufal.
- Les outils Mufal exposés par le plugin sont en lecture seule.
- L'accès est limité au compte Mufal connecté et aux permissions `meetings:read` et `projects:read`.
- Vous pouvez déconnecter Mufal depuis les réglages MCP de Codex.
- Les contenus locaux non synchronisés restent sur votre appareil.

## 7. Dépannage

Si Codex ne trouve pas un meeting, vérifiez qu'il est synchronisé dans Mufal Cloud et associé au bon projet. Si l'authentification a expiré, relancez `codex mcp login mufal`. Si de nouveaux outils n'apparaissent pas après une mise à jour, démarrez une nouvelle tâche Codex ou redémarrez l'application.

Pour vérifier la connexion depuis le terminal :

```bash
codex mcp list
```

Le serveur `mufal` doit apparaître activé avec OAuth.
