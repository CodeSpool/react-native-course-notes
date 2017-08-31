## Note on ES7 class syntax

The syntax:

```JavaScript
class ResultsContainer extends React.Component {
  static propTypes = {
    someProp: PropTypes.bool.isRequired,
    anotherProp: PropTypes.func.isRequired,
  }
  state = {
    ...
  }
  componentDidMount () {
    ...
  }
  fetchUsersFollowers = (username) => {
    ...
  }
  render () {
    return (
      ...
    )
  }
}
```

Advantages:
- cleaner syntax
- arrow function is bound to `this` automatically
- prop types and default props inside the component

#### Note:
If using `standard` linter, install `babel-eslint` package where `standard` is installed (globally or locally) and add this to `package.json`:
```
"standard": {
  "parser": "babel-eslint"
}
```

## Deprecated
The `Navigator` and `NavigationExperimental` components are deprecated.

Use `react-navigation` or `react-native-navigation` instead