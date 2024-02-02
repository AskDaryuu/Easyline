# Easyline

import java.util.Scanner;

public class Mission3etape3 {
    public static class Voyageur {
        private String nom;
        private int age;
        private String categorie;
        private AdressePostal adresse;
        private Bagages bagage;

        public Voyageur() {
            this.nom = ""; // Init nom
            this.age = 0; // Init âge
            this.adresse = null; // Init adresse
            this.bagage = null; // Init bagage
            
        }

        public Voyageur(String nom, int age) {
            if (nom.length() >= 2) {
                this.nom = nom; // Init nom
            } else {
                System.out.println("Le nom doit comporter au moins 2 caractères.");// Si le nom est inférieur à 2
                                                                                     // caractères
            }

                if (age >= 0) {
                     this.age = age; // Init âge
                    setCategorie();
                  } else { // Si l'âge est négatif
                       System.out.println("L'âge doit être positif.");
            }
        }
        public Voyageur(String nom, int age, AdressePostal adresse, Bagages bagage) {

            if (nom.length() >= 2) {
                this.nom = nom; // Init nom
            } else {
                System.out.println("Le nom doit comporter au moins 2 caractères.");// Si le nom est inférieur à 2 caractères
            }

                if (age >= 0) {
                     this.age = age; // Init âge
                    setCategorie();
                  } else { // Si l'âge est négatifsd
                       System.out.println("L'âge doit être positif.");
            }
            if (adresse != null) {
                this.adresse = adresse; // Init adresse
            } else {
                System.out.println("L'adresse doit être spécifiée.");
            }
            if (bagage != null) {
                this.bagage = bagage; // Init bagage
            } else {
                System.out.println("Le bagage doit être spécifié.");
            }
        }
        public void setCategorie() {
            if (age < 1) {
                categorie = "nourrisson";
            } else if (age <= 18) {
                categorie = "enfant";
            } else if (age <= 60) {
                categorie = "adulte";
            } else {
                categorie = "senior";
            }
        }
        public void afficherVoyageur() {
            System.out.println( "---------------------------------------------------------------------"); 
            System.out.println("Nom: " + nom); // Affiche nom
            System.out.println("Âge: " + age); // Affiche âge
            System.out.println("Catégorie: " + categorie); // Affiche catégorie
            if (adresse != null) {
                System.out.println(adresse.getAdresseComplete()); // Affiche adresse
            } else {
                System.out.println("Adresse: Non spécifiée");
            }
            if (bagage != null) {
                System.out.println(bagage.getBagagecomplet()); // Affiche bagage
                System.out.println( "---------------------------------------------------------------------");
            } else {
                System.out.println("Bagage: Non spécifié");
            }
        }

        public void setNom(String nom) {
            if (nom.length() >= 2) {
                this.nom = nom; // rends obligatoire le nom de 2 caractères
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("Le nom doit comporter au moins 2 caractères.");
                System.out.println("---------------------------------------------");
            }
        }

        public void setAge(int age) {
            if (age >= 0) {
                this.age = age; // rends obligatoire l'âge positif
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("L'âge doit être positif.");
                System.out.println("---------------------------------------------");
            }
        }

        public String getNom() {
            return nom; // j'ai mis ca ici pour pouvoir rendre nom en public pour pouvoir l'utiliser dans la classe
                        // Voyage
        }

        public int getAge() {
            return age; // j'ai mis ca ici pour pouvoir rendre age en public pour pouvoir l'utiliser dans la classe
                        // Voyage
        }
        public AdressePostal getAdresse() {
            return adresse; // j'ai mis ca ici pour pouvoir rendre adresse en public pour pouvoir l'utiliser dans la classe
                        // Voyage
        }
        public void setAdresse(AdressePostal adresse) {
            if (adresse != null) {
                this.adresse = adresse; // rends obligatoire l'adresse
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("L'adresse doit être spécifiée.");
                System.out.println("---------------------------------------------");
            }
        }

        public Bagages getBagage() {
            return bagage; // j'ai mis ca ici pour pouvoir rendre bagage en public pour pouvoir l'utiliser dans la classe
                        
        }
        public void setbagage(Bagages bagage) {
            if (bagage != null) {
                this.bagage = bagage; // rends obligatoire le bagage
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("Le bagage doit être spécifié.");
                System.out.println("---------------------------------------------");
            }
        }
        
    }




    public static class AdressePostal {// Crée une classe adresse postal
        private String numerorue;
        private int codePostal;
        private String ville;

        public AdressePostal(String numerorue, int codePostal, String ville) {// Constructeur a 3 arguments pour initialiser les attributs de la classe adresse postal                        
            this.numerorue = numerorue;
            this.codePostal = codePostal;
            this.ville = ville;
        }

        public String getNumerorue() {// Get et set pour les attributs de la classe adresse postal
            return numerorue;
        }

        public void setNumerorue(String numerorue) {//set numero de rue
            if (numerorue.length() >= 2) {
                this.numerorue = numerorue;
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("Le numéro de rue doit comporter au moins 2 caractères.");
                System.out.println("---------------------------------------------");
            }
        }

        public int getCodePostal() {//get code postal
            return codePostal;
        }

        public void setCodePostal(int codePostal) {//set code postal
            if (codePostal >= 0) {
                this.codePostal = codePostal;
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("Le code postal doit être positif.");
                System.out.println("---------------------------------------------");
            }
        }

        public String getVille() {//get ville
            return ville;
        }

        public void setVille(String ville) {//set ville
            if (ville.length() >= 2) {
                this.ville = ville;
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("La ville doit comporter au moins 2 caractères.");
                System.out.println("---------------------------------------------");
            }
        }
        public String getAdresseComplete() {
            return "Rue: "+numerorue+" \nCode postal: "+codePostal+" \nVille: "+ville;
        }
        

        public void afficherAdresse() {// Affiche adresse
            System.out.println("Rue: "+numerorue); // Affiche numéro de rue
            System.out.println("Code postal: "+codePostal); // Affiche code postal
            System.out.println("Ville: "+ville); // Affiche ville

        }
    }


    public static class Bagages {// Crée une classe bagages
        private double numeroBagage;
        private double poidsBagage;
        private String couleurBagage;
        
        public Bagages(double numeroBagage, double poidsBagage, String couleurBagage) {// Constructeur a 3 arguments pour initialiser les attributs de la classe bagages
            this.numeroBagage = numeroBagage;
            this.poidsBagage = poidsBagage;
            this.couleurBagage = couleurBagage;
        }
        public Bagages() {// Constructeur a 0 arguments pour initialiser les attributs de la classe bagages
            this.numeroBagage = 0;
            this.poidsBagage = 0;
            this.couleurBagage = "";
        }
        public double getNumeroBagage() {// Get et set pour les attributs de la classe bagages
            return numeroBagage;
        }
        public void setNumeroBagage(double numeroBagage) {//set numero de bagage
            this.numeroBagage = numeroBagage;
        }
        public double getPoidsBagage() {
            return poidsBagage;
        }
        public void setPoidsBagage(double poidsBagage) {//set poids de bagage
            if (poidsBagage == 0 ) {
                this.poidsBagage = poidsBagage;
            } else {
                System.out.println("------------------ERREUR----------------------.");
                System.out.println("Le poids de bagage doit être positif.");
                System.out.println("---------------------------------------------");
            }
        }
        public String getCouleurBagage() {
            return couleurBagage;
        }
        public void setCouleurBagage(String couleurBagage) {//set couleur de bagage
            this.couleurBagage = couleurBagage;
        }
        public String getBagagecomplet() {
            return "Numéro de bagage: "+numeroBagage+" \nPoids de bagage: "+poidsBagage+" \nCouleur de bagage: "+couleurBagage;
        }
        public void afficherBagage() {// Affiche bagage 
            System.out.println("Numéro de bagage: "+numeroBagage);
            System.out.println("Poids de bagage: "+poidsBagage);
            System.out.println("Couleur de bagage: "+couleurBagage);
            System.out.println( "---------------------------------------------------------------------");
        }

    }
    
        

    public static void main(String[] args) {
        Voyageur voyageur = new Voyageur("lucas", 25); // Crée voyageur avec nom et âge
        voyageur.afficherVoyageur(); // Affiche infos
        AdressePostal adresse = new AdressePostal("rue de la paix", 75000, "Paris"); 
        adresse.afficherAdresse(); // Affiche adresse
        Bagages bagage = new Bagages(123, 20, "rouge");
        bagage.afficherBagage();
        
        Voyageur voyageurInit = new Voyageur(); // Crée voyageur avec valeurs par défaut
        AdressePostal adressePostalInit = new AdressePostal("", 0, ""); 
        Bagages bagageInit = new Bagages(0, 0, "");

        Scanner scanner = new Scanner(System.in);
        System.out.println("Saisir le nom : ");
        String nom = scanner.nextLine(); // Saisit nom
        System.out.println("Saisir l'âge : ");
        int age = scanner.nextInt(); // Saisit âge
        scanner.nextLine(); // Consume the newline character
        System.out.println("Saisir le numéro et nom de rue : ");
        String numerorue = scanner.nextLine(); // Saisit numéro de rue
        System.out.println("Saisir le code postal : ");
        int codePostal = scanner.nextInt(); // Saisit code postal
        scanner.nextLine(); //pour evitter les probleme de scanner
        System.out.println("Saisir la ville : ");
        String ville = scanner.nextLine(); // Saisit ville
        System.out.println("Voulez vous saisir un bagage ? (oui/non) : ");
        String saisieBagage = scanner.nextLine(); // Saisit oui ou non
        if (saisieBagage.equals("oui")) {
            System.out.println("Saisir le numéro de bagage : ");
            double numeroBagage = scanner.nextDouble(); // Saisit numéro de bagage
            System.out.println("Saisir le poids de bagage : ");
            double poidsBagage = scanner.nextDouble(); // Saisit poids de bagage
            scanner.nextLine(); //pour evitter les probleme de scanner
            System.out.println("Saisir la couleur de bagage : ");
            String couleurBagage = scanner.nextLine(); // Saisit couleur de bagage
            bagageInit.setNumeroBagage(numeroBagage); // Modifie numéro de bagage
            bagageInit.setPoidsBagage(poidsBagage); // Modifie poids de bagage
            bagageInit.setCouleurBagage(couleurBagage); // Modifie couleur de bagage
           
        }else{
            System.out.println("Vous n'avez pas saisi de bagage");
            bagageInit.setNumeroBagage(0);
            bagageInit.setPoidsBagage(0);
            bagageInit.setCouleurBagage("Pas de bagage");
        }
        
        adressePostalInit.setNumerorue(numerorue); // Modifie numéro de rue
        adressePostalInit.setCodePostal(codePostal); // Modifie code postal
        adressePostalInit.setVille(ville); // Modifie ville
        voyageurInit.setNom(nom); // Modifie nom
        voyageurInit.setAge(age); // Modifie âge
        voyageurInit.setCategorie(); // Modifie catégorie en fonction de l'âge , en oubliant cette ligne la catégorie sera null pour les nouveaux voyageurs
        voyageurInit.setAdresse(adressePostalInit); // Modifie adresse
        voyageurInit.setbagage(bagageInit); // Modifie bagage
        voyageurInit.afficherVoyageur(); // Affiche infos
       // adressePostalInit.afficherAdresse(); // Affiche adresse
        scanner.close();
    }
}
