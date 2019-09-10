# Intel - Fukuoka 2019 TPAC Plugfest

Two services are provided:
* A Simple Web Camera
* A Simple Speech interface

### Authentication
These services support end-to-end security
via a proxy.  Use the credentials, linked below, for "wotbasicproxy" or "wodigestproxy" based on whether you are using
basic or digest authentication.   Both services use the same credentials.

WARNING: Digest auth is broken at the moment.  I hope to fix it soon.  Basic should work.

* [Proxy Authentication Credentials](https://lists.w3.org/Archives/Member/member-wot-ig/2018May/0003.html)

W3C WoT membership required to access these credentials.
Please do not repost them in a public forum
(for example,
do not check the keys into a public github repo as part of a test suite,
post on a forum,
share in a public messaging system, etc).
These will be updated peroidically so if an access does not work,
check that you have the latest version.

### Simple Web Camera
Example image is given below.
Note that this does not auto-update;
that is in progress,
but it needs client-side script support
(eg to follow the frame "observe" interaction)
so will have to be implemented in HTML.

![Example image from camera 0](IMAGES/intel_light_observe.jpeg)

Summary of network API (see TDs for details):
* `/api` - get Thing Description
    * `/frame` - get last frame captured
        - `/observe` get next frame captured when ready (long polling)
    * `/exposure` - get/set manual exposure
        - `/observe` - observe changes in (manual) exposure (long polling)
    * `/crop` - get cropped version of last frame captured (an action using POST)

#### HTTP and Nosec 
* Local Access:
    [TD](http://plus2.local:9190/api) 
          
#### HTTPS and Basic Auth
* Digital Ocean Portal:
    [TD](https://portal.mmccool.net:8098/api) 
* AWS Portal:
    [TD](https://tiktok.mmccool.org:8098/api) 

#### HTTPS and Digest Auth
* Digital Ocean Portal:
    [TD](https://portal.mmccool.net:8099/api) 
* Japan AWS Portal:
    [TD](https://tiktok.mmccool.org:8099/api) 
       
### Web Speak
Speech synthesizer service.

Summary of network API: POST a quoted string to /api/say and it will speak it.

#### HTTP and Nosec 
* Local Access:
    [TD](http://plus2.local:8085/api) 
          
#### HTTPS and Basic Auth
* Digital Ocean Portal:
    [TD](https://portal.mmccool.net:8096/api) 
* AWS Portal:
    [TD](https://tiktok.mmccool.org:8096/api) 

#### HTTPS and Digest Auth
* Digital Ocean Portal:
    [TD](https://portal.mmccool.net:8097/api) 
* AWS Portal:
    [TD](https://tiktok.mmccool.org:8097/api) 