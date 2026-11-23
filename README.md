# Tableau de bord des taux BCE

## 1. Question métier

Le taux du marché monétaire en euro (€STR) suit-il fidèlement les décisions de taux de la BCE, et quel écart persiste entre les deux ?

## 2. Utilisateurs

- **Trésorerie** : suivre le coût réel de la liquidité au jour le jour et anticiper l'effet des décisions de la BCE.
- **Gestion actif-passif (ALM)** : alimenter les scénarios d'évolution des taux qui pèsent sur la marge de la banque.
- **Desk de taux (salle des marchés)** : disposer d'un historique fiable de l'€STR, taux de référence de nombreux produits dérivés.
## 3. Sources
Données publiques issues de l'API du portail de données de la BCE (ECB Data Portal), téléchargées au format CSV.

| Série | Clé BCE | Fréquence | Fichier |
|---|---|---|---|
| €STR (taux du marché monétaire au jour le jour) | `EST.B.EU000A2X2A25.WT` | Jours ouvrés (B) | `data/raw/bce_estr_quotidien.csv` |
| Taux de la facilité de dépôt (DFR) | `FM.D.U2.EUR.4F.KR.DFR.LEV` | Quotidienne (D) | `data/raw/bce_dfr_quotidien.csv` |
| Taux des opérations principales de refinancement (MRO) | `FM.D.U2.EUR.4F.KR.MRR_RT.LEV` | Quotidienne (D) | `data/raw/bce_mro_quotidien.csv` |

**Choix de la série MRO** : la série `MRR_RT` a été retenue car elle couvre en continu les deux modes d'adjudication de la BCE (taux minimum de soumission avant 2008, taux fixe depuis), contrairement à `MRR_FR`.

**Point d'attention** : l'€STR n'est publié que les jours ouvrés, alors que le DFR et le MRO sont quotidiens. Les séries seront alignées lors de la préparation des données.
## 4. Indicateurs

## 5. Périmètre