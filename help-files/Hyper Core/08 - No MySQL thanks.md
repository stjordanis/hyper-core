## Extensions methods without MySQL

If you don't want to use MySQL, or want to create some method where you don't care about any database at all,
you have the `x` method, without any MySQL bindings. If this is the case, you can simply slightly modify your
URL, at which point it will invoke your extension method, without first opening up any MySQL database(s) for
you. This will first of all save a couple of CPU cycles, in addition to completely de-entangling your entire
project from MySQL. At which point you could create your own extension methods in for instance C# or something,
to use the project towards for instance MongoDB or MS SQL instead (or anything really). To invoke our
previously created _"foo.hl"_ file for instance, without opening any MySQL databases first, we could
accomplish that with the following URL.

```markdown
/hyper-core/x/foo
```

Now of course, if you do this, you do not have any open database connections, and are on your own in regards to
exactly what you want to do. The JSON returned from these methods, and arguments passed into these methods,
will still be 100% similar to its `/hyper-core/mysql/todo/foo/x` counterparts.
