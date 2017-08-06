## Difference from react

- different UX, UI
- no URL

### Routes
- think of routes as in terms of layers rather than URL to UI mappings
  - layers are ordered in stack format (array)
  - transitions push or pop routes to that array
- different route transitions are called _scene configurations_
  - different platforms have different transitions

### Native elements
There are no DOM elements like ```<div>```, ```<a>``` or ```<span>```.
If looking for a specific native component, odds are it has already been implemented ba React Native Core or the community.

#### Most Commonly used components:
```<View>``` 
- a fundamental component
- Equivalent to ```<div>``` in browser

```<Text>```
- displays text
- you can't render any text that isn't wrapped in ```<Text>``` component.

```<Image>```
- for displaying any type of image
- any source - network, static, temp, local (camera roll..)

```<TextInput>```
- get input from keyboard
- ```onChangeText``` prop called on change

```<TouchableHighlight><TouchableOpacity><TouchableWithoutFeedback>```
- most components are not able to handle ```onPress``` prop and have to be wrapped in one of these components
- avoid ```<TouchableWithoutFeedback>``` (bad UX)

```<ActivityIndicator>```
- default loading indicator
- change default styling based on platform

```<ScrollView>```
- overflow content is not visible in regular ```View```
- all content is always rendered
- not suitable for larger lists

```<ListView>```
- more performant for longer lists than ```<ScrollView>```
- only renders elements currently showing on the screen

## Hello world app

- Platform specific code
  - Any filename named ```*.android.js``` or ```*.ios.js``` will be rendered only for the target platform. 
  - ```<View>``` component automatically maps to platform-specific equivalent (UiView on IOS, Android.View on android).

- All styles in react native are written in JavaScript - no CSS:
  - ```StyleSheet.create({......})```

- ```AppRegistry```
  - initialize the RN project
  - call once in the root of the project
