CARTE SCOLAIRE DE PARIS

A. Les fichiers sources en ligne :
- Fichier des rues de Paris avec leur code Paris : http://parisdata.opendatasoft.com/explore/dataset/liste_des_bureaux_de_vote_2013_voies_de_paris/download/?format=csv&timezone=Europe/Berlin&use_labels_for_header=true
- Fichier des adresses des rues de Paris : http://parisdata.opendatasoft.com/explore/dataset/adresse_paris/download/?format=csv&timezone=Europe/Berlin&use_labels_for_header=true
- l'API de serveur de la DGSCO perimsco.paris.fr/

B. Les fichiers de traitement de donn�es sont :
- 1.codage_adresses_rues_Paris_vf.R : qui code la base des adresses avec les codes rue de Paris ;
- 2.Carte_scolaire_scrap_Paris.R : qui extrait du serveur 3 la carte scolaires pour toute la base adresse de Paris
- 3.geocodage_etablissements.R : qui code l'adresse des �tablissements

C. Les fichiers de r�sultat sont :
1.- adresses_paris_codees.csv : qui rajoute un champ � la base adresse de Paris pour rajouter le code rue de Paris
	contient notamment les champs :
	- N_SQ_AD : identifiant unique d'adresse,
	- VOIE_ID : identifiant unique des rues de Paris ;
2.- correspondance_N_SQ_VO-VOIE_ID.csv : la version de liaison simple permettant de reconstituer adresses_paris_codees.csv � partir de la source (correspondance entre les codes rues de la base adresse et ceux de Paris) ;
3.- carte_scolaire_maternelles.csv : la carte scolaire de maternelle reliant les champs :
	- N_SQ_AD : index adresse de la base 1.
	- maternelle : num�ro de l'�tablissement dans la liste 6.
4. - carte_scolaire_primaires.csv : la carte scolaire de primaire reliant les champs :
	- N_SQ_AD : index adresse de la base 1.
	- primaire : num�ro de l'�tablissement dans la liste 6.
5. - carte_scolaire_college.csv : la carte scolaire de college reliant les champs :
	- N_SQ_AD : index adresse de la base 1.
	- maternelle : num�ro de l'�tablissement dans la liste 6.
6.- etablissements_Paris.csv : liste des �tablissements, en majuscule, avec les champs :
	- libelle.complet : la cha�ne de caract�re compl�te extrait du site ;
	- index : l'index utilis� dans les tables 3., 4. et 5 ;
	- libelle : le nom de l'�cole (�cole maternelle, �cole primaire ou coll�ge avec le nom) ;
	- numero : num�ro dans la rue ;
	- rue : rue ;
	- N_SQ_AD : le code adresse de l'�tablissement suivant le codage du fichier 1.