# CSS styles in Next.js

### Styled-componets
```
pnpm install --save-dev styled-components

// update.next.config.js
module.exports = {
  compiler: {
    // see https://styled-components.com/docs/tooling#babel-plugin for more info on the options.
    styledComponents: true
  }
}
```

```jsx

import styled from 'styled-components'

// Styled component
const Main = styled.main`
	background-color: black;
`

// Usage in render
<Main>My content...</Main>
`
```
