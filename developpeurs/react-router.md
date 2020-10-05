# React Router

Ce module, permet de gérer les route de votre application single page. Voyons son utilisation avec un exemple, vous allez voir c'est très simple.

## Installation

```shell
npm install react-router-dom
```

## Utilisation

On doit tout d'abord importer tous les éléments dont on a besoin pour construire nos routes.

```JSX
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";
```

- Router: il va englober toutes nos routes
- Link: c'est avec cet élément qu'on va créer nos liens vers nos routes
- Switch: c'est ici qu'on va stocker les routes
- Route: c'est dans les routes qu'on va définir quel composant utiliser

Ensuite dans notre application on va définir nos liens vers nos futures routes. Pour ce faire on crée un composant `<Link>`et on lui donne comme attribut `to=""`, ce dernier sera notre route.

```jsx
export default function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/users">Users</Link>
            </li>
          </ul>
        </nav>

        {/* On va ajouter ici le Switch dans un instant */}

      </div>
    </Router>
  );
}
```

Maintenant il faut définir un `switch`qui va être l'endroit où le router va regarder après une route qui correspond à celle sur laquelle notre utilisateur à cliquer. Pour ce faire on crée d'abord un composant `<Switch>`qui va englober toutes nos composants`<Route>` qui eux on en attribut `path=""`. Ce dernier doit correspondre aux `to=""`définit dans les `<Link>`. Entre les `<Route>`on va placer le composant que le router doit charger.

```jsx 
<Switch>
  <Route path="/about">
    <About />
  </Route>
  <Route path="/users">
    <Users />
  </Route>
  <Route path="/">
    <Home />
  </Route>
</Switch>
```

Du coup quand on clique sur le `link`About, le router va regarder si il a une route qui correspond à `/about`et va afficher le composant `<About>`. Dans l'exemple ci-dessous il s'agit d'une simple fonction qui va changer le titre à afficher sur notre app. Vous pouvez copier-coller le code suivant dans une page javascript pour tester.

```jsx
import React from "react";
import ReactDOM from 'react-dom';
import {
  BrowserRouter as Router,
  Switch,
  Route,
  Link
} from "react-router-dom";

export default function App() {
  return (
    <Router>
      <div>
        <nav>
          <ul>
            <li>
              <Link to="/">Home</Link>
            </li>
            <li>
              <Link to="/about">About</Link>
            </li>
            <li>
              <Link to="/users">Users</Link>
            </li>
          </ul>
        </nav>

        {/* A <Switch> looks through its children <Route>s and
            renders the first one that matches the current URL. */}
        <Switch>
          <Route path="/about">
            <About />
          </Route>
          <Route path="/users">
            <Users />
          </Route>
          <Route path="/">
            <Home />
          </Route>
        </Switch>
      </div>
    </Router>
  );
}

function Home() {
  return <h2>Home</h2>;
}

function About() {
  return <h2>About</h2>;
}

function Users() {
  return <h2>Users</h2>;
}

ReactDOM.render(
  <App />,
  document.getElementById('root')
  );
```

## Conclusion

C'est assez simple de gérer ses liens avec React-Router, normalement vous n'aurez pas besoin d'allez beaucoup plus loin, mais si jamais et comme toujours... voici le lien vers [:book: la documentation](https://reactrouter.com/web/guides/quick-start)