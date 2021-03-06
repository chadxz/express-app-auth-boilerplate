# express-app-auth-boilerplate

Building a node.js web application with authentication involves a great deal of boilerplate to get up and running. This
repo intends to serve as a jumpstart for this scenario. Some features:

 - express.js server framework
 - local account creation & management
 - social signon using twitter, github, and google
 - ability to associate existing account with social login methods

some things this project does **not** have:

 - no modules that require native addons, making it easy to get started on windows
 - no attempt to define look and feel
 - no advanced tools (transpilers, minifiers, bundlers, build tools). developer can add as needed!
 - no requirement of database backend, thanks to nedb database

## getting started

 1. `git clone https://github.com/chadxz/express-app-auth-boilerplate.git --depth=1 your-app-name` to retrieve the repo
 with only the most recent history. This makes the clone quick!
 1. `cd your-app-name && rm -rf .git` to remove the repo history so you can start your repo fresh
 1. `npm install` to install the project dependencies
 1. change the project name in `package.json` and `bower.json`, to make the project your own
 1. `npm start` to start the server on http://localhost:8080

## obtaining API keys

By default, the project only has local login enabled. To enable social login via google, github, or twitter, you must
obtain the appropriate credentials from the respective service. Once you obtain the necessary credentials, you can copy
`config/default.js` to `config/local.js`, and fill in your credentials under the service's object. Once the credentials
have been filled in, you can toggle the social login method by setting the `enable` property to `true` or `false` as
needed.

<img src="http://images.google.com/intl/en_ALL/images/srpr/logo6w.png" width="200">

- Visit [Google Cloud Console](https://cloud.google.com/console/project)
- Click **CREATE PROJECT** button
- Enter *Project Name*, then click **CREATE**
- Then select *APIs & auth* from the sidebar and click on *Credentials* tab
- Click **CREATE NEW CLIENT ID** button
 - **Application Type**: Web Application
 - **Authorized Javascript origins**: `http://localhost:8080`
 - **Authorized redirect URI**: `http://localhost:8080/auth/google/callback`
- Copy and paste *Client ID* and *Client secret* keys into `config/local.js`

**Note:** When you ready to deploy to production don't forget to add your new url to *Authorized Javascript origins*
and *Authorized redirect URI*, e.g. `http://my-awesome-app.herokuapp.com` and
`http://my-awesome-app.herokuapp.com/auth/google/callback` respectively. The same goes for other providers.

<img src="https://github.global.ssl.fastly.net/images/modules/logos_page/GitHub-Logo.png" width="200">

- Go to [Account Settings](https://github.com/settings/profile)
- Select **Applications** from the sidebar
- Then inside **Developer applications** click on **Register new application**
- Enter *Application Name* and *Homepage URL*.
- For *Authorization Callback URL*: `http://localhost:8080/auth/github/callback`
- Click **Register application**
- Now copy and paste *Client ID* and *Client Secret* keys into `config/local.js`

<img src="https://g.twimg.com/Twitter_logo_blue.png" width="90">

- Sign in at [https://apps.twitter.com/](https://apps.twitter.com/)
- Click **Create a new application**
- Enter your application name, website and description
- For **Callback URL**: `http://localhost:8080/auth/twitter/callback`
- Go to **Settings** tab
- Under *Application Type* select **Read and Write** access
- Check the box **Allow this application to be used to Sign in with Twitter**
- Click **Update this Twitter's applications settings**
- Copy and paste *Consumer Key* and *Consumer Secret* keys into `config/local.js`

## screenshots

![login page](https://cloud.githubusercontent.com/assets/309219/7867971/cd7482b6-053e-11e5-97b9-834323063c2e.png)

![signup page](https://cloud.githubusercontent.com/assets/309219/7867975/cd83bf74-053e-11e5-82cc-bb094b9c4201.png)

![account management 1](https://cloud.githubusercontent.com/assets/309219/7867972/cd7edbf8-053e-11e5-86e6-77f500fd2203.png)

![account management 2](https://cloud.githubusercontent.com/assets/309219/7867973/cd7f5eca-053e-11e5-892c-4f49fdb47e2c.png)

## license
[MIT](LICENSE-MIT)
