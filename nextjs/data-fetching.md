# Data fetching in NMEt.js

### SSR: server-sider rendering
* runs on server only
* executed on each request
* implement async function getServerSideProps(context)

```js
export async function getServerSideProps() 
  const res = await fetch(`https://.../data`)
  const data = await res.json()

  // Passing data to the page via props
  return { props: { data } }
}
```

### SSG: static-side generation
* runs on server only
* pre-rendered at build time
* implement async function gestStaticProps(context) 
```js
export async function getStaticProps(context) {
  return { props: {} }
}
```
### CSR: client-side rendering
* runs on client using useEffect hook or (recommended) SWR hook
```js
// using swr
import useSWR from 'swr'
const fetcher = (...args) => fetch(...args).then((res) => res.json())

function Component() {
  const {data,error} = useSWR('/api/profile-data', fetcher)

  if (error) return <div>Cannot load...</div>
  if (!data) return <div>Loading...</div>
  return (<div>{data.message}</div>)
}
```

* run on client 
###  Dynamic Routing
* runs during build
* if using SSG and dynamic routes, paths needs to be rerender
* implement getSTaticPaths()
```js
return {
paths: [{params: {id: '1'}}, {params: {id: '2'}}],
fallback: false, // true or blocking
}
```


###  ISR: Incremental Static Regenration
* alows to create or update static pages after you built site
* getStaticProps needs to return revalidat: 10 // in seconds
* allows to prerender at build time static paths and 
```
// getStaticPaths
return {paths, fallback: 'blocking'} // server renders non-existing paths on demand
```
More: https://nextjs.org/docs/basic-features/data-fetching/incremental-static-regeneration

