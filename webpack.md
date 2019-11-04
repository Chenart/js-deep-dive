# Webpack

## What is Webpack and why use it?
Webpack takes all of our application's files and bundles them into a single file that can be run by a client. 

Webpack is useful when we're building frontend applications where we want the dependencies on the frontend. 
Traditionally, servers render the applications, but this introduces page flashing upon rerender, and makes us reliant on network quality. 
We can overcome these drawbacks by using client rendering, but clients don't have an environment that can "connect" multiple files to each other via their dependencies.

Therefore, to make it possible for clients to render multi-file applications, we use Webpack to bundle the multi-file application into a single-file application.

Good SO answer: https://stackoverflow.com/questions/40562031/webpack-how-does-webpack-work

## How to use Webpack

## How to configure Webpack

## Other notes
* Sometimes, Webpack conflicts with certain types of modules (ex. AMD).
In this case, we either need to write a custom Webpack config, or we should export our module with a different type.
