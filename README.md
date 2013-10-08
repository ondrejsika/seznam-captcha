seznam-captcha
==============

Wrapper for Seznam Captcha <http://captcha-api.seznam.cz/>

### Author
* Ondrej Sika, <http://ondrejsika.com>, <ondrej@ondrejsika.com>

### Source
* Python Package Index: <http://pypi.python.org/pypi/seznam-captcha>
* GitHub: <https://github.com/sikaondrej/seznam-captcha>


Installation
------------

    pip install seznam-captcha

Usage
-----

### Raw methods

Get captcha key

    import seznam_captcha
    key = seznam_captcha.create()

Get captcha image url

    url = seznam_captcha.image_url(key)

Get captcha audio url

    url = seznam_captcha.image_url(key)

read and check captcha value

    captcha_text = raw_input()
    if seznam_captcha.check(key):
        print "OK :)"
    else:
        print "Try it again :("

### Object oriented

Captha object has these attributes

* key - captcha hash
* image_url - url to image with hash
* audio_url - url to audio with hash
* get_image() - fill image_file from remote file on image_url as Python file
* get_audio() - fill audio_file from remote file on audio_url as Python file
* image_file 
* audio_file
* check(text) - check if captcha is valid


``` python
>>> captcha = seznam_captcha.Captcha()
>>> captcha.key
"KJGTZVCF"
>>> captcha.get_image()
<addinfourl at 29361720 whose fp = <socket._fileobject object at 0x183a0d0>>
>>> captcha.image_file
<addinfourl at 29361720 whose fp = <socket._fileobject object at 0x183a0d0>>
>>> captcha.check("aljkdew")
True
>>> captcha.key
None
>>> captcha.check("aljkdew")
False
```
