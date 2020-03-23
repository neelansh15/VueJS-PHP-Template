# VueJS PHP Template Repository
A template repository to quickly start a new project with a VueJS frontend and PHP CodeIgniter backend. This is especially useful in hackathons or personal projects, since you can get down and immediately start programming your idea.

   ![Javascript](https://img.shields.io/badge/Frontend-Javascript-yellow)
   ![VueJS](https://img.shields.io/badge/Frontend-VueJS-brightgreen)
   ![PHP](https://img.shields.io/badge/Backend-PHP-blue)
   ![CodeIgniter v3](https://img.shields.io/badge/Backend-CodeIgniter%20v3-orange)
   
![VueJS Image](https://www.mindinventory.com/blog/wp-content/uploads/2018/07/vuejs1200.png)

## What's included
### VueJS
VueJS is installed via vue-cli with default configuration **plus** vuex and vue-router.
Below is the list of newly installed packages:
  * Vuex
  * vue-router
  * vue-toast-notifications
  * axios
  * qs

   __qs__ is used to securely stringify an object before sending it through a POST request using `axios`.
   
   Example usage:
   ```javascript
const headers = {
      'Content-Type': 'application/x-www-form-urlencoded'
}
const data = {
        username: 'alkibiadez',
        password: 'goCorona'
}

axios({
        method: 'post',
        url: 'localhost:80/myapp/post',
        data: qs.stringify(data),
        headers: headers
})
   ```
   
### PHP

   CodeIgniter v3 is installed in the `api/` directory. CodeIgniter is an open-source software rapid development web framework, for use in building dynamic web sites with PHP. It has a **really** small footprint, so it keeps your project lightweight. It is also reallyeasy to get started with.  
   As of now, CodeIgniter v4 is realeased too. But I found v3 to be simpler and easier than v4, which is fresh out of Beta.

   **Note:** Since you would be sending cross-domain requests, you need to look at allowing cross origin requests in the API to avoid CORS errors. Look at the below section to know how you can solve this.

## Errors you may encounter
### CORS
To know more about CORS, visit https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS  
This error pops up only when you are using different domains in develpment. Even hosting on different ports like `localhost:3000` and `localhost:80` count.

To solve CORS errors, just set the required headers _wherever_ you have an action method (function) inside a controller in PHP:
```php
header('Access-Control-Allow-Origin: *');
header("Access-Control-Allow-Methods: GET, POST, OPTIONS, PUT, DELETE");
header("Access-Control-Allow-Headers: Authorization");
```
Be careful. You might want to restrict access to only your own domain when deploying for production (Change `*` to the domain name). For development on your local machine though, this is fine.
 
## XAMPP Instructions
   If you're programming on your local machine, you would need to have two servers running. One for VueJS at `localhost:3000` and one for PHP at `localhost:80`.  
   
   But XAMPP stores files and folders only from its `xampp/htdocs` directory. In order to serve your PHP from thee `api/` directory of this template, you can look up the __Make an alias__ section on this link: https://stackoverflow.com/a/1421/11743498  
 
# Contributing
I welcome everyone to make contributions to this template. Contributions can be anything, like:  
   * Adding a new package which you think is essential
   * Fixing a problem
   * Fixing a problem concerning the version of a package. Or if a package is outdated, adding another similar to it.
   * New code to better organize the workflow
   * Everything else

You can even suggest better practices for writing code if necessary!
   
