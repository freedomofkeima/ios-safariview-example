# ios-safariview-example

This repository contains an example of SFSafariViewController for iOS 9 and up in Objective-C. This repository is mainly created because there is no proper documentation on how to pass data between Safari and your native apps in Objective-C.

By using this example, you will learn how to:

- Open your web content via SFSafariViewController directly
- Implement a callback when "Done" button is pressed via `safariViewControllerDidFinish` (normal way)
- Invoke a callback via custom URL scheme (e.g.: redirection) & NSNotificationCenter
- Allow backwards compatibility with iOS 8 and below (of course, without this functionality)

As a reference, this repository is inspired from [mackuba/SafariAutoLoginTest](https://github.com/mackuba/SafariAutoLoginTest). In addition to seamless auto-login, one of the other motivation in using this technique is to support certificate sharing between native apps which are not signed under same publishers.


## Screenshot

<img src="https://lh3.googleusercontent.com/-tsgLwrKOM40/V8fyHG6AVBI/AAAAAAAAO7Q/PsWjj_hQh4gMnPWEwSR7zcyuI7hUNM4rACLcB/s0/Screen+Shot+2016-09-01+at+3.58.44+PM.png" height="500px">

<img src="https://lh3.googleusercontent.com/-nGihXcni5RE/V8fyKXFMc4I/AAAAAAAAO7Y/ZiBZdAtbIA85F4Ck3Zledgl_KY0C8Uc8wCLcB/s0/Screen+Shot+2016-09-01+at+3.58.50+PM.png" height="500px">


## Allow custom URL scheme invocations

You need to configure the value of `LSApplicationQueriesSchemes` and `URL types` in your `Info.plist`. In this example, it's already provided so you don't need to change anything.

<img src="https://lh3.googleusercontent.com/-Pjpx-8F6si8/V8fzEM7ys9I/AAAAAAAAO70/Pnd_njA1iNsqYZ9QQrFFGAbT5NHNnL1hACLcB/s0/Screen+Shot+2016-09-01+at+4.17.39+PM.png">


## Allow backwards compatibility

In order to use lower deployment target (e.g.: iOS 8.1) safely, you need to change the binary which is linked from `Required` to `Optional`.

<img src="https://lh3.googleusercontent.com/-ZKVMvQvm914/V8fzJdNoxxI/AAAAAAAAO78/ZPeW0H8Q2Qw2oKOPAyM5CFixmbKRZ7nnwCLcB/s0/Screen+Shot+2016-09-01+at+4.18.01+PM.png">


## How to test (callback via URL scheme)

- Clone this project

- In your website, use the following example code to redirect your client to `freedomofkeima://?ThisIsResponseSample`

```
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Refresh" content="3; URL='freedomofkeima://?ThisIsResponseSample'">
    </head>
    <body>
    </body>
</html>
```

- Add your `url_endpoint` [here](https://github.com/freedomofkeima/ios-safariview-example/blob/master/ios-safariview-example/ViewController.m#L19)

- Open this project in Xcode and run it


## License

MIT License.

Last Updated: September 1, 2016

