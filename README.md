# jacket-captcha
> A captcha that develop by Jacket Chen..

## Sample
The generated captcha image looks like this:
![alt tag](https://raw.githubusercontent.com/chenjuneking/jacket-captcha/master/jacket-captcha-sample.png)

## Usage

First, install `jacket-captcha`.

```shell
npm install jacket-captcha
```

`jacket-captcha` depend on `node-canvas`, install `node-canvas` you'll _need_ __Cairo__. For system-specific installation view the [Wiki](https://github.com/Automattic/node-canvas/wiki/_pages).

You can quickly install the dependencies by using the command for your OS:

OS | Command
----- | -----
OS X | `brew install pkg-config cairo libpng jpeg giflib`
Ubuntu | `sudo apt-get install libcairo2-dev libjpeg8-dev libpango1.0-dev libgif-dev build-essential g++`
Fedora | `sudo yum install cairo cairo-devel cairomm-devel libjpeg-turbo-devel pango pango-devel pangomm pangomm-devel giflib-devel`
Solaris | `pkgin install cairo pkg-config xproto renderproto kbproto xextproto`
Windows | [Instructions on wiki](https://github.com/Automattic/node-canvas/wiki/Installation---Windows)

**El Capitan users:** If you have recently updated to El Capitan and are experiencing trouble when compiling, run the following command: `xcode-select --install`. Read more about the problem [on Stack Overflow](http://stackoverflow.com/a/32929012/148072).

After you sucessfully install `jacket-captcha`, use it in your node app:

```javascript
// require library
var captcha = require('jacket-captcha');

// configure and create a captcha image
var captchaObj = captcha.config({
    width: 70,      // image's width
    height: 35,     // image's height
    lineNumber: 6,  // lines number that would be drawn into the image in case of prevent the program automatically discern the code on the image
    charNumber: 4   // the length of code
}).create();

// get the captcha code
var code = captchaObj.code;

// get the base64 url of the captcha image
var base64URL = captchaObj.base64URL;

// Do something...

```

## API

require `jacket-captcha` will return a captcha instance.

#### Captcha#config(options)
Return: `Object` <br>
This method will return the captcha instance.

#### options
Type: `Object` <br>
The configuration of the captcha instance.

##### options.width
Type: `Number` <br>
Config the width of the captcha image.

##### options.height
Type: `Number` <br>
Config the height of the captcha image.

##### options.lineNumber
Type: `Number` <br>
Config the number of lines that would be drawn into the image in case of prevent the program automatically discern the code on the image.

##### options.charNumber
Type: `Number` <br>
Config the length of code.

#### Captcha#create()
Return: `Object` <br>
Create a captcha image.<br>
This method will return the captcha image instance.

#### Captcha#getCode()
Return: `String`<br>
Get the captcha code.<br>
This method will return the captcha code that generated by the method of `Captcha#create()`.

#### Captcha#getBase64URL()
Return: `String`<br>
Get the base64 url of the captcha image.<br>
This mehod will return the base64 url of the captcha image that generated by the method of `Captcha#create()`.




