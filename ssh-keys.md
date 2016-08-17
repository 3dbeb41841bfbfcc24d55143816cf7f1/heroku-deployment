# Heroku and SSH Keys


> DEPRECATED: Just as with GitHub, you no longer need to use SSH Keys to securely deploy your code. The HTTPS protocol with a login/password authentication is sufficient and you can use your OSX Keychain to remember your login/password credentials.



## Add SSH-key to Heroku

Very similar to when we setup GitHub, we need to add our ssh-keys to Heroku so that Heroku can know we're authenticated users.

So let's add our ssh-key to Heroku. First, we need to copy our ssh-key:

```bash
cat ~/.ssh/id_rsa.pub | pbcopy
```

Then we need to go to [Heroku](https://www.heroku.com/).

Email > Manage Account > SSH Keys.
