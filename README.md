# Mess about the ways to define components 

According to SHubham Khatri [2017 StackOverflow], there is a functional component approach, that can be used when your component only takes in props and renders the result directly:

```
const Main = () => { 
   return(<h1>my title</h1>)
}
```

However, there is also the ES6 class based approach, that can be used when the React component has more functionality and handles states:

```
class Main extends React.Component {
   render(){ return(<h1>something</h1>}
}
```

[2017 Stack Overflow](https://stackoverflow.com/questions/44074315/react-create-class-confusion-with-extends-components)

## What's next here? 

* https://stackoverflow.com/questions/36097965/react-when-to-use-es6-class-based-components-vs-functional-es6-components

According to Jeff Cousins [Cousins 2016], the decision to go with functional is when you can have a component that is limited to using props, as external data, and it simpy produces output via the render – in a pure function fashion. (depends:pure-functions) 

The other kinds of components are the ones that have internal states or other internal functionality.  

[Cousins 2016](https://stackoverflow.com/questions/36097965/react-when-to-use-es6-class-based-components-vs-functional-es6-components) 

## Whats's next? 

According to Cory House, there are 9 wins to look at when using functional components: 

* https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc

## Related 

# https://60devs.com/pure-component-in-react.html

* // Stateless components https://hackernoon.com/writing-clean-and-concise-react-components-by-making-full-use-of-es6-7-features-and-the-container-4ba0473b7b01

* // Consier the article for these different ways // https://stackoverflow.com/questions/44074315/react-create-class-confusion-with-extends-components

* /Users/taboca/Desktop/all/000_atividades/290_learning_react_native_redux/test-app-react-redux-native-app
