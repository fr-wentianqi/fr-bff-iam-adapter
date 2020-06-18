# fr-bff-iam-adapter

## Usage
- In SPA
```ts
const App = () => {
  const yourCurrentPath = window.location.pathname
  const bffAuthoritiesEndpoint = "bffPath/authorities"
  const bffAuthenticateEndpoint = `bffPath/authenticate?originalURL=${yourCurrentPath}`
  const { result } = await request(bffAuthoritiesEndpoint)
  
  if (result) {
    // alreayd logged in then continue your dataflow in SPA
  } else {
    window.location.replace(authEndpoint)
  }
  
  return (...);
}
```

- In BFF
```ts
// router of your app
import iamAdapter from "fr-bff-iam-adapter";

const iamAdapterConfig = {
  basePath: BASE_PATH,
  authEndpoint: AUTH_ENDPOINT,
  tokenEndpoint: TOKEN_ENDPOINT,
  clientID: CLIENT_ID,
  clientSecret: CLIENT_SECRET,
  appHost: APP_HOST,
  whiltelist: ["/status"],
}

router.use(
  BASE_PATH,
  iamAdapter()
  router.use(routerA),
  router.use(routerB),
  ...
)
```
