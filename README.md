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

Get captcha key

    import seznam_captcha
    key = seznam_captcha.create()

Get captcha image url

    url = seznam_captcha.image_url(key)

read and check captcha value

    captcha_text = raw_input()
    if seznam_captcha.check(key):
        print "OK :)"
    else:
        print "Try it again :("