# Custom Link with Apollo (GraphQL)

### 01/27/2019

You can use a custom Link with Apollo to set up custom urls or interceptor like functionality on GraphQL requests. But you may notice that if you try to implement a link with a custom graphql url and you are using apollo-boost, this doesn't work and it defaults the url to `localhost:5000/graphql`. 

Feat not, we can use the ApolloClient from `apollo-client` instead! This comes expecially in handy if you are using a feature like `devise_token_auth` token refresh per request.

In your frontend, you should define your ApolloClient, but make sure to import it from `apollo-client`.

```javascript
import React from 'react';
import ApolloClient from 'apollo-client'
import { createHttpLink } from 'apollo-link-http';
import { InMemoryCache } from 'apollo-cache-inmemory';
import axios from 'axios';

const customFetch = () => axios({
  method: 'POST',
  url: SOME_URL,
  headers: {},
  data: {}
}).then(response => ({
  text: () => Promise.resolve(JSON.stringify(response.data)),
  status: response.status
}))  // ProTip: If you use axios here, your request needs to `then` the response into `fetch` format

const link = createHttpLink({
  uri: `${YOUR_GRAPHQL_SERVER}/graphql`,
  fetch: customFetch
})

const client = new ApolloClient({
  link,
  cache: new InMemoryCache(),
})

function Home() {
  return (
    <ApolloClient client={client}>
      {
        // ...
      }
    </ApolloClient>
  );
}

export default Home;
```


Tags: JavaScript, React, Apollo, GraphQL
