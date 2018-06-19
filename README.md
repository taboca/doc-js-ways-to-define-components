# This is part of the "Struggling with JavaScript" aka doc-js book

* https://leanpub.com/doc-js
* If you want to contribute to the book or join me as a coauthor pool, please get in contact mgalli at mgalli dot com subject "doc-js book"

# From a higher level, smart vs dumb components

According to Vivek Nayya [Vivek 2017](https://medium.com/netscape/component-state-vs-redux-store-1eb0c929277) developers should be familiar with React's main kinds of comopnents: smart and dumb ones.

* The dumb kind are the simple ones, with no logic and whose purpose is to provide presentation transformation only.

* The smart kind may involve logic.  

The differentiation relates to how they deal with states (and this may relate to dependency to other logic from other parts of a system). According to Vivek, if a component holds state, then it's smart.  

However, in the React way of doing things, you don't have to decide between smart and dumb; in fact most of your code will eventually grow with smart and dumb counterparts alongside. What you do is to keep their afairs in order as the smart ones can deal with state and calls the simplified ones for rendering:

The following example is referred as a [container](https://gist.github.com/vivek12345/1cb3787185402df040a20edc783890c0#file-productscontainer-js):

```
import React, { Component } from 'react';
import Product from './Product';

export default class ProductsContainer extends Component {
  constructor(props) {
    super(props);
    this.state = {
      products: [
        'Red Saree',
        'Blue Saree',
        'Green Saree'
      ]
    }
  }
  renderProducts() {
    return this.state.products.map((product) => {
      return <Product name={product} />;
    });
  }
  render() {
    return (
      <div className='products-container'>
        {this.renderProducts()}
      </div>
    );
  }
}

```

Notice that the above "renderProducts" function will return a tag, <Product />, which can be implemented as a simple/dumb component - also source from [Vivek](https://gist.github.com/vivek12345/59af492fdf192ccb815461f243c198f3#file-product-js)

```
import React, { Component } from 'react';

export default class Product extends Component {
  render() {
    return (
      <div className='product'>
        {this.props.name}
      </div>
    );
  }
}
```


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

## Any more?

According to Cory House [2016 Cory]:

```
"Enforced Best Practices Stateless functional components are useful for dumb/presentational components. Presentational components focus on the UI rather than behavior, so it’s important to avoid using state in presentational components. "
```

[2016 Cory](https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc)

Cory also asks us to have the state to be managed at a higher level in the hierarchy, at container level components or via Flux/Redux.

## So, avoiding the temptation of adding state and logic to a presentational component

According to Cory, "it’s always tempting to add state to a presentational component when you’re in a hurry".

## Moving on towards functional components  

According to Cory House, [2016 Cory] there are 9 wins to look at when using functional components:

[2016 Cory](https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc)



## Related

# https://60devs.com/pure-component-in-react.html

* // Stateless components https://hackernoon.com/writing-clean-and-concise-react-components-by-making-full-use-of-es6-7-features-and-the-container-4ba0473b7b01

* // Consier the article for these different ways // https://stackoverflow.com/questions/44074315/react-create-class-confusion-with-extends-components

* /Users/taboca/Desktop/all/000_atividades/290_learning_react_native_redux/test-app-react-redux-native-app
