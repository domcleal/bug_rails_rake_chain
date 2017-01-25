# README

Under Rails 5.0 or master (5.1.0.alpha), calling two `test:*` rake tasks at
once ignores the first.

This works fine here on 4.2.7.1:

    $ rake test:functionals test:units TESTOPTS=-v
    Run options: -v --seed 46880

    # Running:

    UnitTest#test_unit = 0.00 s = .
    FunctionalTest#test_functional = 0.00 s = .

    Finished in 0.003849s, 519.6569 runs/s, 0.0000 assertions/s.

        2 runs, 0 assertions, 0 failures, 0 errors, 0 skips

But breaks on Rails 5.x (see [master branch](https://github.com/domcleal/bug_rails_rake_chain/tree/master)).
