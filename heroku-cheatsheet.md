# Heroku Cheatsheet

## General Commands

```bash
heroku help                         # show this usage
heroku version                      # show the version
heroku apps                         # list your apps
```

## Managing Your App

```bash
heroku create [<name>]              # create a new app
git push heroku master              # deploying the latest version of your app
heroku info                         # show app info, like web url and git repo
heroku releases                     # show the releases of your app
heroku open                         # open the app in a web browser
heroku rename <newname>             # rename the app
heroku restart                      # restart app servers
heroku logs                         # fetch recent log output for debugging
heroku config                       # display the app's config vars (environment)
heroku config:add key=val [...]     # add one or more config vars
heroku config:remove key [...]      # remove one or more config vars
heroku config:clear                 # clear user-set vars and reset to default
heroku addons                       # list installed addons
heroku addons:services              # list all available addons
heroku addons:add name [key=value]  # install addon (with zero or more config vars)
heroku addons:remove name           # uninstall an addons
heroku addons:clear                 # uninstall all addons
heroku destroy                      # destroy the app permanently
```

## MongoLab

```bash
heroku addons:create mongolab:sandbox  # Add a mongolab sandbox database
heroku config
heroku addons
```

### JavaScript code for Connecting to either a MongoLab or Localhost Database

```javascript
// Connect to database
if (process.env.MONGODB_URI) {
  mongoose.connect(process.env.MONGODB_URI);
}
else {
  mongoose.connect('mongodb://localhost/express-movies');
}
mongoose.connection.on('error', function(err) {
  console.error('MongoDB connection error: ' + err);
  process.exit(-1);
  }
);
mongoose.connection.once('open', function() {
  console.log("Mongoose has connected to MongoDB!");
});
```

### Running a seeds.js file on Heroku

```bash
heroku run node seeds.js
```
