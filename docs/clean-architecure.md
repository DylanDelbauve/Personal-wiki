---
authors:
  name: Abderrahmane Roumane
  title: Co-creator of Docusaurus 1
  url: https://medium.com/@abderrahmane.roumane.ext
  image_url: https://miro.medium.com/v2/resize:fill:176:176/1*k7LsZYw7hxXxbhPpqvGeuw.png
---

# Les fondements de la clean architecture: une voie vers un code durable

## Introduction
Dans un univers informatique où la complexité des systèmes ne cesse de croître, structurer son code devient une quête perpétuelle pour tout développeur en quête d’excellence. C’est dans cette optique que la Clean Architecture s’érige comme un phare dans la nuit, guidant les programmeurs vers des eaux plus sereines de la maintenabilité et de l’évolutivité. Conçue par Robert C. Martin, cette approche vise à organiser le code de manière à le rendre à la fois flexible et résilient face aux changements.

L’essence de la Clean Architecture réside dans sa capacité à séparer les différentes préoccupations d’une application, réduisant ainsi le couplage entre les composants et facilitant les tests. Elle encourage une dépendance minimale à l’égard des Framework et des outils externes, permettant aux règles métier de briller au centre de l’architecture. Mais pourquoi adopter cette approche et comment peut-elle se concrétiser dans vos projets ? C’est ce que nous allons explorer dans cet article.

Nous plongerons au cœur des principes qui fondent la Clean Architecture, nous déchiffrerons sa structure et ses composants, et nous démystifierons les avantages qu’elle promet. Puis, à travers un guide pratique, nous examinerons comment ces théories prennent vie dans le code que nous écrivons au quotidien.

Que vous soyez un fervent adepte des principes SOLID, un étudiant en génie logiciel ou simplement curieux de découvrir de nouvelles méthodologies, ce voyage au sein de la Clean Architecture est conçu pour enrichir votre palette de compétences en développement logiciel. Alors préparez-vous à décoller vers un horizon où le code est propre, ordonné et, surtout, élégamment structuré.

## Qu’est-ce que la Clean Architecture ?
Au cœur de l’ingénierie logicielle moderne se trouve un défi de taille : concevoir des applications qui non seulement répondent aux exigences actuelles mais sont aussi préparées pour les évolutions et innovations de demain. C’est ici que la Clean Architecture entre en scène, tel un architecte visionnaire pour le code que nous écrivons.

La Clean Architecture n’est pas simplement une méthode ; c’est une philosophie de conception logicielle qui place les préoccupations métier de l’application au centre de l’attention. Elle se distingue par une organisation du code en couches concentriques, chacune ayant un rôle spécifique et indépendant. Cette structure favorise une dépendance vers l’intérieur, où les couches les plus externes — telles que l’interface utilisateur et les mécanismes de stockage de données — dépendent des couches internes, mais jamais l’inverse. Le résultat est une base de code où le cœur métier reste intact et indépendant des outils extérieurs et des Framework.

Historiquement, la Clean Architecture s’inspire de plusieurs approches antérieures comme l’architecture hexagonale, les couches en oignon et les principes SOLID, toutes prônant la séparation des responsabilités et la souplesse de conception. Le terme lui-même a été popularisé par Robert C. Martin dans son ouvrage de 2012, où il présente cette architecture comme un idéal vers lequel tendre pour un code épuré et robuste.

### Les principes fondamentaux de la Clean Architecture s’articulent autour de concepts clés tels que :
- L’indépendance vis-à-vis du Framework : L’architecture ne doit pas dépendre des bibliothèques logicielles. Cela permet de minimiser le coût du changement de Framework et d’assurer une plus grande agilité dans le développement.
- La testabilité : Le système d’entreprise doit être testable sans UI, base de données, serveur web ou tout autre élément externe.
- L’indépendance vis-à-vis de l’UI : L’interface utilisateur peut changer facilement, sans modification majeure du reste du système. Une application web peut devenir une application de bureau sans réécrire la logique métier.
- L’indépendance vis-à-vis de la base de données : La logique métier ne dépend pas du type de base de données utilisée, permettant ainsi un changement aisé de système de stockage.
- L’indépendance des agents extérieurs : La logique métier ne doit pas être affectée par des changements dans des services externes, qu’il s’agisse de serveurs web ou d’autres formes d’interfaces.
Dans les sections suivantes, nous explorerons en détail chacune des couches de la Clean Architecture, leurs interactions, et comment elles s’imbriquent pour former une structure solide et flexible.

## Les Composants de la Clean Architecture
La Clean Architecture se compose de plusieurs couches, chacune avec sa propre responsabilité. Comprendre le rôle de chaque composant est essentiel pour maîtriser la mise en œuvre de cette architecture. Examinons les éléments qui constituent cette structure méthodique :

### Les Entités (Entities):

- Au cœur de la Clean Architecture se trouvent les entités. Ce sont les objets du domaine métier qui incarnent les règles et cas d’usage les plus généraux de l’application. Les entités sont indépendantes des détails techniques et peuvent être utilisées par toutes les couches de l’application.
### Les Cas d’Usage (Use Cases):

- Autour des entités, nous trouvons les cas d’usage. Ils encapsulent toute la logique métier spécifique à l’application. Un cas d’usage décrit une action spécifique que l’utilisateur veut effectuer et les règles métier qui l’encadrent. Il interagit avec les entités et détermine comment les données doivent être transmises entre les entités et les couches extérieures.
### Les Adaptateurs d’Interface (Interface Adapters):

Cette couche, souvent appelée “controllers”, “presenters” ou “gateways”, fait le lien entre les cas d’usage et les couches les plus externes. Elle adapte les données aux formats nécessaires pour les cas d’usage et les présente ensuite dans le format requis par l’interface utilisateur ou d’autres API.
###Les Interfaces Utilisateurs (UIs) et les Frameworks et Drivers (Frameworks & Drivers):

- Enfin, la couche externe comprend tout ce qui est en contact avec le monde extérieur, comme l’interface utilisateur, les systèmes de bases de données, les serveurs web, etc. Cette couche est tenue à l’écart des règles métier et sert uniquement à communiquer avec d’autres systèmes ou avec l’utilisateur.
La clé de la Clean Architecture réside dans le respect de la règle de dépendance : toute modification dans les couches externes ne doit pas affecter les couches internes. Les données traversent ces couches via des mécanismes de passage bien définis, souvent à travers des interfaces ou des ports, garantissant que les dépendances circulent uniquement vers l’intérieur.

Dans la pratique, cela signifie que l’on peut modifier l’interface graphique ou la base de données sans perturber la logique métier. De même, on peut réutiliser la logique métier si l’on décide de développer une nouvelle application avec un objectif différent.

La Clean Architecture ne se limite pas à une simple théorie ; elle se manifeste à travers des principes de conception tangibles qui, lorsqu’ils sont appliqués, produisent un code qui est à la fois solide et souple. Elle incarne l’idéal d’un code à l’épreuve du temps, capable de s’adapter et de prospérer dans un écosystème technologique en perpétuelle évolution.

Dans la section suivante, nous aborderons les avantages pratiques et les défis liés à l’implémentation de la Clean Architecture, ainsi que des conseils pour naviguer dans les complexités qui accompagnent ce modèle de conception.

## Avantages de la Clean Architecture
L’adoption de la Clean Architecture dans le développement de logiciels peut transformer la manière dont une équipe approche la conception et la maintenance de ses applications. Voici les avantages clés qui en découlent :

### Flexibilité et Adaptabilité :

- Avec ses couches bien séparées, la Clean Architecture offre une grande flexibilité. Si un jour une nouvelle technologie ou un nouveau Framework devient prédominant, vous pouvez l’intégrer sans refondre entièrement votre système. Cette adaptabilité est cruciale dans un paysage technologique où le changement est la seule constante.
### Indépendance vis-à-vis des technologies :

- En découplant la logique métier des technologies utilisées pour l’interface utilisateur ou l’accès aux données, vous n’êtes plus lié à des choix technologiques spécifiques. Votre code métier reste pur et agnostique, ce qui favorise une meilleure pérennité.
### Facilité de Test :

- La séparation nette des préoccupations permet de tester les composants de manière isolée. Les cas d’usage peuvent être validés indépendamment des bases de données ou des interfaces utilisateur, ce qui simplifie considérablement les tests unitaires et d’intégration.
### Maintenance et Évolution simplifiées :

- La clarté et l’organisation du code facilitent sa compréhension et sa maintenance. Ajouter de nouvelles fonctionnalités ou modifier des comportements existants devient plus aisé lorsque la logique métier n’est pas enchevêtrée avec le reste de l’infrastructure de l’application.
### Déploiement parallèle :

- Les équipes peuvent travailler sur différentes couches simultanément avec un minimum de dépendances croisées. Cela accélère le développement et réduit les conflits entre les équipes travaillant sur différents aspects de l’application.
### Sécurité renforcée :

- En isolant la logique métier des influences extérieures, vous réduisez la surface d’attaque potentielle. Les interactions avec des systèmes externes sont contrôlées et peuvent être sécurisées de manière centralisée.
### Durabilité du code :

- La Clean Architecture encourage des pratiques qui garantissent que le code reste lisible, compréhensible et donc durable. Cela aide à préserver l’investissement dans le code sur le long terme et facilite le transfert de connaissances au sein des équipes.
Cependant, il est important de noter que l’adoption de la Clean Architecture n’est pas sans défis. La complexité initiale, le temps nécessaire à l’apprentissage et à la mise en œuvre, et la nécessité de discipline en termes de respect des frontières de la couche sont quelques-uns des obstacles à surmonter. Toutefois, les avantages à long terme l’emportent souvent sur ces difficultés initiales.

Dans la section suivante, nous traiterons de ces défis et de la manière de les relever, tout en maximisant les bénéfices de cette approche architecturale dans vos projets de développement logiciel.

## Mise en œuvre de la Clean Architecture
La mise en œuvre de la Clean Architecture exige une compréhension approfondie de ses principes ainsi qu’une application rigoureuse de ses directives. Voici des étapes essentielles pour intégrer avec succès cette architecture dans vos projets :

### Analyse et Conception Initiales :

- Avant même de penser au code, il est crucial de bien comprendre les exigences du domaine d’application. Identifiez les entités, les règles métier et les cas d’usage qui seront au centre de votre architecture. Cette compréhension initiale est la pierre angulaire d’une application bien architecturée.
### Définition des Frontières :

- Établissez clairement les limites entre les différentes couches de votre application. Assurez-vous que les membres de votre équipe comprennent la règle de dépendance qui veut que les couches externes dépendent des couches internes et non l’inverse.
### Création des Entités :

- Commencez par développer les entités qui modélisent le domaine métier. Ces entités doivent être des objets simples, sans logique spécifique à un cas d’usage ou dépendance envers des Framework ou des bases de données.
### Développement des Cas d’Usage :

- Implémentez la logique métier dans des cas d’usage qui manipulent les entités. Chaque cas d’usage doit représenter un processus métier distinct et être indépendant des détails de l’implémentation externe.
### Conception des Adaptateurs :

- Mettez en place des adaptateurs pour convertir les données d’entrée et de sortie en formats utilisables par les cas d’usage et les entités. Les adaptateurs permettent d’isoler la logique métier des détails techniques de l’application.
### Intégration des Interfaces Utilisateur et des Drivers :

- Développez l’interface utilisateur, les bases de données, les services web et tout autre composant externe nécessaire à votre application. Ces composants devraient être conçus de manière à s’adapter facilement aux changements grâce à l’utilisation des adaptateurs.
### Tests Rigoureux :

- Implémentez une suite de tests robuste qui couvre les entités, les cas d’usage et les interactions entre les couches. L’objectif est de s’assurer que la logique métier fonctionne comme prévu et que les couches externes interagissent correctement avec les cas d’usage.
### Révision et Refactorisation :

À mesure que le projet évolue, il est vital de revoir et de refactoriser le code pour maintenir l’alignement avec les principes de la Clean Architecture. L’objectif est de préserver la séparation des préoccupations et d’éviter le couplage fort.
En suivant ces étapes, vous pouvez assurer une intégration cohérente de la Clean Architecture dans vos projets. Il est important de se rappeler que la transition vers cette architecture peut nécessiter du temps et des efforts considérables, surtout pour les équipes habituées à des approches moins structurées.

La Clean Architecture n’est pas une solution universelle et ne se prête pas à chaque situation. Elle révèle toute sa valeur dans le cadre d’applications complexes où les enjeux de durabilité, de testabilité et de flexibilité sont au premier plan. Pour des projets de moindre envergure ou des prototypes conçus rapidement, une architecture plus simple peut souvent s’avérer suffisante.

Dans la prochaine section, nous discuterons des meilleures pratiques et des pièges à éviter lors de l’adoption de la Clean Architecture, pour garantir que vos efforts portent leurs fruits et que votre code reste propre et évolutif.

## Défis et Solutions lors de la mise en œuvre de la Clean Architecture
L’intégration de la Clean Architecture est une entreprise qui n’est pas exempte de défis. Cependant, pour chaque obstacle, il existe des stratégies et des solutions pour les surmonter.

### Complexité Perçue :

- Défi : La Clean Architecture peut sembler complexe à première vue, avec ses multiples couches et règles.
- Solution : La formation et l’éducation sont essentielles. Investissez dans des sessions de formation pour vous-même et votre équipe. Utilisez des diagrammes et des exemples concrets pour décomposer la complexité et montrer comment chaque partie s’imbrique dans le tout.
### Courbe d’apprentissage :

- Défi : Il peut y avoir une courbe d’apprentissage raide pour les équipes non familières avec les principes de la Clean Architecture.
- Solution : Commencez par de petits projets ou modules pour pratiquer et renforcer les principes. Encouragez le pair programming et les revues de code pour partager les connaissances et les compétences.
### Résistance au Changement :

- Défi : Les développeurs peuvent résister au changement, surtout s’ils sont habitués à un certain ensemble de pratiques.
- Solution : Montrez les bénéfices à long terme de la Clean Architecture en termes de maintenance et d’évolutivité. Faites des membres de l’équipe des champions du changement en impliquant tout le monde dans le processus de décision.
### Sur-ingénierie :

- Défi : Il peut être tentant de trop concevoir ou d’introduire une complexité inutile en suivant les principes de la Clean Architecture.
- Solution : Restez pragmatique. Appliquez les principes de la Clean Architecture là où ils apportent de la valeur. Utilisez une approche itérative pour évaluer et ajuster la conception au fur et à mesure.
### Intégration avec des Systèmes Externes :

- Défi : L’intégration de systèmes externes qui ne suivent pas les mêmes principes peut être problématique.
- Solution : Utilisez des adaptateurs et des façades pour encapsuler l’intégration externe, gardant ainsi la logique métier isolée et protégée des détails d’implémentation des systèmes tiers.
### Performance :

- Défi : Certaines personnes craignent que les multiples couches puissent nuire à la performance.
- Solution : Profilerez et mesurez les performances réelles plutôt que de supposer. Les optimisations prématurées sont souvent inutiles. Lorsque des problèmes de performances surviennent, adressez-les avec des stratégies ciblées.
### Maintien de la Discipline :

- Défi : Maintenir la discipline nécessaire pour suivre les règles de la Clean Architecture peut être difficile, surtout sous pression.
- Solution : Intégrez des contrôles de qualité dans votre processus de CI/CD. Mettez en place des outils de linting et d’analyse statique pour renforcer les bonnes pratiques.
En abordant ces défis de front et en mettant en œuvre des solutions pragmatiques, la transition vers la Clean Architecture peut être lissée, permettant à votre équipe de récolter les fruits d’une base de code plus propre, plus maintenable et plus évolutive.

## Exemple de Clean Architecture en TypeScript
Pour démontrer les principes de la Clean Architecture dans un contexte pratique, je vais vous fournir un exemple de code simplifié en TypeScript. L’exemple suivant illustre une petite partie de ce que pourrait être une application respectant la Clean Architecture, en mettant l’accent sur la séparation des préoccupations.

Imaginez que nous avons une application qui gère les utilisateurs. Nous allons créer une structure de dossiers qui reflète les différentes couches de la Clean Architecture.

```text
src/
|-- entities/
|   `-- User.ts
|-- use_cases/
|   `-- CreateUser.ts
|-- interfaces/
|   |-- controllers/
|   |   `-- UserController.ts
|   `-- gateways/
|       `-- UserRepository.ts
|-- framework_drivers/
    `-- web/
        `-- ExpressServer.ts
```

Entities (Entités)

```ts
// src/entities/User.ts

export class User {
    constructor(
        public readonly id: string,
        public readonly name: string,
        public readonly email: string
    ) {}
}
```

Use Cases (Cas d’utilisation)

```ts
// src/use_cases/UserUseCases.ts

import { User } from "../entities/User";
import { UserRepository } from "../interfaces/gateways/UserRepository";

export class UserUseCases {
  constructor(private userRepository: UserRepository) {}

  async createUser(name: string, email: string): Promise<User> {
    const user = new User(this.generateId(), name, email);
    await this.userRepository.add(user);
    return user;
  }

  async getUserById(userId: string): Promise<User | null> {
    return this.userRepository.findById(userId);
  }

  async updateUser(userId: string, updateParams: { name?: string; email?: string }): Promise<User> {
    const user = await this.userRepository.findById(userId);

    if (!user) {
      throw new Error('User not found');
    }

    user.name = updateParams.name || user.name;
    user.email = updateParams.email || user.email;

    await this.userRepository.update(user);

    return user;
  }

  async deleteUser(userId: string): Promise<void> {
    await this.userRepository.delete(userId);
  }

  private generateId(): string {
    // Implementation for ID generation, could be a UUID or similar
    return '...';
  }
}
```

Interface Adapters (Adaptateurs d’Interface)


```ts
// src/interfaces/gateways/UserRepository.ts

import { User } from "../../entities/User";

export interface UserRepository {
  add(user: User): Promise<void>;
  findById(userId: string): Promise<User | null>;
  update(user: User): Promise<void>;
  delete(userId: string): Promise<void>;
}

```

```ts
// src/interfaces/controllers/UserController.ts

import { CreateUser } from "../../use_cases/CreateUser";
import { Request, Response } from "express";

export class UserController {
    constructor(private createUserUseCase: CreateUser) {}

    async createUser(req: Request, res: Response) {
        const { name, email } = req.body;

        try {
            const user = await this.createUserUseCase.execute(name, email);
            res.json(user);
        } catch (error) {
            // Gestion des erreurs
            res.status(500).json({ error: error.message });
        }
    }
}
```

Frameworks & Drivers (Cadres et Pilotes)


```ts
// src/framework_drivers/web/ExpressServer.ts

import express from 'express';
import { UserController } from '../../interfaces/controllers/UserController';

const app = express();
app.use(express.json());

const userController = new UserController(/* Dépendances */);

app.post('/users', (req, res) => userController.createUser(req, res));

app.listen(3000, () => {
    console.log('Server is running on port 3000');
});
```

## Conclusion
La Clean Architecture propose une vision structurée et disciplinée du développement logiciel, conçue pour favoriser la création de systèmes évolutifs et maintenables. En plaçant les règles métier au cœur de l’architecture, elle facilite la création de logiciels qui peuvent non seulement s’adapter aux exigences changeantes mais aussi survivre à l’évolution des Framework et des modes technologiques.

Toutefois, comme nous l’avons exploré, l’adoption de la Clean Architecture n’est pas sans défis. Elle exige un engagement envers une formation continue, une volonté de s’adapter et de changer de pratiques établies, ainsi qu’une approche pragmatique pour éviter la sur-ingénierie. Les bénéfices, cependant, justifient les efforts : une base de code plus propre, une plus grande flexibilité face aux changements, et une meilleure testabilité.

En fin de compte, la Clean Architecture n’est pas seulement un ensemble de directives pour structurer le code, c’est une philosophie de développement qui privilégie la clarté, la séparation des préoccupations et la durabilité. En intégrant ces principes dans votre travail, vous pouvez non seulement améliorer la qualité de vos applications mais aussi renforcer la dynamique de travail de votre équipe.

Comme pour tout modèle architectural, il est important de l’adapter aux spécificités de chaque projet. Il n’y a pas de solution universelle, mais dans le paysage en constante évolution du développement logiciel, la Clean Architecture offre un cadre solide pour naviguer dans la complexité sans se perdre dans les détails.

Livres :

”Clean Architecture: A Craftsman’s Guide to Software Structure and Design” par Robert C. Martin
Articles de Blog et Études de Cas :

http://cleancoder.com/products

By [Abderrahmane Roumane](https://medium.com/@abderrahmane.roumane.ext)  from [Medium](https://medium.com/@abderrahmane.roumane.ext/les-fondements-de-la-clean-architecture-une-voie-vers-un-code-durable-1542f91f9d0a)