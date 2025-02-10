# Nextjs 

Nextjs is a fullstack framework

## App Router

```file

layout.js
template.js
error.js
loading.js
not-found.js
page.js

```

equilvalent to 

```jsx
<Layout>
<Template>
<ErrorBoundary fallback={<Error/>}>
<Suspense fallback={<Loading/>}>
<ErrorBoundary fallback={<NotFound/>}>
<Page/>
</ErrorBoundary>
</Suspense>
</ErrorBoundary>
</Template>
</Layout>

```

> Folder name is the route

- page.tsx - client file
- route.tsx - server file

Do not create route.ts and page.js in same folder

> `global-error.js` at root will a wrap whole application

> for middleware create middleware.js at root level

### Route Group
- (folderName) - it will not include in url

- _myFolderName - foldername start with _ is a private folder
- [folderName] - Dynamic Route - eg: [id] , [slug]
- [...folderName] - catch all subsequent segment
- [[...folderName]] - optional catch all
- Parallel Routes

  ```bash
  > app
    > @analytics
    > @team 
  ```



  ## Get productId

  > product
    [productId]

 ### Way-1
 ```js
 const { productId } = useParams();
 ```
 ### Way-2
 ```js
 function MyComponent({params}:{params:{productId:string}}){
    const { productId } = params
 }
 ```   

 

## Server Component vs Client Component

- Server Component - run at server and send html as a response(console.log() result is not seen here in client browser)
- Client Component - run at client browser (console.log() is seen in client browser)