# GLO-2003 H22 - Floppa

Bienvenue chez Floppa, l'application qui deviendra le meilleur site de vente anonyme au Québec! Notre équipe a maintenant besoin de l'aide de développeurs expérimentés afin de développer l'architecture et les fonctionnalités de l'application! 

Notre équipe a tout de même déjà établie quelques standards qui seront à respecter lors du développement. Également, nous avons prévu le développement en 4 itérations, comportant chacune à la fois des fonctionnalités et des améliorations techniques.

## Mise en place

Les étapes de mises en place du projet sont disponibles [ICI](./setup.md).

## Itérations

- [Itération 1 : Vendeur](https://github.com/glo2003/H22-Iteration1)
- [Itération 2 : Produit](https://github.com/glo2003/H22-Iteration2)
- [Itération 3 : Offre](https://github.com/glo2003/H22-Iteration3)
- [Itération 4 : Vente](https://github.com/glo2003/H22-Iteration4)

## Technologies

L'application **doit** être faite à l'aide de la librairie Jersey. Vous être libre d'ajouter les libraries que vous désirez pour les tests et features additionnelles, mais vous **devez** demander la permission aux auxiliaires avant, **sauf** si vous voulez installer les libraries permises suivantes :

- MongoDB
- Junit
- Rest-assured
- Mockito

## Types généraux

```ts
type DateTime: date et heure selon ISO-8601/RFC-3339 (au timezone UTC)
type Date: date (sans heures) selon ISO-8601/RFC-3339
type Amount: float/double positif arrondi à 2 décimales
type Email: <identifiant>@<service>.<extension> (ex: "john.doe1@gmail.com")
type PhoneNumber: 11 chiffres, en string (ex: +1 819 123 4567 => "18191234567")
type ProductCategory = "sports" | "electronics" | "apparel" | "beauty" | "housing" | "other"
type Percentage: float/double de 0 à 100 arrondi à 2 décimales
type SaleStatus = "ongoing" | "sold" | "cancelled"
```

## Retours d'erreur

### Format

```ts
{
    code: ErrorCode,
    description: string
}
```

### Types

| ErrorCode        | statut HTTP | description                                                                          |
| ---------------- | ----------- | ------------------------------------------------------------------------------------ |
| `MISSING_PARAM`  | 400         | un paramètre (URL, header, JSON, etc.) est manquant                                  |
| `INVALID_PARAM`  | 400         | un paramètre (URL, header, JSON, etc.) est invalide (vide, négatif, trop long. etc.) |
| `ITEM_NOT_FOUND` | 404         | un élément est introuvable (id invalide ou inexistant)                               |

> L'exception pour le statut 500 n'est pas inscrite ici car elle devrait en principe ne jamais être retournée par le serveur

## Informations additionnelles

- Un paramètre "*manquant*" correspond à une valeur inexistante (champs non présent) ou nulle (`Null` en Java ou `null` en JSON).
- Un paramètre "*vide*" correspond à une valeur dont le contenu est "vide" (ex: string vide `""` ou contenant seulement des caractères "vide" (`'\t'`, `'\n'`, `' '`), chiffre vide `0`, etc.).
- Lorsqu'un paramètre est nullable (avec `| null` après sont type), alors ce dernier peut être manquant sans générer d'erreur.
- Un champ non nullabel doit retourner une erreur de type `MISSING_PARAM` si la valeur reçue est manquante.
- Tous les paramètres d'URL (query params) sont optionels et peuvent donc être manquants sans retourner d'erreur.
- Les valeurs "vides" des paramètres d'URL (ex: "") doivent être considérées comme étant des vraies valeurs (ex: filtrer par `title = ""` doit retourner les titres égals à `""`).
- Par défaut, une valeur vide ne doit pas retourner d'exception (sauf si explicitement décrit dans les énoncés de features).

## Références

- RFC-3339 \[[1](https://datatracker.ietf.org/doc/html/rfc3339)\] et ISO-8601 \[[1](https://www.w3.org/TR/NOTE-datetime)\] \[[2](https://www.loc.gov/standards/datetime/iso-tc154-wg5_n0038_iso_wd_8601-1_2016-02-16.pdf)\]: Références pour les format *date* et *datetime* standards

## Changelog

- **17 janvier 2022** : Précisions sur les libraries permises.
