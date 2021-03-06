

======================
Git Branch Management
======================

```
$ git branch --list
  * master
  version1
  version2
  version3
  version4
  version5
  version6

git checkout <branch>
git branch <new-branch>
git branch -d <branch>

git status
git add -A
git status
git commit -m "."
```

=================
Heroku Toolbelt
=================

```
heroku apps
heroku logs --app pnguyen-gumball
heroku pg:psql
heroku pg:psql --app pnguyen-gumball
```


======================
MongoDB / MongoLabs
======================

```
  https://devcenter.heroku.com/articles/mongolab
  http://docs.mongolab.com/connecting/
  
  https://www.mlab.com/databases/heroku_jc07tp0r

  sudo apt-get install -y mongodb-org

  heroku config --app pnguyen-gumball | grep MONGOLAB_URI
  
  MONGOLAB_URI: 
  
    mongodb://<db_user>:<db_pass>@ds045614.mlab.com:45614/heroku_jc07tp0r

  To connect using the mongo shell:

    mongo ds045614.mlab.com:45614/heroku_jc07tp0r -u <dbuser> -p <dbpassword> 

  To connect using a driver via the standard MongoDB URI (what's this?):

    mongodb://<dbuser>:<dbpassword>@ds045614.mlab.com:45614/heroku_jc07tp0r
  
  Troubleshoot Connections:

    ping ds045614.mlab.com
    nc -w 3 -v ds045614.mlab.com 45614
    heroku logs --app pnguyen-gumball
    
  MongoDB Node Drivers:
  
    https://docs.mongodb.org/ecosystem/drivers/node-js/
```

======================
package.json (changes)
======================

```
{
  "name": "gumball_v1",
  "description": "Simple Test Form",
  "version": "1.0.0",
  "main": "app.js",
  "engines": {
    "node": "4.1.1"
  },
  "private": true,
  "scripts": {
    "start": "node app.js",
    "test": "vows --spec"
  },  
  "dependencies": {
    "express" : "3.x",
    "fs" : "0.0.2",
    "node-rest-client" : "1.4.1",
    "vows" : "*"
  }
}
```


=================
app.js (changes)
=================

```
app.set('port', (process.env.PORT || 5000));

app.post("*", handle_post );
app.get( "*", handle_get ) ;

app.listen(app.get('port'), function() {
  console.log('Node app is running on port', app.get('port'));
});
```


===========
.travis.yml
===========

```
language: node_js
node_js:
  - "4.1"
```
  
  