## Checking the token

The authentication service has a path */auth/users* which lists the details of every user in the database.
Now, we do not want anyone to get it, we only want the admin to access this information.
So, type (make sure you type it if you have not stored the token anywhere) the following command and paste it in the terminal and make sure to add the token you got in previous step into it.
`
    curl -X POST -H "x-access-token: <YOUR_TOKEN>" \
    http://localhost:10000/auth/users
`

This should give a 403 status code.

Now let us repeat the previous step for admin:
`
    curl -X POST -H "Content-Type: application/json" \
    -d '{"id": "admin", "password": "admin"}' \
    http://localhost:10000/auth/signin
`{{execute}}

Now if we repeat this step with the token of admin, it should work.
`
    curl -X POST -H "x-access-token: <YOUR_TOKEN>" \
    http://localhost:10000/auth/users
`
