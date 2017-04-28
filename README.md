Progressive app
===============

Installation
------------

*Forker* ce repertoire sur github.

Ensuite cloner ce repertoire :

`git clone https://github.com/<your_pseudo>/meetup_pwa_29_4_2017.git`

Entrer dans le repertoire avec la commande :

`cd meetup_pwa_29_4_2017`

Puis installer React Router:

`npm install --save react-router@3.0.5`

Ajouter les routes dans `src/App.js` :

```
import React, { Component } from 'react';
import { Router, browserHistory, Route, Link } from 'react-router';
import logo from './logo.svg';
import './App.css';

const Page = ({ title }) => (
    <div className="App">
      <div className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <h2>{title}</h2>
      </div>
      <p className="App-intro">
        This is the {title} page.
      </p>
      <p>
        <Link to="/">Home</Link>
      </p>
      <p>
        <Link to="/about">About</Link>
      </p>
      <p>
        <Link to="/settings">Settings</Link>
      </p>
    </div>
);

const Home = (props) => (
  <Page title="Home"/>
);

const About = (props) => (
  <Page title="About"/>
);

const Settings = (props) => (
  <Page title="Settings"/>
);

class App extends Component {
  render() {
    return (
      <Router history={browserHistory}>
        <Route path="/" component={Home}/>
        <Route path="/about" component={About}/>
        <Route path="/settings" component={Settings}/>
      </Router>
    );
  }
}

export default App;
```

Maintenant, tester l'application avec `yarn start`.

Etape 1 : installer Lighthouse
------------------------------

Lighthouse est un outil gratuit de Google pour évaluer si notre application
respecte les standart des *progressive web apps*.

Pour installer ce plugin, aller sur https://chrome.google.com/webstore/detail/lighthouse/blipmdconlkpinefehnmjammfjpmpbjk.

Maintenant lancer un rapport Lighthouse pour évaluer l'application.

Le score est seulement de 24/100.

Etape 2 : configurer le service worker
--------------------------------------
