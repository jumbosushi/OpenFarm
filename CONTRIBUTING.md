# Contributing

First off, before contributing anything, sign our [Contributor License Agreement](https://www.clahub.com/agreements/openfarmcc/OpenFarm).

## Then!

 1. Fork this repo (see Running Locally for more details).
 2. Fix stuff, write features, unit tests(!).
 3. Send pull request to master.

Not sure where to help? Take a look at the [Issue Tracker](https://github.com/openfarmcc/OpenFarm/issues). It is advisable to let others know your intent to implement a feautre before starting, as it lets other contributors focus their efforts elsewhere.

Want to see the big picture? We have a [project roadmap](https://docs.google.com/spreadsheets/d/13_VQDOm8HpM49Ql3HyNfL9ut5JlqbLEDA9yEk5OqgqU/edit?usp=sharing) for that!

# Running Locally

You will need [Ruby](http://www.ruby-lang.org/en/), [Rails](http://rubyonrails.org/), [ElasticSearch](http://www.elasticsearch.org/) and [Mongodb](http://docs.mongodb.org/manual/installation/) installed before continuing. Once you have these prerequisites to get started with a local copy of the project, run:

```bash
$ git clone https://github.com/openfarmcc/OpenFarm.git
$ cd OpenFarm
$ bundle install
$ rake db:setup
$ echo "ENV['SECRET_KEY_BASE'] = '$(rake secret)'" >> config/app_environment_variables.rb
$ rails s
```

If all went well, you will have a seeded database and can use the account `admin@admin.com` with password `admin123`.

**If you had any problems** installing bundles getting up and running etc see the [Common Issues Page](https://github.com/openfarmcc/OpenFarm/wiki/Common-Issues).

#### Sensitive Information

All secrets (such as S3 credentials) are stored in ENV variables. You will need to set `config/app_environment_variables.rb` accordingly. See `config/app_environment_variables.rb.example` for an example.

## When Ready to Submit your Changes

Make sure the tests pass:

    rspec

Push to your fork and [submit a pull request][pr].

[pr]: https://github.com/openfarmcc/OpenFarm/compare/

At this point you're waiting on us. We like to at least comment on pull requests
within three business days (and, typically, one business day). We may suggest
some changes or improvements or alternatives.

Some things that will increase the chance that your pull request is accepted:

* Write tests.
* Follow our Style Guides.
* Write a [good commit message][commit].

[commit]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html


## Style Guides and formatting.

 * We use the [ThoghtBot Style Guide](https://github.com/thoughtbot/guides/tree/master/style) when writiting Ruby. The exception to this is that we use 'single quotes' instead of "double quotes".
 * When designing API endpoints, follow the [JSONAPI.org formatting guide](http://jsonapi.org/format/)
 * Please write specs for your code. We use Rspec as our testing framework.