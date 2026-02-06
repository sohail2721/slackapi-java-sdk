
# OAuth 2 Authorization Code Grant



Documentation for accessing and setting credentials for slackAuth.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| OAuthClientId | `String` | OAuth 2 Client ID | `oauthClientId` | `getOauthClientId()` |
| OAuthClientSecret | `String` | OAuth 2 Client Secret | `oauthClientSecret` | `getOauthClientSecret()` |
| OAuthRedirectUri | `String` | OAuth 2 Redirection endpoint or Callback Uri | `oauthRedirectUri` | `getOauthRedirectUri()` |
| OAuthToken | `OauthToken` | Object for storing information about the OAuth token | `oauthToken` | `getOauthToken()` |
| OAuthScopes | `List<OauthScope>` | List of scopes that apply to the OAuth token | `oauthScopes` | `getOauthScopes()` |



**Note:** Auth credentials can be set using `authorizationCodeAuth` in the client builder and accessed through `getAuthorizationCodeAuth` method in the client instance.

## Usage Example

### 1\. Client Initialization

You must initialize the client with *OAuth 2.0 Authorization Code Grant* credentials as shown in the following code snippet.

```java
import com.slack.SlackWebApiClient;
import com.slack.authentication.AuthorizationCodeAuthModel;
import com.slack.exceptions.ApiException;
import com.slack.models.OauthScope;
import com.slack.models.OauthToken;
import java.io.IOException;
import java.util.Arrays;

public class Program {
    public static void main(String[] args) {
        SlackWebApiClient client = new SlackWebApiClient.Builder()
            .authorizationCodeAuth(new AuthorizationCodeAuthModel.Builder(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri"
                )
                .oauthScopes(Arrays.asList(
                        OauthScope.ADMIN,
                        OauthScope.ADMIN_APPSREAD
                    ))
                .build())
            .build();
    }
}
```



Your application must obtain user authorization before it can execute an endpoint call in case this SDK chooses to use *OAuth 2.0 Authorization Code Grant*. This authorization includes the following steps

### 2\. Obtain user consent

To obtain user's consent, you must redirect the user to the authorization page.The `buildAuthorizationUrl()` method creates the URL to the authorization page. You must have initialized the client with scopes for which you need permission to access.

```java
String authUrl = client.getAuthorizationCodeAuth().buildAuthorizationUrl(); // build auth url
httpServletResponse.sendRedirect(authUrl); // show user the auth page in a browser or by redirection
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

```java
try {
    String authorizationCode = "Replace me with actual authorization code";
    OAuthToken token = client.getAuthorizationCodeAuth().fetchToken(authorizationCode);
    // re-instantiate the client with oauth token
    client = client.newBuilder()
            .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                    .oauthToken(token)
                    .build())
            .build();
} catch (Throwable e) {
    // TODO Handle exception
}
```

### Scopes

Scopes enable your application to only request access to the resources it needs while enabling users to control the amount of access they grant to your application. Available scopes are defined in the [`OauthScope`](../../doc/models/oauth-scope.md) enumeration.

| Scope Name | Description |
|  --- | --- |
| `ADMIN` | admin |
| `ADMIN_APPSREAD` | admin.apps:read |
| `ADMIN_APPSWRITE` | admin.apps:write |
| `ADMIN_CONVERSATIONSREAD` | admin.conversations:read |
| `ADMIN_CONVERSATIONSWRITE` | admin.conversations:write |
| `ADMIN_INVITESREAD` | admin.invites:read |
| `ADMIN_INVITESWRITE` | admin.invites:write |
| `ADMIN_TEAMSREAD` | admin.teams:read |
| `ADMIN_TEAMSWRITE` | admin.teams:write |
| `ADMIN_USERGROUPSREAD` | admin.usergroups:read |
| `ADMIN_USERGROUPSWRITE` | admin.usergroups:write |
| `ADMIN_USERSREAD` | admin.users:read |
| `ADMIN_USERSWRITE` | admin.users:write |
| `AUTHORIZATIONSREAD` | authorizations:read |
| `BOT` | Bot user scope |
| `CALLSREAD` | calls:read |
| `CALLSWRITE` | calls:write |
| `CHANNELSHISTORY` | channels:history |
| `CHANNELSMANAGE` | channels:manage |
| `CHANNELSREAD` | channels:read |
| `CHANNELSWRITE` | channels:write |
| `CHATWRITE` | chat:write |
| `CHATWRITEBOT` | Author messages as a bot |
| `CHATWRITEUSER` | Author messages as a user |
| `CONVERSATIONSHISTORY` | conversations:history |
| `CONVERSATIONSREAD` | conversations:read |
| `CONVERSATIONSWRITE` | conversations:write |
| `DNDREAD` | dnd:read |
| `DNDWRITE` | dnd:write |
| `EMOJIREAD` | emoji:read |
| `FILESREAD` | files:read |
| `FILESWRITEUSER` | files:write:user |
| `GROUPSHISTORY` | groups:history |
| `GROUPSREAD` | groups:read |
| `GROUPSWRITE` | groups:write |
| `IDENTITY_BASIC` | identity.basic |
| `IMHISTORY` | im:history |
| `IMREAD` | im:read |
| `IMWRITE` | im:write |
| `LINKSWRITE` | links:write |
| `MPIMHISTORY` | mpim:history |
| `MPIMREAD` | mpim:read |
| `MPIMWRITE` | mpim:write |
| `NONE` | No scope required |
| `PINSREAD` | pins:read |
| `PINSWRITE` | pins:write |
| `REACTIONSREAD` | reactions:read |
| `REACTIONSWRITE` | reactions:write |
| `REMINDERSREAD` | reminders:read |
| `REMINDERSWRITE` | reminders:write |
| `REMOTE_FILESREAD` | remote_files:read |
| `REMOTE_FILESSHARE` | remote_files:share |
| `REMOTE_FILESWRITE` | remote_files:write |
| `RTMSTREAM` | rtm:stream |
| `SEARCHREAD` | search:read |
| `STARSREAD` | stars:read |
| `STARSWRITE` | stars:write |
| `TEAMREAD` | team:read |
| `TOKENS_BASIC` | tokens.basic |
| `USERGROUPSREAD` | usergroups:read |
| `USERGROUPSWRITE` | usergroups:write |
| `USERS_PROFILEREAD` | users.profile:read |
| `USERS_PROFILEWRITE` | users.profile:write |
| `USERSREAD` | users:read |
| `USERSREAD_EMAIL` | users:read.email |
| `USERSWRITE` | users:write |
| `WORKFLOW_STEPSEXECUTE` | workflow.steps:execute |

### Refreshing the token

An access token may expire after sometime. To extend its lifetime, you must refresh the token.

```java
if (client.getAuthorizationCodeAuth().isTokenExpired()) {
    try {
        OAuthToken token = client.getAuthorizationCodeAuth().refreshToken();
        // re-instantiate the client with oauth token
        client = client.newBuilder()
                .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                        .oauthToken(token)
                        .build())
                .build();
    } catch (Throwable e) {
        // TODO Handle exception
    }
}
```

If a token expires, an exception will be thrown before the next endpoint call requiring authentication.

### Storing an access token for reuse

It is recommended that you store the access token for reuse.

```java
// store token
httpSession.setAttribute("access_token", client.getAuthorizationCodeAuth().getOauthToken());
```

### Creating a client from a stored token

To authorize a client using a stored access token, just set the access token in Configuration along with the other configuration parameters before creating the client:

```java
// load token later...
OauthToken token = (OauthToken) httpSession.getAttribute("access_token");

// re-instantiate the client with oauth token
client = client.newBuilder()
        .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                .oauthToken(token)
                .build())
        .build();
```

### Complete example



In this example that uses the Spring framework and an application using spring framework can be easily set up through [`spring initializr`](https://start.spring.io/), the `/callapi` route will first check if an access token is available for the user. If one is not set,
it redirects the user to `/authcallback` route which will obtain an access token and redirect the user back to the `/callapi` route.
Now that an access token is set, `/callapi` route can use the client to make authorized calls to the server.

#### `MainController.java`

```java
package com.example;

import com.slack.SlackWebApiClient;
import com.slack.authentication.AuthorizationCodeAuthModel;
import com.slack.http.client.LoggingConfiguration.Level;
import com.slack.models.OauthScope;
import com.slack.models.OauthToken;
import jakarta.servlet.http.HttpServletResponse;
import jakarta.servlet.http.HttpSession;
import java.util.Arrays;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;
import org.springframework.web.bind.annotation.RequestParam;
import org.springframework.web.bind.annotation.RestController;

@RestController
@RequestMapping("/")
public class MainController {
    private SlackWebApiClient client;

    public MainController() {
        client = new SlackWebApiClient.Builder()
            .authorizationCodeAuth(new AuthorizationCodeAuthModel.Builder(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri"
                )
                .oauthScopes(Arrays.asList(
                        OauthScope.ADMIN,
                        OauthScope.ADMIN_APPSREAD
                    ))
                .build())
            .build();
    }

    @RequestMapping(value = "/callapi", method = RequestMethod.GET, produces = "application/json")
    public String callApi(HttpSession session, HttpServletResponse response) throws Throwable {
        // redirect if access token is not set
        if (session.getAttribute("access_token") == null) {
            response.sendRedirect("authcallback");
            return null;
        }

        synchronized (client) {
            client = client.newBuilder()
                    .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                            .oauthToken((OauthToken) session.getAttribute("access_token"))
                            .build())
                    .build();

            // refresh the token if it is expired
            if(client.getAuthorizationCodeAuth().isTokenExpired()) {
                try {
                    OauthToken token = client.getAuthorizationCodeAuth().refreshToken();
                    session.setAttribute("access_token", token);
                    // re-instantiate the client with oauth token
                    client = client.newBuilder()
                            .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                                    .oauthToken(token)
                                    .build())
                            .build();
                } catch (Throwable e) {
                    // TODO Handle exception
                }
            }

            // now you can use client to make endpoint calls
            // client will automatically refresh the token when it expires
            return "someView";
        }
    }

    @RequestMapping(value = "/authcallback", method = RequestMethod.GET)
    public void authcallback(HttpSession session, @RequestParam(required = false) String code,
            HttpServletResponse response) throws Throwable {
        if (code == null) {
            String authUrl;
            
            synchronized (client) {
                authUrl = client.getAuthorizationCodeAuth().buildAuthorizationUrl();
            }
            
            // if authorization code is absent, redirect to authorization page
            response.sendRedirect(authUrl);
        } else {
            OauthToken token;
            
            synchronized (client) {
                token = client.getAuthorizationCodeAuth().fetchToken(code);
                // re-instantiate the client with oauth token
                client = client.newBuilder()
                        .authorizationCodeAuth(client.getAuthorizationCodeAuthModel().toBuilder()
                                .oauthToken(token)
                                .build())
                        .build();
            }
            
            session.setAttribute("access_token", token);
            response.sendRedirect("callapi");
        }
    }
}
```


