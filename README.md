# fr-bff-iam-adapter

## Usage
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
