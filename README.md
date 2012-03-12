rubyzip
=======

rubyzip is a ruby library for reading and writing zip files.

Install
-------

  gem install rubyzip


To run the unit tests you need to have test::unit installed

  rake test
[![Build Status](https://secure.travis-ci.org/aussiegeek/rubyzip.png)](http://travis-ci.org/aussiegeek/rubyzip)

Configuration
-------------

By default, rubyzip will not overwrite files if they already exist inside of the extracted path.  To change this behavior, you may specify a configuration option like so:

```
Zip.options[:on_exists_proc] = true
```

If you're using rubyzip with rails, consider placing this snippet of code in an initializer file such as `config/initializers/rubyzip.rb`

Additionally, if you want to configure rubyzip to overwrite pre-existing files while creating a .zip file, you can do so with the following:

```
Zip.options[:continue_on_exists_proc] = true
```


Documentation
-------------


There is more than one way to access or create a zip archive with
rubyzip. The basic API is modeled after the classes in
java.util.zip from the Java SDK. This means there are classes such
as Zip::ZipInputStream, Zip::ZipOutputStream and
Zip::ZipFile. Zip::ZipInputStream provides a basic interface for
iterating through the entries in a zip archive and reading from the
entries in the same way as from a regular File or IO
object. ZipOutputStream is the corresponding basic output
facility. Zip::ZipFile provides a mean for accessing the archives
central directory and provides means for accessing any entry without
having to iterate through the archive. Unlike Java's
java.util.zip.ZipFile rubyzip's Zip::ZipFile is mutable, which means
it can be used to change zip files as well.

Another way to access a zip archive with rubyzip is to use rubyzip's
Zip::ZipFileSystem API. Using this API files can be read from and
written to the archive in much the same manner as ruby's builtin
classes allows files to be read from and written to the file system.

rubyzip also features the
zip/ziprequire.rb[link:files/lib/zip/ziprequire_rb.html] module which
allows ruby to load ruby modules from zip archives.

For details about the specific behaviour of classes and methods refer
to the test suite. Finally you can generate the rdoc documentation or
visit http://rubyzip.sourceforge.net.

License
-------

rubyzip is distributed under the same license as ruby. See
http://www.ruby-lang.org/en/LICENSE.txt


Website and Project Home
------------------------

http://github.com/aussiegeek/rubyzip

http://rdoc.info/github/aussiegeek/rubyzip/master/frames

Authors
-------

Alan Harper ( alan at aussiegeek.net)

Thomas Sondergaard (thomas at sondergaard.cc)

Technorama Ltd. (oss-ruby-zip at technorama.net)

extra-field support contributed by Tatsuki Sugiura (sugi at nemui.org)
