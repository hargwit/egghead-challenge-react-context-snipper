# React context snippet

My entry to the egghead VS Code Snippet Communnity Challenge.

By using the prefix `context`, you will be given the template for the React context pattern. 
This template will provide you with a `Context`, a `Provider` and a custom hook to safely access the context.

An example result of the template:

```
import React, { createContext, useContext } from 'react'
import PropTypes from 'prop-types'

const ExampleContext = createContext(null)

function ExampleProvider({ exampleProp, children }) {
    // cursor ends here

    return (
        <ExampleContext.Provider value={exampleProp}>
            {children}
        </ExampleContext.Provider>
    )
}

ExampleProvider.propTypes = {
    exampleProp: PropTypes.number,
    children: PropTypes.node.isRequired,
}

const useExample = () => {
    const contextValue = useContext(ExampleContext)

    if (!contextValue) {
        throw new Error('useExample must be used within a ExampleProvider.')
    }

    return contextValue
}

export { ExampleProvider, useExample }
```
