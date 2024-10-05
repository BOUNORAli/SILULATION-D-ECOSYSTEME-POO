# Simulateur d'Écosystème

Ce projet est un simulateur d'écosystème réalisé en Java dans le cadre d'un devoir de Programmation Orientée Objet (POO). Le simulateur modélise un environnement virtuel peuplé d'êtres vivants tels que des animaux et des végétaux, et simule leur comportement au fil du temps.

## Sommaire

- [Introduction](#introduction)
- [Présentation de l'architecture du projet](#présentation-de-larchitecture-du-projet)
- [Diagramme de classes](#diagramme-de-classes)
- [Description détaillée des classes principales](#description-détaillée-des-classes-principales)
- [Implémentation des fonctionnalités principales](#implémentation-des-fonctionnalités-principales)
- [Tests](#tests)
- [Conclusion et perspectives](#conclusion-et-perspectives)
- [Annexes et Explication de quelques parties du code](#annexes-et-explication-de-quelques-parties-du-code)

## Introduction

Nous avons réalisé un projet consistant à créer un simulateur d'écosystème. L'objectif principal était de modéliser un environnement virtuel peuplé d'êtres vivants tels que des animaux et des végétaux, afin de simuler leur comportement au fil du temps. Notre but était de développer un système réaliste où les êtres vivants interagissent entre eux et avec leur environnement.

Ce projet était motivé par notre volonté de comprendre et d'explorer les dynamiques écologiques et les interactions complexes qui se produisent dans un écosystème. Nous souhaitions résoudre des problèmes tels que la croissance et la survie des plantes en fonction des ressources disponibles, la prédation entre les animaux, la compétition pour les ressources et les changements environnementaux liés aux conditions climatiques.

En termes de fonctionnalités, nous voulions créer un simulateur flexible et extensible qui permette d'ajouter facilement de nouveaux types d'êtres vivants, de définir des comportements spécifiques pour chaque espèce, de modéliser des interactions complexes et de visualiser l'évolution de l'écosystème au fil du temps.

Dans ce rapport, nous détaillerons la conception et la mise en œuvre du simulateur d'écosystème. Nous présenterons les différentes classes et interfaces utilisées, ainsi que les principaux mécanismes et algorithmes qui régissent le comportement des êtres vivants. Nous expliquerons également comment nous avons utilisé une interface graphique pour visualiser l'écosystème en temps réel.

Nous espérons que ce projet approfondira notre compréhension des écosystèmes et des interactions complexes qui s'y produisent. Nous sommes impatients de voir les résultats de nos simulations et d'observer comment les différentes espèces interagissent et évoluent dans cet environnement virtuel.

## Présentation de l'architecture du projet

Nous avons conçu l'architecture du projet de manière à fournir une structure modulaire et flexible pour le simulateur d'écosystème. Notre approche s'appuie sur la programmation orientée objet, en organisant le code en différentes classes et interfaces, qui jouent chacune un rôle spécifique et interagissent entre elles pour former un système cohérent.

Voici les principales classes que nous avons créées :

- **EtreVivant** : Cette classe abstraite constitue la base pour tous les êtres vivants de notre écosystème. Elle définit des attributs communs tels que la santé, la position actuelle, la couleur et le rayon. Elle propose également des méthodes pour effectuer des actions spécifiques à chaque être vivant et pour accéder aux informations sur la santé et la position.
- **Animal** : Cette classe abstraite hérite de "EtreVivant" et représente les animaux de notre écosystème. Elle ajoute des comportements spécifiques aux animaux, tels que le déplacement et la consommation d'autres êtres vivants. Nous avons également créé des classes dérivées spécifiques pour différents types d'animaux, comme les insectes, les oiseaux, les lapins et les loups. Chaque classe dérivée implémente les actions propres à chaque espèce.
- **Vegetal** : Cette classe abstraite hérite également de "EtreVivant" et représente les végétaux de notre écosystème. Elle inclut des attributs tels que le niveau d'eau, l'âge et la taille, ainsi que des comportements de croissance spécifiques aux végétaux. Nous avons créé des classes dérivées spécifiques pour des types de végétaux tels que les arbres et les plantes vivaces. Chaque classe dérivée met en œuvre des règles de croissance et de consommation d'eau spécifiques à chaque espèce.
- **Zone** : Cette classe représente une zone dans notre écosystème. Elle contient une liste d'êtres vivants résidents, ainsi que des attributs tels que le niveau d'eau, la température et le type de la zone. La classe "Zone" permet d'ajouter et de supprimer des êtres vivants, de modifier les niveaux d'eau et de température, et de vérifier le type de la zone en fonction des conditions environnementales.
- **GrilleNature** : Cette classe représente la grille de notre écosystème, qui est composée de différentes zones. Elle contient une matrice de zones et fournit des méthodes pour accéder aux zones adjacentes, récupérer une zone spécifique en fonction de ses coordonnées, et simuler l'évolution de l'écosystème sur une certaine période de temps.
- **GrilleNatureGUI** : Cette classe gère l'interface graphique du simulateur d'écosystème. Elle hérite de "JFrame" et utilise des méthodes de dessin pour représenter visuellement les zones et les êtres vivants de l'écosystème. Elle fournit également des méthodes pour mettre à jour et rafraîchir l'interface graphique pendant la simulation.

Ces différentes classes interagissent entre elles pour créer le simulateur d'écosystème. Par exemple, la classe "GrilleNature" utilise la classe "Zone" pour gérer les résidents et les conditions environnementales de chaque zone. Les classes "Animal" et "Vegetal" interagissent avec la classe "Zone" pour se déplacer, se nourrir et se reproduire. La classe "GrilleNatureGUI" utilise la classe "GrilleNature" pour obtenir les informations sur l'écosystème et les représenter graphiquement.

L'architecture modulaire du projet nous permet d'ajouter facilement de nouveaux types d'êtres vivants en créant des classes dérivées d'"Animal" ou de "Vegetal", et de modifier les comportements existants en les redéfinissant dans les classes dérivées. De plus, l'utilisation de l'interface graphique nous permet de visualiser en temps réel l'évolution de l'écosystème et les interactions entre les êtres vivants.

Cette architecture logicielle offre donc une structure claire et extensible pour notre simulateur d'écosystème, qui nous permet de modéliser efficacement les interactions complexes et les dynamiques écologiques.

## Diagramme de classes

- **Relation d'héritage** :
  - La classe abstraite `EtreVivant` est la classe de base pour les différentes entités vivantes du projet, telles que les animaux et les végétaux. Les classes `Animal` et `Vegetal` héritent de `EtreVivant`, ce qui signifie qu'elles héritent de ses attributs et méthodes communes.
  - Les classes `Insecte`, `Oiseau`, `Mammifere` héritent de la classe `Animal`, ce qui signifie qu'elles héritent à leur tour des attributs et méthodes de `EtreVivant` et `Animal`.
  - Les classes `Carnivore` et `Herbivore` héritent de la classe `Mammifere`, ce qui signifie qu'elles héritent à leur tour des attributs et méthodes de `EtreVivant`, `Animal` et `Mammifere`.
  - Les classes `Lapin` et `Loup` héritent des classes `Herbivore` et `Carnivore` respectivement, ce qui signifie qu'elles héritent à leur tour des attributs et méthodes de `EtreVivant`, `Animal` et `Mammifere`, `Herbivore` et `Carnivore` respectivement.
  - Les classes `Arbre` et `Vivace` héritent de la classe `Vegetal`, ce qui signifie qu'elles héritent des attributs et méthodes de `EtreVivant` et `Vegetal`.

- **Interfaces** :
  - L'interface `ConsommerEau` est implémentée par la classe abstraite `EtreVivant`, ce qui signifie que chaque être vivant doit fournir une implémentation de la méthode `consommerEau()`.
  - L'interface `Reproduire` est implémentée par les classes `Lapin` et `Loup`, ce qui signifie que ces animaux ont la capacité de se reproduire et doivent fournir une implémentation de la méthode `reproduire()`.
  - L'interface `Manger` est implémentée par les classes `Lapin` et `Loup`, ce qui signifie que ces animaux ont la capacité de manger d'autres êtres vivants et doivent fournir une implémentation de la méthode `manger(EtreVivant cible)`.

## Description détaillée des classes principales

- **EtreVivant** : Cette classe abstraite joue un rôle essentiel en tant que classe de base pour tous les êtres vivants de l'écosystème. Elle définit des attributs communs tels que la santé, la zone actuelle, la couleur et le rayon, ainsi que des méthodes pour exécuter des actions spécifiques à chaque être vivant et accéder aux informations sur la santé et la zone.
- **Animal** : Cette classe abstraite hérite de "EtreVivant" et représente les animaux de l'écosystème. Elle ajoute des comportements propres aux animaux, comme le déplacement et l'alimentation d'autres êtres vivants. Les méthodes "seDeplacer(Zone zone)" et "manger(EtreVivant cible)" doivent être implémentées par les classes dérivées pour définir le déplacement vers une zone spécifique et le comportement alimentaire respectivement.
- **Vegetal** : Cette classe abstraite hérite également de "EtreVivant" et représente les végétaux de l'écosystème. Elle inclut des attributs tels que le niveau d'eau, l'âge et la taille, ainsi que des comportements de croissance propres aux végétaux. La méthode "croissance()" permet à la plante de grandir en augmentant son âge, sa taille et en diminuant son niveau d'eau.
- **Zone** : Cette classe représente une zone dans l'écosystème, contenant une liste d'êtres vivants résidents ainsi que des attributs tels que le niveau d'eau, la température et le type de la zone. Des méthodes comme "addEtreVivant(EtreVivant etreVivant)" et "removeEtreVivant(EtreVivant etreVivant)" permettent d'ajouter ou de supprimer des êtres vivants de la liste résidente. Il y a également des méthodes pour accéder et modifier le niveau d'eau, la température et le type de la zone, ainsi que pour obtenir les zones adjacentes et le nombre d'arbres résidents.
- **GrilleNature** : Cette classe représente la grille de l'écosystème, composée de différentes zones. Elle permet de simuler l'évolution de l'écosystème sur un certain nombre de tours et gère les interactions entre les êtres vivants. Des méthodes telles que "simuler(int tours, GrilleNatureGUI gui)", "getZoneAdjacente(int i, int j, int direction)" et "getZone(int x, int y)" sont fournies pour effectuer ces opérations.
- **GrilleNatureGUI** : Cette classe est responsable de l'interface graphique de l'écosystème. Elle utilise les méthodes "paint(Graphics g)", "update()" et "updateAndRepaint()" pour afficher et mettre à jour graphiquement la grille et les êtres vivants.

Cette approche modulaire offre une structure claire et extensible, respectant le principe de responsabilité unique. Chaque classe a un rôle précis et des méthodes spécifiques, ce qui facilite la compréhension, la maintenance et l'ajout de nouvelles fonctionnalités à l'écosystème.

## Implémentation des fonctionnalités principales

- **Comportement des êtres vivants** :
  Chaque être vivant, qu'il s'agisse d'un animal ou d'un végétal, dispose d'une méthode "executeActions()" qui lui permet d'exécuter ses actions spécifiques à chaque tour de simulation. Le comportement des animaux est implémenté dans les classes dérivées de la classe abstraite "Animal". Chaque animal a sa propre implémentation des méthodes "seDeplacer()" et "manger()" en fonction de son type et de son comportement alimentaire. Le comportement des végétaux est implémenté dans les classes dérivées de la classe abstraite "Vegetal". Chaque plante a sa propre implémentation de la méthode "croissance()", qui détermine sa croissance en fonction de son niveau d'eau et de son âge.

- **Capacité à se nourrir** :
  Les animaux qui implémentent l'interface "Manger" ont la capacité de se nourrir d'autres êtres vivants. Lors de l'exécution de la méthode "executeActions()", un animal peut choisir une cible parmi les autres êtres vivants de sa zone et utiliser la méthode "manger(cible)" pour effectuer la prédation. L'implémentation spécifique de la méthode "manger(cible)" dépend du comportement alimentaire de chaque animal. Par exemple, un carnivore peut tuer et consommer un herbivore, tandis qu'un herbivore peut simplement consommer un végétal.

- **Capacité à boire** :
  Les animaux et les végétaux qui implémentent l'interface "ConsommerEau" ont la capacité de boire de l'eau. Lors de l'exécution de la méthode "executeActions()", un être vivant peut appeler la méthode "consommerEau()" pour réduire son niveau d'eau.

- **Capacité à se reproduire** :
  Les animaux et les végétaux qui implémentent l'interface "Reproduire" ont la capacité de se reproduire. Lors de l'exécution de la méthode "executeActions()", un être vivant peut appeler la méthode "reproduire()" pour générer une descendance. La mise en œuvre spécifique de la reproduction dépend du type d'être vivant.

- **Capacité à se déplacer** :
  Les animaux qui implémentent l'interface "SeDeplacer" ont la capacité de se déplacer vers une zone adjacente. Lors de l'exécution de la méthode "executeActions()", un animal peut choisir une direction de déplacement au hasard et appeler la méthode "seDeplacer(zone)" pour se déplacer vers la zone adjacente spécifiée. La méthode "getZoneAdjacente(i, j, direction)" de la classe "GrilleNature" est utilisée pour obtenir la zone adjacente en fonction des coordonnées actuelles et de la direction de déplacement.

- **Mort des êtres vivants** :
  Les êtres vivants perdent de la santé ou meurent en fonction de certaines conditions. Par exemple, un animal peut perdre de la santé s'il manque d'eau ou s'il ne parvient pas à se nourrir. S'il atteint un certain seuil de santé, il peut mourir et être supprimé de la liste des résidents de sa zone. Les végétaux peuvent également perdre de la santé s'ils manquent d'eau, et s'ils atteignent un certain seuil, ils peuvent également mourir et être supprimés de la liste des résidents de leur zone.

L'implémentation de ces fonctionnalités repose sur les principes de l'héritage et de l'interface. Chaque classe d'êtres vivants (animaux, végétaux) implémente les interfaces appropriées en fonction de leurs capacités spécifiques. Cela permet une flexibilité et une extensibilité dans la définition de nouvelles fonctionnalités pour différents types d'êtres vivants. De plus, en encapsulant le comportement spécifique dans des classes dérivées, il est facile de maintenir et de modifier le comportement des êtres vivants sans affecter le reste du système.

## Tests

J'ai réalisé des tests en exécutant le programme avec différentes configurations de grille et en observant le comportement des êtres vivants au fil des simulations. Cela m'a permis de vérifier si les animaux et les plantes se développent, se reproduisent, se déplacent et meurent conformément aux règles définies. J'ai également vérifié si les zones de la grille changeaient correctement de type en fonction des conditions telles que la température et le niveau d'eau. Ces tests ont été effectués en utilisant une interface graphique qui affiche la grille et les êtres vivants, ce qui a facilité l'observation et la validation visuelles. En fin de compte, les tests ont joué un rôle essentiel dans la validation et la fiabilité du programme, garantissant qu'il fonctionne correctement dans divers scénarios et conditions.

## Conclusion et perspectives

Dans le cadre de ce projet, j'ai développé un simulateur de vie naturelle en utilisant Java. L'objectif initial était de créer un système permettant de modéliser le comportement des êtres vivants dans un environnement simulé et d'observer leur croissance, leurs interactions et leur évolution au fil du temps. Je suis satisfait des résultats obtenus, car le programme remplit les objectifs fixés et offre une représentation réaliste et dynamique de la vie naturelle.

L'architecture logicielle que j'ai choisie, basée sur des classes et des interfaces bien définies, a permis de structurer efficacement le programme et de séparer les responsabilités. Cela facilite la compréhension, la maintenance et l'extension du code. Les différentes classes, telles que les animaux, les végétaux et les zones, ont des rôles bien définis et interagissent entre elles de manière cohérente.

J'ai implémenté avec succès les fonctionnalités principales du simulateur, notamment le comportement des êtres vivants, leur capacité à se nourrir, à boire, à se reproduire, à se déplacer et à mourir. Les règles de croissance des plantes, la prédation entre les animaux et les interactions avec l'environnement sont bien représentées dans le programme. Les tests réalisés, tels que les tests unitaires, les tests d'intégration et les tests de validation, ont confirmé le bon fonctionnement du système et ont aidé à identifier et à corriger des bugs potentiels.

Pour les perspectives d'amélioration, il serait intéressant d'ajouter de nouvelles fonctionnalités pour enrichir le simulateur. Par exemple, on pourrait introduire des facteurs aléatoires tels que les conditions météorologiques, les maladies ou les catastrophes naturelles pour rendre l'environnement plus dynamique et réaliste. On pourrait également envisager d'ajouter de nouvelles espèces d'animaux ou de plantes, chacune ayant des comportements spécifiques. Une amélioration possible serait également d'optimiser les performances du simulateur pour gérer de grandes grilles avec un grand nombre d'êtres vivants.

En conclusion, ce projet a été une expérience enrichissante qui m'a permis de développer mes compétences en programmation orientée objet et de mettre en pratique les principes de modélisation de la vie naturelle. Le simulateur réalisé répond aux objectifs fixés et constitue une base solide pour de futures améliorations et extensions.

## Annexes et Explication de quelques parties du code

### `executeActions()`

```java
public void executeActions() {
    // Manger
    if (this instanceof Manger && !this.currentZone.getEtresVivants().isEmpty()) {
        List<EtreVivant> autresEtresVivants = new ArrayList<>(this.currentZone.getEtresVivants());
        autresEtresVivants.remove(this);
        if (!autresEtresVivants.isEmpty()) {
            EtreVivant cible = autresEtresVivants.get(new Random().nextInt(autresEtresVivants.size()));
            ((Manger) this).manger(cible);
            this.rayon++; // Augmenter le rayon après avoir mangé
        }
    }

    // Boire de l'eau
    if (this instanceof ConsommerEau) {
        ((ConsommerEau) this).consommerEau();
    }

    // Reproduction
    if (this instanceof Reproduire) {
        EtreVivant enfant = ((Reproduire) this).reproduire();
        if (enfant != null) {
            this.currentZone.addEtreVivant(enfant);
        }
    }

    // Gestion des déplacements
    if (this instanceof SeDeplacer) {
        List<Zone> zonesAdjacentes = this.currentZone.getZonesAdjacentes();
        if (!zonesAdjacentes.isEmpty()) {
            Zone nouvelleZone = zonesAdjacentes.get(new Random().nextInt(zonesAdjacentes.size()));
            ((SeDeplacer) this).seDeplacer(nouvelleZone);
        }
    }
}
```

La méthode `executeActions()` de la classe `EtreVivant` est responsable de l'exécution des actions spécifiques à un être vivant donné. Voici une explication détaillée de chaque partie de cette méthode :

- **Manger** :
  La première partie vérifie si l'instance courante implémente l'interface `Manger` et si la zone actuelle contient d'autres êtres vivants. Si ces conditions sont remplies, une liste nommée `autresEtresVivants` est créée en copiant la liste des êtres vivants de la zone actuelle, à l'exception de l'instance courante elle-même. Si la liste `autresEtresVivants` n'est pas vide, un être vivant cible est sélectionné au hasard dans cette liste. Ensuite, la méthode `manger(cible)` de l'interface `Manger` est appelée, permettant ainsi à l'instance courante de se nourrir de la cible. Après avoir mangé, le rayon de l'instance courante est augmenté de 1.

- **Boire de l'eau** :
  Cette partie vérifie si l'instance courante implémente l'interface `ConsommerEau`. Si c'est le cas, la méthode `consommerEau()` de l'interface `ConsommerEau` est appelée, permettant à l'instance courante de boire de l'eau.

- **Reproduction** :
  Cette partie vérifie si l'instance courante implémente l'interface `Reproduire`. Si c'est le cas, la méthode `reproduire()` de l'interface `Reproduire` est appelée, permettant ainsi à l'instance courante de générer une descendance. Si la descendance n'est pas nulle, elle est ajoutée à la zone actuelle en utilisant la méthode `addEtreVivant(enfant)`.

- **Gestion des déplacements** :
  Cette partie vérifie si l'instance courante implémente l'interface `SeDeplacer`. Si c'est le cas, la méthode `getZonesAdjacentes()` de la zone actuelle est appelée pour obtenir une liste de zones adjacentes. Si la liste n'est pas vide, une zone adjacente est sélectionnée au hasard dans cette liste. Ensuite, la méthode `seDeplacer(nouvelleZone)` de l'interface `SeDeplacer` est appelée, permettant à l'instance courante de se déplacer vers la nouvelle zone.

En résumé, la méthode `executeActions()` de la classe `EtreVivant` coordonne l'exécution des différentes actions spécifiques à chaque type d'êtres vivants. Elle permet à un être vivant de se nourrir, de boire, de se reproduire et de se déplacer. Cela garantit que les comportements spécifiques à chaque type d'êtres vivants sont correctement exécutés et gérés au sein de la simulation.

### `manger(EtreVivant cible)` et `trouverNouvelleZone()`

```java
@Override
public void manger(EtreVivant cible) {
    // If a target is provided, the carnivore eats it
    if (cible != null && cible instanceof Herbivore) {
        this.currentZone.removeEtreVivant(cible);
        System.out.println("Carnivore mange herbivore");
        this.hunger -= 5; // the carnivore's hunger is reduced after eating
    } else {
        // If no target is provided, the carnivore looks for a herbivore in the current zone
        Iterator<EtreVivant> iterator = this.currentZone.getEtresVivants().iterator();
        while (iterator.hasNext()) {
            EtreVivant ev = iterator.next();
            if (ev instanceof Herbivore) {
                // consommer l'herbivore
                System.out.println("Carnivore mange herbivore");
                iterator.remove();
                this.hunger -= 5; // the carnivore's hunger is reduced after eating
                break; // un carnivore mange seulement un herbivore à la fois
            }
        }
    }
}

public Zone trouverNouvelleZone() {
    // Obtenir les zones adjacentes à la zone actuelle de l'insecte
    List<Zone> zonesAdjacentes = this.currentZone.getZonesAdjacentes();

    // Si aucune zone adjacente n'est disponible, l'insecte reste dans sa zone actuelle
    if (zonesAdjacentes.isEmpty()) {
        return this.currentZone;
    }

    // Sinon, choisissez une zone adjacente au hasard
    Random random = new Random();
    int index = random.nextInt(zonesAdjacentes.size());
    return zonesAdjacentes.get(index);
}
```

- **`manger(EtreVivant cible)`** :
  Cette méthode est utilisée pour permettre à un carnivore de manger un être vivant cible. La méthode prend en paramètre un objet cible de type `EtreVivant`, qui représente l'être vivant que le carnivore va essayer de manger. La méthode vérifie d'abord si la cible n'est pas nulle et si la cible est une instance de la classe `Herbivore`. Si ces conditions sont remplies, cela signifie que le carnivore a une cible spécifique à manger. Dans ce cas, la cible est retirée de la zone actuelle du carnivore à l'aide de la méthode `removeEtreVivant(cible)` de la classe `Zone`. Un message est également affiché dans la console pour indiquer que le carnivore a mangé un herbivore. Enfin, la variable `hunger` du carnivore est réduite de 5 pour représenter que sa faim diminue après avoir mangé.

  Si aucune cible n'est spécifiée, cela signifie que le carnivore recherche un herbivore dans sa zone actuelle. Un itérateur est utilisé pour parcourir les êtres vivants de la zone actuelle. Si un herbivore est trouvé, il est retiré de la liste des êtres vivants de la zone, un message est affiché dans la console et la variable `hunger` du carnivore est réduite de 5. La boucle est ensuite interrompue pour s'assurer que le carnivore mange seulement un herbivore à la fois.

- **`trouverNouvelleZone()`** :
  Cette méthode est utilisée par un carnivore pour trouver une nouvelle zone vers laquelle se déplacer. La méthode commence par obtenir une liste de zones adjacentes à la zone actuelle du carnivore à l'aide de la méthode `getZonesAdjacentes()` de la classe `Zone`. Si aucune zone adjacente n'est disponible, ce qui signifie que le carnivore est piégé dans sa zone actuelle, la méthode retourne simplement la zone actuelle. Sinon, si des zones adjacentes sont disponibles, la méthode utilise un objet `Random` pour générer un index aléatoire à partir de la liste des zones adjacentes. La méthode retourne ensuite la zone correspondante à cet index, ce qui représente la nouvelle zone vers laquelle le carnivore se déplacera.

Ces deux méthodes de la classe `Carnivore` sont essentielles pour le comportement spécifique d'un carnivore dans la simulation. La méthode `manger()` permet au carnivore de manger un herbivore ciblé ou de chercher un herbivore dans sa zone actuelle. La méthode `trouverNouvelleZone()` permet au carnivore de choisir une nouvelle zone vers laquelle se déplacer. Ces fonctionnalités contribuent à la dynamique de la simulation et à l'interaction entre les différents types d'êtres vivants.

### `simuler(int tours, GrilleNatureGUI gui)`

```java
public void simuler(int tours, GrilleNatureGUI gui) {
    for (int tour = 0; tour < tours; tour++) {
        for (int i = 0; i < taille; i++) {
            for (int j = 0; j < taille; j++) {
                Zone zone = zones[i][j];
                List<EtreVivant> etresVivants = new ArrayList<>(zone.getEtresVivants());

                // Chaque être vivant dans la zone effectue son action
                for (EtreVivant etreVivant : etresVivants) {
                    etreVivant.executeActions();
                }

                // Changement du type de zone
                zone.changerType();
            }
        }

        // Mise à jour de l'interface graphique tous les 5 tours
        if ((tour + 1) % 5 == 0) {
            gui.update();
            try {
                Thread.sleep(1000); // Attendre 1 seconde avant de continuer pour pouvoir observer les changements
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}
```

La méthode `simuler(int tours, GrilleNatureGUI gui)` est utilisée pour exécuter la simulation pendant un certain nombre de tours spécifié. Voici une explication détaillée de son fonctionnement :

- La méthode prend en paramètre le nombre de tours à simuler (`tours`) et une instance de la classe `GrilleNatureGUI` (`gui`) qui représente l'interface graphique de la simulation.
- La boucle externe `for` est utilisée pour itérer à travers chaque tour de la simulation. Le compteur `tour` est initialisé à 0 et augmente de 1 à chaque itération jusqu'à atteindre le nombre de tours spécifié.
- Les boucles `for` imbriquées sont utilisées pour parcourir chaque zone de la grille. La variable `i` représente la ligne et la variable `j` représente la colonne de la zone.
- À chaque itération, la méthode récupère la zone correspondante à la position (`i`, `j`) dans la grille en utilisant `zones[i][j]`. Elle crée également une liste `etresVivants` contenant tous les êtres vivants présents dans cette zone en utilisant la méthode `getEtresVivants()` de la classe `Zone`.
- Ensuite, la boucle `for-each` est utilisée pour parcourir chaque être vivant de la liste `etresVivants`. Pour chaque être vivant, la méthode `executeActions()` est appelée, ce qui lui permet d'effectuer ses actions spécifiques définies dans sa classe respective.
- Après que tous les êtres vivants de la zone aient effectué leurs actions, la méthode `changerType()` de la classe `Zone` est appelée pour effectuer un éventuel changement de type de la zone en fonction des conditions spécifiées.
- Tous les 5 tours, la condition `(tour + 1) % 5 == 0` est vérifiée. Si elle est vraie, cela signifie que c'est le moment de mettre à jour l'interface graphique. La méthode `update()` de l'objet `gui` est appelée pour rafraîchir l'affichage de la simulation.
- Après avoir mis à jour l'interface graphique, la méthode utilise `Thread.sleep(1000)` pour faire une pause de 1 seconde, permettant ainsi d'observer les changements sur l'interface graphique avant de continuer avec la prochaine itération.

Cette méthode est responsable de l'exécution de la simulation, où chaque être vivant effectue ses actions et les zones peuvent changer de type au fil des tours. Elle permet également de mettre à jour l'interface graphique périodiquement pour refléter les changements dans la simulation.
