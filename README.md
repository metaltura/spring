# metaltura/spring

Le vocabulaire Spring Boot, à côté du métamodèle d'application qu'il ne change pas. Le dépôt `spring-angular` le relie à Angular.

## Ce qu'il contient

- `models/Spring.yaml` — le vocabulaire Spring Boot (PLAT-306), à côté d'Application qu'il ne change pas : un contexte (boot.Context) réalise une Application avec son paquet Java · un controller (web.Controller) expose une ressource de l'API · sert les points d'entrée qu'il liste et appelle un service · un service (service.Service) utilise des repositories · un repository (jpa.Repository) gère une entité JPA · une entité JPA (jpa.Entity) est liée à une table SQL et décrit chacun de ses attributs : un attribut simple (jpa.Field) désigne sa colonne · une association ManyToOne sa clé étrangère et l'entité visée · une association OneToMany la ManyToOne qui porte le lien. Rien ne se déduit d'un nom. Ses listes de choix ne proposent que les éléments de l'Application du contexte · de son contexte ou de la table de l'entité. Son diagramme de classes montre aussi les classes d'Application qu'il désigne.

## Ce dont il dépend

| Dépôt | Ce qu'il en emploie | Ligne `depends` |
| --- | --- | --- |
| `metaltura/application` | `Application`, que `Spring` désigne ou spécialise | `metaltura/application/Application@v1.0.0` |

`Diagram` et `Uml` sont des modèles système de Metaltura : leur nom seul suffit.

## L'utiliser depuis un autre dépôt

Écrire dans la liste `depends` du modèle :

```yaml
depends:
  - metaltura/spring/Spring@v1.0.0
```

Metaltura clone ce dépôt à l'étiquette `v1.0.0`, puis `metaltura/application` dont il dépend, et `metaltura/domain` que ce dernier nomme. Toute la librairie est à `v1.0.0` : Metaltura refuse qu'un même dépôt soit demandé à deux versions.

## D'où il vient

Ce dépôt vient du dépôt privé `Kogitec/simple-mda`, `main` à `96a1a75` (PLAT-1461), rangé par sujet par PLAT-1498 en un seul commit : son modèle était sous `models/applications/spring-angular/`. L'historique de ses fichiers reste dans `simple-mda`, archivé.
