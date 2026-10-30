\# Pipeline de dépistage du diabète en temps réel



Architecture Big Data hybride (batch et streaming), déployée sous Docker, qui estime en continu le risque de diabète à partir de dossiers de santé et affiche les résultats sur un tableau de bord en direct.



> Le modèle illustre une architecture : il ne pose aucun diagnostic médical.





\## Architecture



!\[Architecture du pipeline](docs/architecture.png)



\- \*\*Circuit temps réel\*\* : générateur de dossiers → Kafka → Spark Structured Streaming → MongoDB → Streamlit

\- \*\*Circuit d'apprentissage\*\* : données CDC → HDFS → Spark MLlib → modèle enregistré dans HDFS





\## Technologies



| Domaine | Outils |

|---|---|

| Conteneurisation | Docker, Docker Compose |

| Stockage et calcul distribués | Hadoop (HDFS, YARN), Apache Spark |

| Streaming | Apache Kafka, Spark Structured Streaming |

| Apprentissage automatique | Spark MLlib |

| Base de données | MongoDB |

| Restitution | Streamlit |

| Langage | Python (PySpark) |





\## Données



Indicateurs de santé et de diabète issus de l'enquête téléphonique BRFSS 2015 du CDC (Centers for Disease Control and Prevention, États-Unis) : environ 250 000 réponses, une vingtaine de variables (tension, cholestérol, IMC, activité physique, âge…) et une variable cible indiquant si la personne est diabétique.



Les données sont publiques et anonymisées. Elles ne sont pas incluses dans ce dépôt : un script de téléchargement sera fourni.





\## Avancement



| Phase | Contenu | État |

|---|---|---|

| Conception | Architecture, choix techniques, plan | Terminée |

| 1. Préparation | Environnement Docker, dépôt Git | En cours |

| 2. Socle | Cluster Hadoop et Spark | À venir |

| 3. Données | Chargement dans HDFS, exploration | À venir |

| 4. Modèle | Entraînement et évaluation avec Spark MLlib | À venir |

| 5. Ingestion | Kafka et générateur de dossiers | À venir |

| 6. Temps réel | Prédiction avec Spark Structured Streaming | À venir |

| 7. Restitution | Tableau de bord Streamlit | À venir |

| 8. Validation | Tests de bout en bout et de tolérance aux pannes | À venir |





\## Documentation



Le document de conception détaillé (objectifs, justification des choix, plan de réalisation et de tests) se trouve dans \[docs/Conception\_Pipeline\_Diabete.docx](docs/Conception\_Pipeline\_Diabete.docx).



\## Auteur



\*\*Berthold Neville\*\* – \[github.com/BertholdNeville](https://github.com/BertholdNeville)



Projet personnel.

