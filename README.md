NAPA
NAPA met en relation des étudiants et des particuliers pour des missions ponctuelles à domicile, en commençant par les cours particuliers.

Les étudiants gagnent un revenu flexible, déclaré et compatible avec leurs cours.
Les particuliers trouvent un étudiant vérifié près de chez eux. Grâce au CESU et à son avance immédiate de crédit d'impôt, ils ne paient réellement que la moitié du prix.

Statut : projet en démarrage, en phase d'étude de marché (landing page de préinscription). Lancement prévu à Grenoble. Dernière mise à jour : 24/10/2026.

La vision complète (problème, cadre CESU, concurrence, risques, décisions, roadmap) se trouve dans docs/vision.md.


Comment ça marche
Un étudiant publie une offre de cours, ou un particulier publie une demande.
Ils se trouvent grâce à la recherche (matière, niveau, quartier, disponibilités) et se mettent en contact.
Le cours a lieu au domicile du particulier.
Le particulier, qui est l'employeur, déclare et paie l'étudiant via Cesu+ sur cesu.urssaf.fr. Le crédit d'impôt de 50 % est déduit immédiatement.
Le particulier laisse un avis sur l'étudiant.

Le paiement ne passe pas par NAPA : il passe par le CESU.
Utilisateurs
Profil
Ce qu'il veut faire
Étudiant
Créer son profil (études, matières, disponibilités, tarif), trouver des élèves près de chez lui, être payé en étant déclaré, se constituer une réputation
Particulier
Trouver rapidement un étudiant de confiance, connaître le coût réel après crédit d'impôt, laisser un avis
Équipe NAPA (admin)
Vérifier les profils étudiants, modérer les annonces, traiter les signalements et les litiges

Périmètre de la V1 (Grenoble)
Inscription et connexion avec confirmation d'e-mail (étudiant ou particulier)
Vérification du statut étudiant : e-mail universitaire (@univ-grenoble-alpes.fr, @grenoble-inp.fr…) ou carte étudiante
un onglet qui explique le fonctionnement du CESU et qui guide(NAPA se contente d'un guide pour mettre en place Cesu+. Napa ne gere pas les declarations)
Profil étudiant : (age, études, quelles matières il peut enseigner jusqu'à quel niveau, un extrait de casier judiciaire (bulletin n° 3))
Publication de demandes (particulier) pour qui est fait la demande (lui ou son enfant ou autre), tarif
Afficher trois montants : le salaire net de l'étudiant, le coût employeur avec cotisations, et le coût réel après crédit d'impôt
Recherche et filtres : matière, niveau, quartier, disponibilité
Avis et notes
Pages légales : mentions légales, CGU, politique de confidentialité

Hors V1 :

messagerie interne (le mode de mise en contact reste à préciser) ;
paiement intégré (le paiement passe par le CESU) ;
application mobile native ;
autres villes ;
autres catégories de missions.
Stack technique
Brique
Choix
Application web
Next.js (React)
Authentification et base de données
Supabase
Landing page : contacts et newsletter
Brevo
Hébergement de l'application
À décider (développement en local pour l'instant)
Hébergement de la landing page
Hébergeur gratuit, en HTTPS, sur le nom de domaine NAPA (jamais une IP avec un port)

Équipe
NAPA est porté par Clément et Camille, cofondateurs. 

