---
sidebar_position: 4
title: Référence de modèle de serveur
---

## DND-like

```json
{
  "charName": false,
  "statistics": {
    "Force": {
      "min": 1
    },
    "Dextérité": {
      "min": 1
    },
    "Constitution": {
      "min": 1
    },
    "Intelligence": {
      "min": 1
    },
    "Sagesse": {
      "min": 1
    },
    "Charisme": {
      "min": 1
    }
  },
  "diceType": "1d20+{{ceil(($-10)/2)}}>20",
  "critical": {
    "failure": 1,
    "success": 20
  },
  "total": 27
}
```

## Simple système

```json
{
  "charName": true,
  "statistics": {
    "Force": {
      "min": 3
    },
    "Endurance": {
      "min": 3
    },
    "Agilité": {
      "min": 3
    },
    "Constitution": {
      "min": 3
    },
    "Éducation": {
      "min": 3
    },
    "Intelligence": {
      "min": 3
    },
    "Charisme": {
      "min": 3
    },
    "Pouvoir": {
      "min": 3
    },
    "PV": {
      "combinaison": "endurance*2+force"
    }
  },
  "diceType": "1d20+$>20",
  "critical": {
    "failure": 1,
    "success": 20
  },
  "total": 88
}
```