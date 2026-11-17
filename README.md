# Kafo : l'assurance de la tontine
 
Simulateur interactif du mémoire de Master 2 Finance Digitale (Dakar Institute of Technology, 2025-2026) :
 
> Kafo Protocol : la mutualisation du risque, une réponse à l'échec d'adoption des tontines rotatives sur blockchain ? Modélisation et prototypage d'un mécanisme d'assurance dans le contexte réglementaire de l'UEMOA
 
Auteur : Hanaphiou Deen Diallo. Encadreur : David Mazola Makasi.
 
## Utilisation
 
Le simulateur tient dans un seul fichier, `index.html`. Il n'a besoin ni d'installation, ni de connexion, ni de serveur : il suffit de l'ouvrir dans un navigateur.
 
Pour le publier en ligne avec GitHub Pages : **Settings > Pages**, puis **Deploy from a branch**, branche `main`, dossier `/ (root)`.
 
## Ce qu'il contient
 
| Onglet | Rôle |
|---|---|
| Ma tontine | Saisir de vrais membres, tirer l'ordre au sort, faire tourner un cycle tour par tour et voir qui supporte la perte. La liste est enregistrée dans le navigateur, avec export et import. |
| Simulateur du fonds | Risque de manque par position, coût net et cycles à découvert selon la prime, dimensionnement du fonds par objectif de couverture, robustesse si le taux de défaut change. |
| Gestionnaire centralisé et blockchain | Risque de ne pas recevoir le pot quand un gestionnaire peut prélever (q) ou disparaître (ρ), face à la version blockchain. |
| Hypothèses et lecture | Hypothèses du modèle, définition des indicateurs, limites. |
 
## Méthode
 
La perte d'un cycle est une somme pondérée de défauts indépendants. Sa loi est calculée exactement par programmation dynamique : il n'y a ni tirage aléatoire, ni bruit de simulation. Les résultats coïncident avec les simulations de Monte Carlo du mémoire (600 000 cycles) aux écarts de simulation près.
 
Paramètres de référence : 22 membres, cotisation de 8 667 FCFA par tour (enquête de Cotonou), taux de défaut de 1,23 % par membre servi (tontines commerciales d'Inde du Sud), prime de référence de 1 097 FCFA. La valeur exacte de la prime d'équilibre est p × C × (N − 1) / 2, soit 1 119 FCFA à ces paramètres.
 
## Limites
 
Aucune donnée ne renseigne le taux de défaut dans les tontines de l'UEMOA : les résultats sont conditionnels au taux retenu. Le simulateur est un outil d'illustration issu d'un mémoire de recherche, il ne constitue pas un conseil financier.
 
## Prototype blockchain
 
Le contrat intelligent associé au mémoire est déployé sur le testnet Sepolia : [0x450b516594764CE4C2BC2a8be780897C285d2A3C](https://sepolia.etherscan.io/address/0x450b516594764CE4C2BC2a8be780897C285d2A3C).
 
