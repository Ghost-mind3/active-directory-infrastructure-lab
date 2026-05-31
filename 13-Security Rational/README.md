# 13 - Justification des mesures de sécurité

## 📌 Vue d’ensemble

Cette section explique les raisons ayant motivé les différentes configurations de sécurité mises en œuvre dans ce laboratoire Active Directory.

L'objectif n'est pas uniquement de comprendre **comment ces mécanismes fonctionnent**, mais surtout **pourquoi ils sont importants** et quels risques ils permettent de réduire ou d'éliminer.

Une infrastructure sécurisée repose sur des choix réfléchis et adaptés aux menaces auxquelles elle peut être exposée.

---

# 🖥️ Stratégie de sécurité des postes de travail (GPO)

## Configuration mise en œuvre

- Désactivation du compte **Guest (Invité)**
- Désactivation des mécanismes d'authentification non sécurisés
- Gestion des administrateurs locaux via **Restricted Groups**

## Pourquoi ?

Ces mesures permettent de réduire la surface d'attaque des postes de travail du domaine tout en garantissant un contrôle centralisé des accès administratifs.

Elles contribuent également à appliquer des standards de sécurité homogènes sur l'ensemble des machines.

## Risques en l'absence de cette configuration

- Accès non autorisés via des comptes par défaut
- Utilisation de mécanismes d'authentification faibles
- Élévation de privilèges sur les postes utilisateurs
- Difficultés à contrôler les droits administratifs locaux

---

# 🔐 Gestion des accès privilégiés (Privileged Access Management)

## Configuration mise en œuvre

Séparation des rôles administratifs :

- `it.admin` → Administration du domaine
- `it.support` → Administration locale des postes de travail

Utilisation des groupes de sécurité :

- `GG_Domain_Admins`
- `GG_Workstation_Local_admins`

## Pourquoi ?

Cette approche applique le principe du **moindre privilège (Least Privilege)**.

Les utilisateurs ne disposent que des droits nécessaires à leurs missions, ce qui limite l'exposition des comptes hautement privilégiés.

Elle permet également une gestion plus simple et plus sécurisée des accès administratifs.

## Risques en l'absence de cette configuration

- Comptes disposant de privilèges excessifs
- Augmentation de l'impact d'une compromission de compte
- Difficultés d'audit et de gestion des accès
- Utilisation abusive des privilèges administratifs

---

# 🔑 Windows LAPS

## Configuration mise en œuvre

- Déploiement de Windows LAPS
- Génération automatique d'un mot de passe unique pour chaque poste
- Rotation automatique des mots de passe administrateur local

## Pourquoi ?

L'objectif est d'empêcher la réutilisation du même mot de passe administrateur local sur plusieurs machines.

Cette pratique est l'une des principales causes de propagation rapide lors d'une compromission interne.

## Risques en l'absence de cette configuration

- Déplacement latéral (*Lateral Movement*) entre les postes
- Réutilisation d'identifiants compromis
- Compromission progressive de l'ensemble du domaine à partir d'une seule machine

---

# ⚙️ Stratégies de groupe (Group Policy Objects)

## Configuration mise en œuvre

Création et déploiement de plusieurs GPO :

- GPO-Workstation-Baseline
- GPO-Audit-Policy
- GPO-Admin-Restrictions
- GPO-LAPS

## Pourquoi ?

Les stratégies de groupe permettent une administration centralisée et garantissent l'application uniforme des paramètres de sécurité sur l'ensemble du domaine.

Elles réduisent considérablement les erreurs de configuration manuelle.

## Risques en l'absence de cette configuration

- Configurations incohérentes entre les machines
- Multiplication des écarts de sécurité
- Administration plus complexe
- Difficultés de maintenance à long terme

---

# 📋 Politique d'audit

## Configuration mise en œuvre

Activation des stratégies d'audit avancées :

- Événements d'ouverture de session
- Gestion des comptes utilisateurs
- Utilisation des privilèges
- Modifications Active Directory

## Pourquoi ?

L'audit fournit une visibilité essentielle sur les activités du domaine.

Il permet d'identifier rapidement les comportements suspects et facilite les investigations en cas d'incident de sécurité.

## Risques en l'absence de cette configuration

- Absence de traces lors d'une compromission
- Difficultés à identifier l'origine d'un incident
- Faible capacité de détection des attaques
- Réponse aux incidents fortement limitée

---

# 🏢 Structure des unités d'organisation (OU)

## Configuration mise en œuvre

Organisation du domaine à l'aide d'unités d'organisation dédiées :

- Employees
- Endpoints
- Groups

## Pourquoi ?

Cette structure permet :

- Une organisation logique des ressources
- Une application ciblée des GPO
- Une administration simplifiée
- Une meilleure évolutivité de l'environnement

## Risques en l'absence de cette configuration

- Difficulté à cibler les stratégies de groupe
- Complexité administrative accrue
- Multiplication des erreurs de configuration
- Manque de visibilité sur les ressources du domaine

---

# 🧠 Point essentiel à retenir

La sécurité ne consiste pas uniquement à appliquer des configurations techniques.

Elle repose avant tout sur la compréhension des objectifs poursuivis par chaque mesure de protection.

Comprendre le **pourquoi** derrière chaque configuration permet :

- De concevoir des infrastructures plus robustes
- D'améliorer la posture de sécurité globale
- De faciliter le diagnostic et la résolution de problèmes
- D'adapter efficacement les contrôles de sécurité aux besoins réels de l'organisation

---

# 🎯 Conclusion

Ce laboratoire démontre qu'un environnement Active Directory relativement simple peut être considérablement renforcé grâce à l'application de principes de sécurité fondamentaux.

Les mécanismes mis en œuvre — gestion des privilèges, stratégies de groupe, audit avancé, segmentation logique et Windows LAPS — constituent des mesures efficaces pour réduire les risques les plus courants rencontrés dans les infrastructures Active Directory.

Au-delà de la mise en œuvre technique, comprendre les raisons qui motivent chaque configuration est une compétence essentielle pour les administrateurs systèmes et les professionnels de la cybersécurité.

Cette approche permet de construire des environnements plus résilients, plus faciles à administrer et mieux préparés face aux menaces actuelles.
