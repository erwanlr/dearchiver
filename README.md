# Dearchiver

A simple Ruby Gem to decompress and check the CRC of compressed files.

## Installation

Add this line to your application's Gemfile:

    gem 'dearchiver'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install dearchiver

## Usage

Dearchiver will use the command line of your operating system to perform the desired operations in the
compressed files. This means that you **need** to have utilities installed (say *unzip*, *unrar*, *7zip* and *tar*).

Usage is very simple.

Just for now the gem will work only of the following type of files:

    .zip
    .rar
    .tar.gz
    .7z

**TESTED ON Ubuntu 10.04**: No idea how it is going to behave in other OS.

### Checking CRC

    da = Dearchiver.new(:filename => "foo.zip")
    da.crc_ok?

If the filename doesn't have any extension, you can use:

    da = Dearchiver.new(:filename => "foo", :archive_type => ".zip")
    da.crc_ok?

### Extracting files

    da = Dearchiver.new(:filename => "foo.zip")
    da.extract_to("/tmp")
    puts da.list_of_files

## Original Blog Post

[Go here!](http://www.jpgenovese.com/2012/10/29/dearchiver-a-small-gem-to-check-the-crc-and-decompress-files/ "Dearchiver, a small gem to check the CRC and decompress files.")

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

