# Password

### [~$ cd ..](../)

Author [Renaud11232](https://renaud11232.github.io/)

For this challenge, we were given a sheet of paper with some story about the challenge with `telegram://CSCBEBot` written on it.

![intro password](assets/intro_password.png)

So we installed `Telegram` and joined the bot and were greeted with :

![start](assets/start.png)

So one of the first things we tried was just `/flag`. You never know :).

![flag not admin](assets/flag_notadmin.png)

Then we tried logging in as the admin :

![login admin](assets/login_admin.png)

Sadly, but expectedly it didn't work.
We also tried some very crude buffer overflows.

![overflow](assets/buffer.png)

SQL injections :

![sql](assets/sql_inject.png)

Then we tried logging in as `*` to see what would happen.

![star](assets/star.png)

We were onto something. We tried logging in as `admin*`, sadly there was still more than 1 result, then we tried `/login b*`:

![login b star](assets/ldap.png)

Now from here we were pretty sure we were talking to a bot with an `LDAP` injection vulnerability. The only missing piece was to know how the requests were made.

And after a bit of tinkering we just tried with `**`

![crash](assets/oopsie.png)

So we knew how our input was concatenated into the filter :

```python
"(&(objectClass=posixAccount)(uid=%s))" % (name)
```

`&` is a `and`. So one way of logging in as the admin was to filter `posixAccount`s `all` of them then only filter the `admin` one:

```
(&(objectClass=posixAccount)(uid=*)(uid=admin))
```
![ldap injection](assets/flag_admin.png)

DONE
