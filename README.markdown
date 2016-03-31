__NAME__

`peng` - encode arbitrary data to a PNG image file

__SYNOPSIS__

    peng.py [-h] [-d] [--compress {gz,zip,bz}] [--scale SCALE]
            [--width WIDTH] [--height HEIGHT] [--fill {repeat,zero,random}]
            [--seed SEED]
            input output

__DESCRIPTION__

With `peng` you can encode arbitrary data to a PNG image file. The
data can optionally be compressed with zip, gzip or bzip2 to reduce
data size and generate a more colorful result (especially for plain
text data). The resulting PNG image file has only a slight overhead
over the original data, that being the PNG header plus 9 bytes of
the `peng` header information.

The amount of data that can be encoded with `peng` is limited to
196,599 bytes.

```
positional arguments:
  input                 input file or '-' for stdin
  output                output file or '-' for stdout

optional arguments:
  -h, --help            show this help message and exit
  -d, --decode          decode input to output
  --compress {gz,zip,bz}
                        compression method, omit for no compression
  --scale SCALE         post-encode scaling, defaults to 1
  --width WIDTH         fixed width (< 256)
  --height HEIGHT       fixed height (< 256)
  --fill {repeat,zero,random}
                        padding fill method, defaults to repeat
  --seed SEED           seed for the --fill=random mode
```

__DEPENDENCIES__

* [PyPNG](https://github.com/drj11/pypng)

__EXAMPLES__

    echo 'Hello, World!' | ./peng.py - helloworld.png --scale=20 --compress=zip

<img align="center" src="http://i.imgur.com/BKgsn3o.png"></img>

    ./peng.py --decode helloworld.png -

> Hello, World!

----

    ./peng.py peng.py peng.png --scale=7 --width=130 --compress=zip --fill=zero

<img align="center" src="http://i.imgur.com/G8ZHTw0.png"></img>
