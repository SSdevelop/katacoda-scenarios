## Authorization

We give stores the ability to change their menu price and there open/closed status.

Of course we do not want any user to change those informaiton.
The only people who should be able to do that are admin and the owner of the store.
In order to achieve this, JWT is implemented through authentication microservice.

In the terminal run:
`
    curl -X POST -H "Content-Type: application/json" \
    -d '{"id": "ecs_ny", "password": "iloveny"}' \
    http://localhost:10000/auth/signin
`{{execute}}

This will return a token, copy or save that token.