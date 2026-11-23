# Cahier de mise en service — HaitiBoutik

## Objectif demandé
- Une seule boutique officielle administrée par HaitiBoutik.
- Les clients consultent le catalogue, passent une commande et règlent via les moyens réellement intégrés.
- Un fournisseur partenaire prépare et livre directement au client lorsque ses conditions le permettent.
- La plateforme conserve une commission selon une règle transparente, calculée uniquement sur les commandes admissibles et confirmées.
- Les retraits de commissions via NatCash sont envisagés, après vérification et activation officielle.

## État actuel du nouveau dépôt
- Interface française et catalogue de démonstration : créés.
- Panier navigateur : créé.
- Préparation locale d'un récapitulatif : créée; pas d'envoi serveur.
- Produits, stocks, prix et fournisseurs : non vérifiés.
- Commandes persistantes : non implémentées.
- Paiements MonCash, NatCash et cartes : non connectés.
- Paiement automatique fournisseur et transfert de commission : non implémentés.
- Retraits NatCash : non connectés.

## Règles techniques à implémenter côté serveur
1. Ne jamais faire confiance au prix, total ou commission envoyés par le navigateur.
2. Recalculer prix, livraison, taxes éventuelles et commission côté serveur.
3. Enregistrer les événements de paiement avec identifiant de transaction et protection contre les doublons.
4. Confirmer une commande payée uniquement après validation authentifiée du prestataire.
5. Libérer le paiement fournisseur selon les conditions contractuelles.
6. En cas d'annulation ou remboursement, annuler ou ajuster la commission.
7. Protéger les fonctions administrateur par authentification et contrôle de rôle côté serveur.
8. Ne jamais stocker les numéros de carte, PIN, mots de passe ou codes OTP.

## Vérification fournisseur obligatoire
Pour chaque produit : prix fournisseur, disponibilité, frais de livraison, pays desservis, livraison directe, délais, suivi colis, retours, frais supplémentaires, devise et méthode de règlement. Aucun fournisseur n'est considéré comme vérifié avant confirmation écrite.

## Mise en service financière
Les comptes de paiement, contrats et transferts doivent être activés par un adulte responsable habilité et les prestataires concernés.
