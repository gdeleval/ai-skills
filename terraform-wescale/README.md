# Terraform WeScale Skills

Collection de skills Terraform pour Claude Code, développés par WeScale.

## Skills disponibles

### terraform-style-guide

Génère du code Terraform HCL en suivant les conventions de style officielles de HashiCorp.

**Utilisation**: Lors de l'écriture, la révision ou la génération de configurations Terraform.

### terraform-test

Guide complet pour écrire et exécuter des tests Terraform avec le framework natif.

**Utilisation**: Création de fichiers de test (.tftest.hcl), scénarios de test avec blocs run, validation du comportement de l'infrastructure, mocking de providers.

## Installation

### Installation de tous les skills

```bash
npx skills add https://gitlab.prod.aws.wescale.fr/wescalefr/ia/ia-platform-playbook/-/raw/feat/terraform-agent/skills/terraform-wescale
```

### Installation d'un skill spécifique

```bash
# terraform-style-guide
npx skills add https://gitlab.prod.aws.wescale.fr/wescalefr/ia/ia-platform-playbook/-/raw/feat/terraform-agent/skills/terraform-wescale --skill terraform-style-guide

# terraform-test
npx skills add https://gitlab.prod.aws.wescale.fr/wescalefr/ia/ia-platform-playbook/-/raw/feat/terraform-agent/skills/terraform-wescale --skill terraform-test
```

## Structure des fichiers

```
terraform-wescale/
├── .well-known/
│   └── skills/
│       └── index.json          # Index des skills disponibles
├── terraform-style-guide/
│   ├── skill.json              # Configuration du skill
│   └── SKILL.md                # Instructions détaillées
├── terraform-test/
│   ├── skill.json              # Configuration du skill
│   └── SKILL.md                # Instructions détaillées
└── README.md                   # Ce fichier
```

## Développement

### Ajouter un nouveau skill

1. Créer un nouveau répertoire dans `terraform-wescale/`
2. Ajouter un fichier `skill.json` avec la configuration:

```json
{
  "name": "mon-skill",
  "description": "Description courte du skill",
  "instructions": "SKILL.md"
}
```

3. Créer un fichier `SKILL.md` avec les instructions détaillées
4. Mettre à jour `.well-known/skills/index.json` pour référencer le nouveau skill

### Format du fichier index.json

```json
{
  "skills": [
    {
      "name": "nom-du-skill",
      "description": "Description du skill",
      "url": "https://gitlab.prod.aws.wescale.fr/wescalefr/ia/ia-platform-playbook/-/raw/feat/terraform-agent/skills/terraform-wescale/nom-du-skill"
    }
  ]
}
```

## Utilisation dans Claude Code

Après installation, les skills sont disponibles via la commande `/nom-du-skill` dans Claude Code.

Exemple:
```
/terraform-style-guide
```

## Support

Pour toute question ou problème, créer une issue sur le dépôt GitLab.
