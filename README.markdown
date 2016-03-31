__NAME__

peng - encode arbitrary data to a PNG image file

__SYNOPSIS__

    peng.py [-h] [-d] [-c {gz,zip,bz}] [-s SCALE] input output

__DESCRIPTION__

With peng you can encode arbitrary data into a PNG image file.

positional arguments:

    input                 Input filename or "-" for stdin.
    output                Output filename or "-" for stdout.

optional arguments:

    -h, --help            show this help message and exit
    -d                    Decode instead of encode.
    -c {gz,zip,bz}, --compress {gz,zip,bz}
    -s SCALE, --scale SCALE
    --width WIDTH         Fixed width.
    --height HEIGHT       Fixed height.

__EXAMPLES__

    echo 'Hello, World!' | python3 peng.py - helloworld.png --scale=20 --compress=zip

<img align="center" src="http://i.imgur.com/BKgsn3o.png"></img>

    cat peng.py | python3 peng.py - peng.png --scale=7 --compress=zip --height=10

<img align="center" src="http://i.imgur.com/vYEOWEp.png"></img>

    python3 peng.py -d helloworld.png -

> Hello, World!
