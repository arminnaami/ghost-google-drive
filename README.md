# Ghost Google Drive
[Google drive storage](https://github.com/robincsamuel/ghost-google-drive) for ghost allows you to store the contents on google drive. I believe its helpful if you are gonna host your ghost app on heroku.

## Installation

In order to replace the storage module, the basic requirements are:

- Create a new folder inside `/content` called `/storage`
- Clone this repo to `/storage`

  ```
  cd [path/to/ghost]/content/storage
  git clone https://github.com/robincsamuel/ghost-google-drive.git
  ```
- Install dependencies

  ```
  cd ghost-google-drive
  npm install
  ```

## Create OAuth credentials

- Login to [google console](https://code.google.com/apis/console)
- Create new project from the top left dropdown.
- Pick your project and select `API & Auth` and then `Credentials` from the left hand menu.
- Under `OAuth`, click `Create new client ID`, and select `Service Account`. (keep the key type as json itself)
- Click `create client id`, and google will generate a json file with the credentials for you.
- In the next step, we have to copy the contents of that json file into the `config.js`.
- Now select, `APIs` under `APIs & Auth` from the same left hand menu.
- Select `Drive API` under `Google Apps APIs` and then enable it.

## Configuration

In your `config.js` file, you'll need to add a new `storage` block to whichever environment you want to change:

```js
storage: {
  active: 'ghost-google-drive',
  'ghost-google-drive': {
    key: {
            "private_key_id": "YOUR PRIVATE KEY ID",
            "private_key": "YOUR PRIVATE KEY",
            "client_email": "YOUR CLIENT EMAIL",
            "client_id": "YOUR CLIENT ID",
          }
  }
}
```
We just need to replace the key object with your json array generated by google console.


## License

Read [LICENSE](LICENSE)

Feel free to create an [issue](https://github.com/robincsamuel/ghost-google-drive/issues), in case of troubles!

Note: I'll try to put this to npm asap

Thanks to [Minwe](http;//github.com/Minwe). I was following your package, even this readme!


