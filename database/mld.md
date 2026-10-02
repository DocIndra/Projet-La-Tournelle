```
utilisateur (id_utilisateur, nom, prenom, email, mot_de_passe, role, langue, actif)
primary key : id_utilisateur
foreign key : aucune

categorie (id_categorie, libelle, sla_cible)
primary key : id_categorie
foreign key : aucune

ticket (id_ticket, titre, description, statut, priorite, localisation,
        date_creation, id_declarant, id_technicien, id_categorie)
primary key : id_ticket
foreign key : id_declarant → utilisateur(id_utilisateur)
              id_technicien → utilisateur(id_utilisateur)
              id_categorie → categorie(id_categorie)

commentaire (id_commentaire, id_ticket, id_auteur, contenu, visibilite, date_commentaire)
primary key : id_commentaire
foreign key : id_ticket → ticket(id_ticket)
              id_auteur → utilisateur(id_utilisateur)

piece_jointe (id_pj, id_ticket, nom_fichier, chemin)
primary key : id_pj
foreign key : id_ticket → ticket(id_ticket)

notification (id_notif, id_utilisateur, id_ticket, type, canal, lu, date_envoi)
primary key : id_notif
foreign key : id_utilisateur → utilisateur(id_utilisateur)
              id_ticket → ticket(id_ticket)

historique_statut (id_historique, id_ticket, id_auteur, ancien_statut, nouveau_statut, date_changement)
primary key : id_historique
foreign key : id_ticket → ticket(id_ticket)
              id_auteur → utilisateur(id_utilisateur)

journal_admin (id_journal, id_admin, action, date_action)
primary key : id_journal
foreign key : id_admin → utilisateur(id_utilisateur)
```
