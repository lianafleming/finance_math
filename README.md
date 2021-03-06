[![Gem Version](https://badge.fury.io/rb/finance_math.svg)](http://badge.fury.io/rb/finance_math)
[![Build Status](https://semaphoreapp.com/api/v1/projects/869d7630-55d3-46e5-9dc2-03d0d1cfecfe/363108/shields_badge.svg)](https://semaphoreapp.com/kolosek/finance_math)
[![Code Climate](https://codeclimate.com/github/kolosek/finance_math/badges/gpa.svg)](https://codeclimate.com/github/kolosek/finance_math)


## What is FinanceMath?

FinanceMath is a Ruby library for mapping Loan based Exel functions. It deals with problem of calculating the PMT and APR functions. It implements advanced usage, taking into account bank fees, fee for for each payment and currency protection (if currency other than $ USD). Highly precise with high speed of execution. 

## Installation

FinanceMath is available as a gem, to install it just install the gem:

    gem install finance_math

If you're using Bundler, add the gem to Gemfile.

    gem 'finance_math'

Run `bundle install`.

## Basic Usage

Create an instance, and pass parameters for nominal annual rate, duration (in months), and amount of loan.

```ruby

Loan.new(10.5, 12, 15000)
```

## Advanced Usage

Create an instance, and pass parameters for nominal annual rate, duration (in months), and amount of loan, and additional values such as bank fee, currency protection, and fee for each monthly payment. 

Defaults are bank fee = 5, currency protection = 3, so please update if you need other values.

```ruby

Loan.new(10.5, 12, 15000, 5.1, 2.75, 25)
```

## Functions 

This is the list of available functions.

### Loan.pmt

Calculates the periodic payment for an annuity investment based on constant-amount periodic payments and a constant interest rate.

```ruby

loan = Loan.new(10, 12, 1000)
loan.pmt
# 87.9158872300099

```

### Loan.apr

Calculates the Annual Percentage Rate.

```ruby

loan = Loan.new(13, 12, 10000)
loan.apr
#29.179538647635006

loan = Loan.new(15, 36, 10000, 5, 3, 10)
loan.apr
#23.964418264624054

```

## Contributing

1. Fork it ( https://github.com/kolosek/finance_math/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

## Tests

Please cover with tests your pull requests

## Copyright

Copyright (c) 2014-2015 Nebojsa Zoric, and Kolosek, Inc. (http://kolosek.com)

###Follow up @nebojsaz and @kolosek


## License

MIT License. See LICENSE for details.
