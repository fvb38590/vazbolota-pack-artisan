# PACK ARTISAN - Vazbolota Consulting

Automatisation complète pour artisans du bâtiment : CRM, planning, relances, emails.

## Workflows n8n (5 workflows)

| # | Workflow | Déclencheur | Description |
|---|---------|-------------|-------------|
| 1 | Nouveau Contact - Analyse IA | Webhook | Score le lead via Claude AI, enregistre dans Notion si qualifié |
| 2 | Demande de Devis | Webhook | Validation RGPD, déduplications, création lead Notion + email confirmation |
| 3 | Planning Intervention | Webhook | Vérifie dispo Calendar, crée événement + fiche Notion + email confirmation |
| 4 | Rappel Intervention | CRON 8h | Rappel J-1 automatique par email des interventions du lendemain |
| 5 | Relance Devis | CRON 9h | Relance auto des devis non signés entre 7 et 30 jours |

## Installation

1. Importer chaque fichier JSON du dossier `n8n/` dans votre instance n8n
2. Configurer les credentials : Gmail, Google Calendar, Notion, Anthropic
3. Activer les workflows

## Intégrations requises

- **Anthropic Claude** (API key) - Scoring IA des leads
- **Google Calendar** (OAuth2) - Vérification dispo + création événements
- **Gmail** (OAuth2) - Emails de confirmation, rappels, relances
- **Notion** (OAuth2) - CRM, base leads, base interventions

## Structure

```
n8n/                         # Workflows n8n importables
  01-nouveau-contact-analyse-ia.json
  02-demande-devis.json
  03-planning-intervention.json
  04-rappel-intervention.json
  05-relance-devis.json
docs/                        # Documentation
  guide-installation.md
```

## Bases Notion requises

1. **Leads Artisans** - Champs : Nom, Prenom, Email, Telephone, Type Client, Source, Adresse, Notes, Statut
2. **Devis / CRM** - Champs : Nom, Email, Telephone, Description demande, Date creation, Statut
3. **Interventions** - Champs : Nom, Adresse intervention, Date intervention, Statut, Note, Artisan

---

Vazbolota Consulting - Pack Artisan v1.0
