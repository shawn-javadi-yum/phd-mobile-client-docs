- Would be nice patterns
    - Git
      - Commits should be descriptive, and explain changes contained in them
      - PRs should be kept small to make for an easier review process
    - React
      - React components should be as dumb as possible
        - Logic should be abstracted away to redux/containers/util functions/api/etc
          - Good:
            - TBD
          - Bad:
            - TBD
      - Avoid using index.js for React component names
        - This will help avoid having 10+ index.js tabs open in the editor
        - It will also help make the components searchable using fuzzy search
    - Code
      - Use meaningful/descriptive names
        - Bad:
          - ```javascript
             ps.map(p => {})
        - Good:
          - ```javascript
             products.map(product => {})
      - Functions/classes should ideally have one responsibility.
        - Single responsibility functions are easier to reuse/test/read/refactor
        - Use functional decomposition to abstract away logic
        - Bad:
          - ```javascript
              function renderRedProducts(products) {
                  const filteredProducts = products.map(...)
                      .filter(...)
                      .someOtherFunction(id)
                  .
                  .
                  .
                  .
                   // Some more data mapping/logic ^
                  return filteredProducts.map(product => <SomeElement />)
              }
        - Good:
          - ```javascript
            - function getRedProducts(products) {
                 const filteredProducts =  products.map(...)
                      .filter(...)
                      .someOtherFunction(id)
                  .
                  .
                  .
                  .
                   // Some more data mapping/logic ^

                 return filteredProducts
              }

              function renderRedProducts(products) {
                  const productsToRender = getRedProducts(products)
                  return productsToRender.map(product => <SomeElement />)
              }

      - Encapsulate boolean expressions for readability
        - Bad:
          - ```javascript
            if (someArray.length > 2 && someArray[0].id === "someId") {
                ...
            }
        - Good:
          - ```javascript
            const isSomeCondition = someArray.length > 2 && someArray[0].id === "someId";

            if (isSomeCondition) {
                ...
            }
      - Prefer using native JS features over outside sources/lodash
        - Modern JS Array/Number/String prototype functions are faster and generally more reliable
        - This is specially true on the mobile side since we don't have to worry about browser compatibility 
        - If we do decide to add an outside library it should be voted on as a team first before being added
        - On flip side no need to reinvent the wheel from scratch if an outside library can save time/provide an already tested/stable solution
      - Function names should explain what they do
         - Bad:
          - ```javascript
              function filterItems(items) {...} // when i pass items here what's actually being filtered out?
        - Good:
          - ```javascript
            - function filterRedItems(items) {...}
      - Variable names should explain what's been done to them/what they contain
        - Bad:
          - ```javascript
              const reducedItems = items.reduce(...) // What did we reduce to?
        - Good:
          - ```javascript
            - const blueItems = items.reduce(...)
      - Avoid long chains of functions/deeply nested functions
        - this example is obviously primitive and simplified/exaggerated to showcase the concept
        - This is obviously only a problem if there is a lot going inside the functions you are chaining. no need to seperate one liners.
        - Bad:
          - ```javascript
              return products.map(product => {
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  return someModifier
              })
              .map(modifier => {
                  ...
                  ...
                  ...
                  ...
                  ...
                  return goodModifiers
              })
              .reduce((someGoodModifiers, modifier) => {
                  ...
                  ...
                  ...
                  ...
                  ...
              }, []).length === 0 || []
        - Good:
          - ```javascript
            - const modifiers = products.map(product => {
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  ...
                  return someModifier
              })

              const goodModifiers =  modifiers.map(modifier => {
                  ...
                  ...
                  ...
                  ...
                  ...
                  return goodModifiers
              })

              const modifiersToCheck = reduce((someGoodModifiers, modifier) => {
                  ...
                  ...
                  ...
                  ...
                  ...
              }, [])

              return modifiersToCheck.length === 0 || []
