__NAME__

peng - encode arbitrary data to a PNG image file

__SYNOPSIS__

    peng.py [-h] [-d] [-c {gz,zip,bz}] [-s SCALE] input output

__DESCRIPTION__

With peng you can encode arbitrary data to a PNG image file. The data can
optionally be compressed with Zip, GZip or BZip in order zo reduce data size
and generate a much more colorful result (especially for plain text data).
The resulting file has the PNG header overhead plus the 3 firrst pixels (ie.
9 bytes) for the peng header information.

The anmount of data that can be encrypted is limited to 196,599 bytes.

```
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
```

__DEPENDENCIES__

* [PyPNG](https://github.com/drj11/pypng)

__EXAMPLES__

    echo 'Hello, World!' | python3 peng.py - helloworld.png --scale=20 --compress=zip

<img align="center" src="http://i.imgur.com/BKgsn3o.png"></img>

    cat peng.py | python3 peng.py - peng.png --scale=7 --compress=zip --height=10

<img align="center" src="http://i.imgur.com/vYEOWEp.png"></img>

    python3 peng.py -d helloworld.png -

> Hello, World!
