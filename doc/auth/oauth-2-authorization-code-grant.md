
# OAuth 2 Authorization Code Grant



Documentation for accessing and setting credentials for slackAuth.

## Auth Credentials

| Name | Type | Description | Setter |
|  --- | --- | --- | --- |
| oauthClientId | `string` | OAuth 2 Client ID | `oauthClientId` |
| oauthClientSecret | `string` | OAuth 2 Client Secret | `oauthClientSecret` |
| oauthRedirectUri | `string` | OAuth 2 Redirection endpoint or Callback Uri | `oauthRedirectUri` |
| oauthToken | `OauthToken` | Object for storing information about the OAuth token | `oauthToken` |
| oauthScopes | `OauthScope[]` | List of scopes that apply to the OAuth token | `oauthScopes` |
| oauthClockSkew | `number` | Clock skew time in seconds applied while checking the OAuth Token expiry. | `clockSkew` |
| oauthTokenProvider | `(lastOAuthToken: OauthToken \| undefined, authManager: AuthorizationCodeAuthManager) => Promise<OauthToken>` | Registers a callback for oAuth Token Provider used for automatic token fetching/refreshing. | `oauthTokenProvider` |
| oauthOnTokenUpdate | `(token: OauthToken) => void` | Registers a callback for token update event. | `oauthOnTokenUpdate` |



**Note:** Auth credentials can be set using `authorizationCodeAuthCredentials` object in the client.

## Usage Example

### 1\. Client Initialization

You must initialize the client with *OAuth 2.0 Authorization Code Grant* credentials as shown in the following code snippet.

```ts
import { Client, OauthScope } from 'slack-apimatic-sdk-sdk';

const client = new Client({
  authorizationCodeAuthCredentials: {
    oauthClientId: 'OAuthClientId',
    oauthClientSecret: 'OAuthClientSecret',
    oauthRedirectUri: 'OAuthRedirectUri',
    oauthScopes: [
      OauthScope.Admin,
      OauthScope.AdminAppsread
    ]
  },
});
```



Your application must obtain user authorization before it can execute an endpoint call in case this SDK chooses to use *OAuth 2.0 Authorization Code Grant*. This authorization includes the following steps

### 2\. Obtain user consent

To obtain user's consent, you must redirect the user to the authorization page.The `buildAuthorizationUrl()` method creates the URL to the authorization page. You must have initialized the client with scopes for which you need permission to access.

```ts
const authUrl = client.authorizationCodeAuthManager?.buildAuthorizationUrl();
```

### 3\. Handle the OAuth server response

Once the user responds to the consent request, the OAuth 2.0 server responds to your application's access request by redirecting the user to the redirect URI specified set in `Configuration`.

If the user approves the request, the authorization code will be sent as the `code` query string:

```
https://example.com/oauth/callback?code=XXXXXXXXXXXXXXXXXXXXXXXXX
```

If the user does not approve the request, the response contains an `error` query string:

```
https://example.com/oauth/callback?error=access_denied
```

### 4\. Authorize the client using the code

After the server receives the code, it can exchange this for an *access token*. The access token is an object containing information for authorizing client requests and refreshing the token itself.

```ts
try {
  const token = await client.authorizationCodeAuthManager?.fetchToken(authorizationCode);
  if (token) {
    client.withConfiguration({
      authorizationCodeAuthCredentials: {
        ...config.authorizationCodeAuthCredentials,
        oauthToken: token
      }
    });
  }
} catch(error) {
  // handle ApiError or OAuthProviderError if needed
}
```

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OauthScope`](../../doc/models/oauth-scope.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `Admin` | admin |
| `AdminAppsread` | admin.apps:read |
| `AdminAppswrite` | admin.apps:write |
| `AdminConversationsread` | admin.conversations:read |
| `AdminConversationswrite` | admin.conversations:write |
| `AdminInvitesread` | admin.invites:read |
| `AdminInviteswrite` | admin.invites:write |
| `AdminTeamsread` | admin.teams:read |
| `AdminTeamswrite` | admin.teams:write |
| `AdminUsergroupsread` | admin.usergroups:read |
| `AdminUsergroupswrite` | admin.usergroups:write |
| `AdminUsersread` | admin.users:read |
| `AdminUserswrite` | admin.users:write |
| `Authorizationsread` | authorizations:read |
| `Bot` | Bot user scope |
| `Callsread` | calls:read |
| `Callswrite` | calls:write |
| `Channelshistory` | channels:history |
| `Channelsmanage` | channels:manage |
| `Channelsread` | channels:read |
| `Channelswrite` | channels:write |
| `Chatwrite` | chat:write |
| `Chatwritebot` | Author messages as a bot |
| `Chatwriteuser` | Author messages as a user |
| `Conversationshistory` | conversations:history |
| `Conversationsread` | conversations:read |
| `Conversationswrite` | conversations:write |
| `Dndread` | dnd:read |
| `Dndwrite` | dnd:write |
| `Emojiread` | emoji:read |
| `Filesread` | files:read |
| `Fileswriteuser` | files:write:user |
| `Groupshistory` | groups:history |
| `Groupsread` | groups:read |
| `Groupswrite` | groups:write |
| `IdentityBasic` | identity.basic |
| `Imhistory` | im:history |
| `Imread` | im:read |
| `Imwrite` | im:write |
| `Linkswrite` | links:write |
| `Mpimhistory` | mpim:history |
| `Mpimread` | mpim:read |
| `Mpimwrite` | mpim:write |
| `None` | No scope required |
| `Pinsread` | pins:read |
| `Pinswrite` | pins:write |
| `Reactionsread` | reactions:read |
| `Reactionswrite` | reactions:write |
| `Remindersread` | reminders:read |
| `Reminderswrite` | reminders:write |
| `RemoteFilesread` | remote_files:read |
| `RemoteFilesshare` | remote_files:share |
| `RemoteFileswrite` | remote_files:write |
| `Rtmstream` | rtm:stream |
| `Searchread` | search:read |
| `Starsread` | stars:read |
| `Starswrite` | stars:write |
| `Teamread` | team:read |
| `TokensBasic` | tokens.basic |
| `Usergroupsread` | usergroups:read |
| `Usergroupswrite` | usergroups:write |
| `UsersProfileread` | users.profile:read |
| `UsersProfilewrite` | users.profile:write |
| `Usersread` | users:read |
| `UsersreadEmail` | users:read.email |
| `Userswrite` | users:write |
| `WorkflowStepsexecute` | workflow.steps:execute |

### Refreshing the token

An access token may expire after sometime. To extend its lifetime, you must refresh the token.

```ts
try {
  const token = await client.authorizationCodeAuthManager?.refreshToken();
} catch(error) {
  // handle error
}
```

If a token expires, an exception will be thrown before the next endpoint call requiring authentication.

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

```ts
Store the token in session storage or local storage.
```

### Creating a client from a stored token

To authorize a client using a stored access token, just set the access token in Configuration along with the other configuration parameters before creating the client:

```ts
const newClient = client.withConfiguration({
  authorizationCodeAuthCredentials: {
    ...config.authorizationCodeAuthCredentials,
    oauthToken: token
  }
});
```

### Complete example



```ts
import {
  Client,
  OauthScope,
  OauthToken,
} from 'slack-apimatic-sdk-sdk';

// function for storing token to database
async function saveTokenToDatabase(token: OAuthToken) {
  // Code to save the token to the database
}

// function for loading token from database
async function loadTokenFromDatabase(): Promise<OAuthToken | undefined> {
  // Load token from the database and return it (return undefined if no token exists)
  return undefined;
}

// create a new client from configuration
const client = new Client({
  authorizationCodeAuthCredentials: {
    oauthClientId: 'OAuthClientId',
    oauthClientSecret: 'OAuthClientSecret',
    oauthRedirectUri: 'OAuthRedirectUri',
    oauthScopes: [
      OauthScope.Admin,
      OauthScope.AdminAppsread
    ]
  },
});

// obtain access token, needed for client to be authorized
const previousToken = await loadTokenFromDatabase();
if (previousToken) {
  // restore previous access token and update the cloned configuration with the token
  client.withConfiguration({
    authorizationCodeAuthCredentials: {
      ...config.authorizationCodeAuthCredentials,
      oauthToken: previousToken
    }
  });
}
else {
    // redirect user to a page that handles authorization
}
```


