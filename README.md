### React-Query Basics

-   ### Client State vs. Server State

    -   #### Client State
        -   information relevant to the browser session
        -   ex.) user's chosen language or light/dark theme
    -   #### Server State
        -   information stored on the server needed to render Components on multiple Clients
        -   ex.) blog post data from the database

-   ### maintains a cache of server data on the Client

    -   React Query cache sits between the client and the server
    -   So when API/Data queries are sent, it first checks is that data available in the React Query cache

-   ### React Query Manages Data

    -   Indicate when to update React Query cache with new data from server

        -   imperatively: invalidate data and refetch
        -   declaratively: configure how (ex. window focus) & when to trigger a re-fetch

                Cache Example

                key: 'blog-posts'
                data: [
                    1: {
                        title: 'React Query',
                        tagLine: 'What is this thing?'
                    },
                    2: {
                        title: 'React Query Mutations',
                        tagLine: 'Not just for ninja turtles'
                    }
                ]
                staleTime: 30 seconds

-   ### Maintains Loading and Error states for every query to the server
-   ### Gives you tools to fetch data in pieces, just when it's needed by the user for pagination and infinite scroll
-   ### Can pre-fetch data if you anticipate the user is going to need it
    -   pre-fetch the data, put it in the cache and then when the user needs it, the data is immediately available
-   ### Can handle mutations or updates of data on the server
-   ### React Queries are identified by a key so that they can be managed and avoid duplicate server requests
-   ### Can manage retries if you get an error from the server
-   ### provides callbacks if a request is successful or an error and take further action in either case
