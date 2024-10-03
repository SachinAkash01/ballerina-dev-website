---
title: 'Better security'
description: 'Ballerina offers robust security features like encryption, authentication, and authorization, essential for businesses handling sensitive data. It also ensures query integrity with depth validation and complexity analysis.'
url: 'https://github.com/ballerina-guides/integration-samples/blob/graphql-security/graphql-social-media-service/service.bal'
---
```
listener graphql:Listener graphqlListener = new (9090,
    secureSocket = {
        key: {
            certFile: "../resource/path/to/public.crt",
            keyFile: "../resource/path/to/private.key"
        }
    }
);

@graphql:ServiceConfig {
    auth: [
        {
            oauth2IntrospectionConfig: {
                url: "https://mytoken.endpoint/oauth2/introspect",
                tokenTypeHint: "access_token",
                scopeKey: "scp",
                clientConfig: {
                    customHeaders: {"Authorization": "Basic YWRtaW46YWRtaW4="},
                    secureSocket: {
                        cert: "../resource/path/to/public.crt"
                    }
                }
            },
            scopes: ["admin"]
        }
    ],
    // Validate the query depth.
    maxQueryDepth: 5,
    queryComplexityConfig: {
        // Limit the complexity of the query being executed.
        maxComplexity: 50
    }
}
service /graphql on graphqlListener {

    @graphql:ResourceConfig {
        // Define complexity for the field.
        complexity: 10
    }
    resource function get users() returns User[] {
        // ...
    }
    remote function createPost(graphql:Context context, NewPost newPost) returns Post|error {
        // ...
    }
}

public type NewPost readonly & record {|
    // Validate user inputs.
    @constraint:String {
        maxLength: 25,
        minLength: 5
    }
    string title;
|};
```
