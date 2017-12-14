## Usage

```sh
yarn
yarn lint
```

### The rule `react/no-unused-prop-types` no working

```sh
➜  eslint-plugin-react-no-unused-prop-types git:(master) ✗ yarn lint
yarn run v1.3.2
$ eslint src
✨  Done in 1.56s.
```

### But when remove `{...this.state}` from App.js the rule is working

```js
class App extends Component {
  static propTypes = {
    bar: PropTypes.string.isRequired,
  };

  state = {
    style: { color: 'red' },
  };

  render() {
    return (
      <div className="App">
        <header className="App-header">
          <img src={logo} className="App-logo" alt="logo" />
          <h1 className="App-title">Welcome to React</h1>
        </header>
        <p className="App-intro">
          To get started, edit <code>src/App.js</code> and save to reload.
        </p>
      </div>
    );
  }
}

```

```sh
➜  eslint-plugin-react-no-unused-prop-types git:(master) ✗ yarn lint
yarn run v1.3.2
$ eslint src

/xxxxx/eslint-plugin-react-no-unused-prop-types/src/App.js
  8:10  error  'bar' PropType is defined but prop is never used  react/no-unused-prop-types

✖ 1 problem (1 error, 0 warnings)

error Command failed with exit code 1.
```
