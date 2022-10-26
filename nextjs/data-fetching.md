# Data fetching in Next.js

### Data fetching Next.js 13+ (app dir)
``` js
// app/page.js
import { use } from 'react';

async function getData() {
  // get data each request
  const res = await fetch(URL);

  // get data SSG (getStaticProps)
  const res = await fetch(URL, {cache: 'force-cache'})

  // get data SSR (getServerSideProps)
  const name = await fetch(URL, {cache: 'no-store'})

  // get data SSG with revalidate after 10[s]
  const name = await fetch(URL, {cache: revalidate: 10});

  const name = await res.json();
  return name;
}

export default function Page() {
    const name = use(getData());
    return <div>{name}</div>
}
```

### Data fetching up to Next.js 12

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

