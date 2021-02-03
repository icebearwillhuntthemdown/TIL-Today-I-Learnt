# Converting to Typescript
1. touch tsconfig.json in the root
2. `npm run dev`  => Next.js populates tsconfig.json 

## Pre-rendering methods in Typescript
- `export const getStaticProps: GetStaticProps = async (context) => {}`
- `export const getStaticPaths: GetStaticPaths = async () => {}`
- `export const getServerSideProps: GetServerSideProps = async (context) => {}`
