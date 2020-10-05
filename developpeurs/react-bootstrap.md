# React Bootstrap

Comme React utilise du JSX pour sa mise en page et non pas de l'HTML pure, il est parfois difficile d'incorporer des éléments Bootstrap en utilisant le CSS officiel. Du coup il existe (évidement) un module pour utiliser les fonctionnalités et composants de Bootstrap, ça s'appel tout simplement... React-Bootstrap.

## Installation

```shell
npm install react-bootstrap bootstrap
```

## Utilisation

C'est super simple d'utilisation. Il suffit de savoir quel composant on veut utiliser et ensuite de l'importer en haut de la page, comme pour n'importe quel composant React.

```jsx
import Button from 'react-bootstrap/Button';
```

Ensuite il suffit de faire appel à ce composant là où vous en avez besoin.

```jsx
<>
  <Button variant="primary">Primary</Button>{' '}
  <Button variant="secondary">Secondary</Button>{' '}
  <Button variant="success">Success</Button>{' '}
  <Button variant="warning">Warning</Button>{' '}
  <Button variant="danger">Danger</Button> <Button variant="info">Info</Button>{' '}
  <Button variant="light">Light</Button> <Button variant="dark">Dark</Button>{' '}
  <Button variant="link">Link</Button>
</>
```

:exclamation: Pour que la plupart des composants s'affiche correctement, il faut aussi importer la feuille de style.

```jsx
import 'bootstrap/dist/css/bootstrap.min.css';
```

Je ne vais pas vous refaire un cours sur Bootstrap car au final tout fonctionne quasi pareil, c'est juste la syntaxe qui est un peu différente. Il vous suffit comme toujours d'allez jetez un coup d'oeil dans [:book: la documentation](https://react-bootstrap.github.io/getting-started/introduction/)

Voici un exemple pour vous prouvez que c'est pas si compliqué, voici un layout réalisé avec le système de grid de Bootstrap, dont les colonnes sont à largeur auto.

```jsx
<Container>
  <Row>
    <Col>1 of 2</Col>
    <Col>2 of 2</Col>
  </Row>
  <Row>
    <Col>1 of 3</Col>
    <Col>2 of 3</Col>
    <Col>3 of 3</Col>
  </Row>
</Container>
```

ou encore des colonnes dont la largeur est responsive:

```jsx
<Container>
  <Row>
    <Col sm={8}>sm=8</Col>
    <Col sm={4}>sm=4</Col>
  </Row>
  <Row>
    <Col sm>sm=true</Col>
    <Col sm>sm=true</Col>
    <Col sm>sm=true</Col>
  </Row>
</Container>
```

Vraiment rien de bien compliqué.

![didnotread](https://media.giphy.com/media/nDMnCjqVziG2EI8P4a/giphy.gif)