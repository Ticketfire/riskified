# Riskified

Use riskified with Ruby and Spree. Don't want to use this with Spree? Make your own adapter in `riskified/adapters/`.

TODO: test

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'riskified'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install riskified

## Usage
    # send spree order to riskified
    $ require 'riskified'
    $ client = Riskified::Client.new
    $ resp = client.create(Spree::Order.last)
    
    # serialize spree order to Riskified API format
    $ o = Spree::Order.where.not(completed_at: nil).first
    $ a = Riskified::Adapter::Spree.new(o)
    $ a.to_json 




## Development

After checking out the repo, run `bin/setup` to install dependencies. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/riskified.


## License

The gem is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).

