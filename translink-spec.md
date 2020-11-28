[![N|Solid](https://translink.merge.africa/assets/Translink-Logo-450.png)](https://merge.africa)

# Translink Specificications Document

*Translink is a CRM focused on solving the problems faced by logistics companies in the modern day. The specifications outlined in the following document exist to solve those problems for small to medium sized logistics firms.*

### Definition of User roles throughout the application:
- Administrator
- Driver
- Site Manager
- Support Staff
- Accounting
- Executive Members

# Login / Logout
### All users
 >  A user with any ranking needs to be able to create a user profile.
 
 > A user whom has created a user profile needs to be able to log into the system.
 
 > The system needs to contain at least one user with the role of "Administrator". At any point in time the database should be seeded with at least one 'priviledged' user.
 
 > A user, after loggin in, should be able to log out.
 
 > User authentication cookies should only be cached for 30 days, after which the user should be forced to log in again, on that device.
 
 > User Password data should be 'hashed' with a unique salt value which can be stored in the same user table.
 ### Administrators
 > Should be able to view all the area's of the system without any restrictions. Full read / write access throughout the entire system.
 
### Executive Members
> Should be allowed to view a summary of the company operations, but not the day to day activities. For example, an executive member, should be able to generate a report summary for the companies sales, but not be able to view all the client and employee information. (Unless granted access by an administrator)

### Site Managers
> Should be allowed to generate and view sales reports, order summaries, trip plans, invoices, customers etc.

> A site manager should not be allowed to delete any information without administrative permission.

### Support Staff
> 
_Important Notes:_



> The overriding design goal for Markdown's
> formatting syntax is to make it as readable
> as possible. The idea is that a
> Markdown-formatted document should be
> publishable as-is, as plain text, without
> looking like it's been marked up with tags
> or formatting instructions.

This text you see here is *actually* written in Markdown! To get a feel for Markdown's syntax, type some text into the left window and watch the results in the right.

### Tech

Dillinger uses a number of open source projects to work properly:

* [AngularJS] - HTML enhanced for web apps!
* [Ace Editor] - awesome web-based text editor
* [markdown-it] - Markdown parser done right. Fast and easy to extend.
* [Twitter Bootstrap] - great UI boilerplate for modern web apps
* [node.js] - evented I/O for the backend
* [Express] - fast node.js network app framework [@tjholowaychuk]
* [Gulp] - the streaming build system
* [Breakdance](https://breakdance.github.io/breakdance/) - HTML to Markdown converter
* [jQuery] - duh

And of course Dillinger itself is open source with a [public repository][dill]
 on GitHub.

### Installation

Dillinger requires [Node.js](https://nodejs.org/) v4+ to run.

Install the dependencies and devDependencies and start the server.

# Postbucket
> Postbucket is a open source alternative to services like formspree, usebasin, etc. You can set this project up as a means to accept form data from static sites.

### Todo's
- [ ] Setup Controller
- [ ] Implement logic to catch "from site" and "recipient"
- [ ] Set up Entity Framework with MySql
- [ ] Send out SMS / Email notifications on submission.

### Features to look at later
- [ ] Create a user interface to sign up and log in to the system.
- [ ] Create a dashboard to view all the form submissions that have been made.
- [ ] Create a donations page.

## Setup
```sh
$ npm install
$ npm run build
$ npm run start
```

### Contributors
[@itsjessicajane](https://github.com/itsjessicajane)
[@caybokotze](https://github.com/caybokotze)

For production environments...

```sh
$ npm install --production
$ NODE_ENV=production node app
```

### Plugins

Dillinger is currently extended with the following plugins. Instructions on how to use them in your own application are linked below.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |


### Development

Want to contribute? Great!

Dillinger uses Gulp + Webpack for fast developing.
Make a change in your file and instantaneously see your updates!

Open your favorite Terminal and run these commands.

First Tab:
```sh
$ node app
```

Second Tab:
```sh
$ gulp watch
```

(optional) Third:
```sh
$ karma test
```
#### Building for source
For production release:
```sh
$ gulp build --prod
```
Generating pre-built zip archives for distribution:
```sh
$ gulp build dist --prod
```
### Docker
Dillinger is very easy to install and deploy in a Docker container.

By default, the Docker will expose port 8080, so change this within the Dockerfile if necessary. When ready, simply use the Dockerfile to build the image.

```sh
cd dillinger
docker build -t joemccann/dillinger:${package.json.version} .
```
This will create the dillinger image and pull in the necessary dependencies. Be sure to swap out `${package.json.version}` with the actual version of Dillinger.

Once done, run the Docker image and map the port to whatever you wish on your host. In this example, we simply map port 8000 of the host to port 8080 of the Docker (or whatever port was exposed in the Dockerfile):

```sh
docker run -d -p 8000:8080 --restart="always" <youruser>/dillinger:${package.json.version}
```

Verify the deployment by navigating to your server address in your preferred browser.

```sh
127.0.0.1:8000
```

#### Kubernetes + Google Cloud

See [KUBERNETES.md](https://github.com/joemccann/dillinger/blob/master/KUBERNETES.md)


### Todos

 - Write MORE Tests
 - Add Night Mode

License
----

MIT

