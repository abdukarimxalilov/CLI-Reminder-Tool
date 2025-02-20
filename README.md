# CLI-Reminder-Tool
Examples

tonight at 11:10 pm
at Friday afternoon
the deadline is next tuesday 14:00
drop me a line next wednesday at 2:25 p.m
it could be done at 11 am past tuesday
Check EN rules and tests of them, for more examples.

Needed rule not found? Open an issue with the case and it will be added asap.

How it works

Usually, there are several rules added to the parser's instance for checking. Each rule has its own borders - length and offset in provided string. Meanwhile, each rule yields only the first match over the string. So, the library checks all the rules and extracts a cluster of matched rules which have distance between each other less or equal to options.Distance, which is 5 by default. For example:

on next wednesday at 2:25 p.m.
   └──────┬─────┘    └───┬───┘
       weekday      hour + minute
So, we have a cluster of matched rules - "next wednesday at 2:25 p.m." in the string representation.

After that, each rule is applied to the context. In order of definition or in match order, if options.MatchByOrder is set to true(which it is by default). Each rule could be applied with given merge strategy. By default, it's an Override strategy. The other strategies are not implemented yet in the rules. Pull requests are welcome.
