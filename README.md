<img alt="" src=".tools/pow.png" width="12%" style="width:12%"/>
[![Travis build status](https://travis-ci.org/coderofsalvation/powscript.svg?branch=master)](https://travis-ci.org/coderofsalvation/powscript.svg?branch=master)
  write shellscript in a powful way!

## Usage

    $ wget "https://raw.githubusercontent.com/coderofsalvation/powscript/master/powscript" -O /usr/local/bin/powscript && chmod 755 /usr/local/bin/powscript
    $ powscript myscript.pow                        # run directly
    $ powscript --compile myscript.pow > myscript   # output bashscript

## Example

    #!/usr/bin/env powscript
    require 'foo'
    
    usage(app)
      echo "$app <number>"
      
    switch $1
      case [0-9]*
        echo "arg 1 is a number"
      case *
        if empty $1
          help=$(usage myapp)
          echo "Usage: $help" && exit

## Reference + Examples

Check the wiki <a href="https://github.com/coderofsalvation/powscript/wiki/Reference">here</a>

## Features

* indentbased, memorizable, coffeescript-inspired syntax
* more human-like, less semantic noise like { ! [[ @ ]] || ~=
* safetynets: automatic quoting, halt on error
* comfort: easy arrays, easy async, functional programming, named variables instead of positionals
* written in bash 4, 'zero'-dependency solution
* hasslefree: easy installation without gcc compilation/3rd party software

## Modules 

Create 1 portable bashscript.

####  /myapp.pow

    require 'mod/mymod.pow'
    require 'mod/foo.bash'

    mymodfunc
    bar

#### /mod/mymod.pow

    mymodfunc()
      echo "hi im a powscript module!"

#### /mod/foo.bash

    function bar(){
      echo "hi im a bash module"
    }

Then run `powscript --compile myapp.pow > all-in-one.bash`

## Examples

* [m3uchecker (19 lines powscript vs 57 lines bash)](https://gist.github.com/coderofsalvation/b1313d287c1f0a7e6cdf)

## Wiki

* [Developer info / Contributions](https://github.com/coderofsalvation/powscript/wiki/Contributing)
* [Similar projects](https://github.com/coderofsalvation/powscript/wiki/Similar-projects)
