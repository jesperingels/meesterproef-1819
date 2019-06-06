# Aantekeningen

## Learning React
I used this [Tutorial](https://react.holiday/2017/) to understand the basics of React.
### Props
```Javascript
import React from "react";
import ReactDOM from "react-dom";

function Greeting(props) {
  return <h1>Hello {props.name}!</h1>;
}

ReactDOM.render(
  <Greeting name="bulbasaur" />,
  document.getElementById("root")
);
```

Using props with while using a class to define a component
```Javascript
class ClapCounter extends React.Component {
  render() {
    return (
      <div>
        <button
          type="button"
          onClick={() => alert(1 + " claps")}
        >
        👏
        </button>
        <i> be the first to clap {this.props.name}</i>
      </div>
    );
  }
}

ReactDOM.render(
  <ClapCounter name='jesper' />,
  document.getElementById("root")
);

```

### Children
The component can be used dynamic, when you want to use the component for instance a button. You might want the text/content to change but the rest of the button to stay the same. This is how you can *smoosh* these together.

```Javascript
ReactDOM.render(
  <ClapCounter>
    <h1>Clap This!</h1>
  </ClapCounter>,

  ...
```

```Javascript
class ClapCounter extends React.Component {
  render () {
    <div>
      {this.props.children}

      ...
```

The `<h1>` element will be placed on the spot where: `{this.props.children}` is defined in the component.

### States
A state stores a value which you can use in the component itself, e.g. for calculations. 

How to set a state for a component:
```Javascript
class MyStateOfMind extends React.Component {
  constructor() {
    super();
    this.state = { sexy: true }
  }
  ...
```

ESNext way:
```Javascript
class MyStateOfMind extends React.Component {
  state = { sexy: true }
  ...
  ```

  #### Change the state in the component:
  ```Javascript
  <button
  type="button"
  onClick={() =>
    this.setState({ clapCount: 1 })
  }
>

...
```

#### Change the state dynamically
```Javascript
...

this.setState((previousState) =>
  ({ clapCount: previousState.clapCount + 1 })
)

...
```

### Rendering data
Use .map() to put the JSON data in for example a list:
```Javascript
class Pokemon extends React.Component {
  state = {
    character: null
  };

  componentDidMount() {
    fetchPokemon(this.props.id, character =>
      this.setState({ character })
    );
  }

  render() {
    return this.state.character ? (
      <div>
        {console.log(this.state.character)}
        <h2>{this.state.character.name}</h2>

        <h4>Abilities</h4>
        <ul>
          {this.state.character.abilities.map(ability => (
            <li>{ability.ability.name}</li>
          ))}
        </ul>
      </div>
    ) : (
      <div>loading...</div>
    );
  }
}

```

Don't forget to set a key! 

```Javascript
<li key={ability.ability.name}>
  {ability.ability.name}
</li>
```

### Event aan component doorgeven
Gebruik het geïmporteerde component in je huidige component.
Geef 'onClick' als property mee
```Javascript
     <Button
          onClick={() => {
            console.log("hello");
          }}
        >
          -
        </Button>
```

In het Button component:
```Javascript
  render() {
    return <button onClick={this.props.onClick}>{this.props.children}</button>;
  }
```

### Lifecycle Hooks
When pressing the button to update the property id the number changes but the api call doesn't start again. This is what Lifecycle Hooks are used for. 
```Javascript
import React from "react";
import ReactDOM from "react-dom";
import fetchPokemon from "./fetchPokemon";

class Pokemon extends React.Component {
  state = {
    character: null
  };
  
  componentDidUpdate(prevProps) {
    // Typical usage (don't forget to compare props):
    if (this.props.id !== prevProps.id) {
      fetchPokemon(this.props.id).then(character =>
        this.setState({ character }))
    }
  }

  componentDidMount() {
    fetchPokemon(this.props.id).then(character =>
      this.setState({ character })
    );
  }

  render() {
    return this.state.character ? (
      <div>
        <h2>{this.state.character.name}</h2>

        <h4>Abilities</h4>
        <ul>
          {this.state.character.abilities.map(ability => (
            <li key={ability.ability.name}>
              {ability.ability.name}
            </li>
          ))}
        </ul>
      </div>
    ) : (
      <div>loading...</div>
    );
  }
}

class PokemonPager extends React.Component {
  state = {
    id: 1
  };

  render() {
    return (
      <div>
        <button
          type="button"
          onClick={() =>
            this.setState(({ id }) => ({ id: id - 1 }))}
        >
          Previous
        </button>
        
        <button
          type="button"
          onClick={() =>
            this.setState(({ id }) => ({ id: id + 1 }))}
        >
          Next
        </button>
        
        <h2>{this.state.id}</h2>

        <Pokemon id={this.state.id} />
        
      </div>
    );
  }
}

ReactDOM.render(
  <PokemonPager />,
  document.getElementById("root")
);

```

## New ES6 things (I didn't know of)
(Using Typescript)

When having this object:
```Typescript
interface Props {
    className?: string
    type?: ButtonType
    styleOverride?: StyleType
    onClick?: React.MouseEventHandler<HTMLButtonElement>
}
```

You can pick two out in a shorter way:
```Javascript
const { className, styleOverride } = this.props
```
