# SimpleCov::Buildkite

Generate [Buildkite annotations] from your [SimpleCov] coverage reports when running your build on [Buildkite].

  [Buildkite]: https://buildkite.com
  [Buildkite annotations]: https://buildkite.com/docs/agent/v3/cli-annotate
  [SimpleCov]: https://github.com/colszowka/simplecov

## Installation

Add this line to your application's Gemfile, after `simplecov`:

```ruby
gem "simplecov"
gem "simplecov-buildkite"
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install simplecov-buildkite

## Usage

Use it alongside your favourite formatter. For example, in [Rails] with [RSpec], add it in your `spec_helper.rb` like this:

```ruby
# spec/spec_helper.rb

require "simplecov"
require "simplecov-buildkite"

SimpleCov.start "rails" do
  formatter SimpleCov::Formatter::MultiFormatter.new([
    SimpleCov::Formatter::HTMLFormatter,
    SimpleCov::Buildkite::AnnotationFormatter,
  ])
end
```

When run on Buildkite, this will also output a pretty Buildkite annotation:

<img width="473" alt="Buildkite build showing a SimpleCov report in a Buildkite annotation" src="https://user-images.githubusercontent.com/282113/40627591-b8de5bc4-6274-11e8-8483-245e35c873af.png">

  [Rails]: https://rubyonrails.org
  [RSpec]: http://rspec.info

## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/ticky/simplecov-buildkite. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant] code of conduct.

  [Contributor Covenant]: http://contributor-covenant.org

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the SimpleCov::Buildkite project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/ticky/simplecov-buildkite/blob/master/CODE_OF_CONDUCT.md).
