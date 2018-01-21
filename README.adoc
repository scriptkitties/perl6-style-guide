= Perl 6 Style Guide

* Avoid using $_, unless needed.
[source,perl6]
----
for @array -> $element { # good
  say $element;
}
for @array {
  .say # good
}
.say for @array; # better
----

* Declare constants with my, otherwise they are **automatically** *exported* by any module that uses it.
[source,perl6]
----
constant CONST = 10; # BAD
my constant CONST = 10; # good
