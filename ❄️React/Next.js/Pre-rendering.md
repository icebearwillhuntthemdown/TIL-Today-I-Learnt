# Pre-rendering
- Next.js has pre-rendered the app into static HTML, allowing users to see the UI without running JS. 
- Next.js pre-renders every page by default.
- React.js doens't to pre-rendering so you can't see the app when JS is disabled.

## Pre-rendering Process
1. Initial load: pre-rendered HTML is displayed
2. Hydration
    - React components are initialised and the app becomes interactive
    - If the app has interactive components they'll be active after JS loads

* Hydration: when a page is loaded by the browser, its JS code runs and makes the page fully interactive.

## Static Generation : `getStaticProps()`
- `export const getStaticProps: GetStaticProps = async (context) => {}`
- runs at build time on the server side
- you can fetch external data in this function and send it as props to the page

## Static Generation with Dynamic Routes : `getStaticPaths()`
- `export const getStaticPaths: GetStaticPaths = async () => {}`
- used to return an array of possible values for dynamic routing 
    + a must when using `getStaticProps()` on a page using dynamic routing
    + cannot be used with `getServerSideProps()`
- runs at build time on the server side
- only allowed in a page: can only be exported from a page

## Server-Side Rendering : `getServerSideProps()`
- `export const getServerSideProps: GetServerSideProps = async (context) => {}`
- called at request time
- `context`: contains request specific parameters

## Hybrid Rendering
- Statically generate parts of the page
- Populate the remaining parts using external data fetched at request time
