# libcurl for Crystal [![Build Status](https://travis-ci.org/blocknotes/curl-crystal.svg)](https://travis-ci.org/blocknotes/curl-crystal)

Crystal C bindings for libcurl, the multiprotocol file transfer library - see [libcurl](https://curl.haxx.se/libcurl/)

**NOTE**: actually not all functions are mapped - if you find something missing [contact me](http://www.blocknot.es/me)

## Installation

Add this to your application's `shard.yml`:

```yaml
dependencies:
  curl-crystal:
    github: blocknotes/curl-crystal
```

## Usage

Fetch an URL an print the content to the STDOUT:

```ruby
require "curl-crystal"
curl = LibCurl.curl_easy_init  # init
LibCurl.curl_easy_setopt curl, LibCurl::CURLoption::CURLOPT_URL, "https://www.google.com"  # set URL
LibCurl.curl_easy_setopt curl, LibCurl::CURLoption::CURLOPT_FOLLOWLOCATION, 1  # follow redirect
LibCurl.curl_easy_perform curl  # run
LibCurl.curl_easy_cleanup curl  # deinit
```

## More examples

- [examples](https://github.com/blocknotes/curl-crystal/tree/master/examples) folder
- libcurl C [examples](https://curl.haxx.se/libcurl/c/example.html)

## Contributors

- [Mattia Roccoberton](http://blocknot.es) - creator, maintainer, Crystal fan :)
