# README

Both unit/functional test rake tasks can't be run in one rake command:

    $ rake test:units test:functionals TESTOPTS=-v
    Run options: -v --seed 41266

    # Running:

    FunctionalTest#test_functional = 0.00 s = .

    Finished in 0.002507s, 398.8766 runs/s, 0.0000 assertions/s.

    1 runs, 0 assertions, 0 failures, 0 errors, 0 skips

But the other way, only unit tests run:

    $ rake test:functionals test:units TESTOPTS=-v
    Run options: -v --seed 9620

    # Running:

    UnitTest#test_unit = 0.00 s = .

    Finished in 0.002579s, 387.7828 runs/s, 0.0000 assertions/s.

    1 runs, 0 assertions, 0 failures, 0 errors, 0 skips

(`rake test` etc work fine, it's just the selective tasks)

It works fine on Rails 4.2.7.1 (see [4.2 branch](https://github.com/domcleal/bug_rails_rake_chain/tree/4.2)).
