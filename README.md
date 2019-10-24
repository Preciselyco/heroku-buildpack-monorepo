# Heroku Multi Procfile buildpack
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FPreciselyco%2Fheroku-buildpack-monorepo.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2FPreciselyco%2Fheroku-buildpack-monorepo?ref=badge_shield)


Imagine you have a single code base, which has a few different applications within it... or at least the ability to run a few different applications. Or, maybe you're Google with your mono repo?

In any case, how do you manage this on Heroku? You don't. Heroku applications assume one repo to one application.

Enter the Monorepo buildpack, which is a copy of [heroku-buildpack-multi-procfile](https://github.com/heroku/heroku-buildpack-multi-procfile) except it moves the target path in to the root, rather than just the Procfile. This helps for ruby apps etc.

# Usage

1. Write a bunch of ~~Procfiles~~ apps and scatter them through out your code base.
2. Create a bunch of Heroku apps.
3. For each app, set `APP_BASE=relative/path/to/app/root`, and of course:
   `heroku buildpacks:add -a <app> https://github.com/lstoll/heroku-buildpack-monorepo`
4. For each app, `git push git@heroku.com:<app> master`

# Authors

* Andrew Gwozdziewycz <apg@heroku.com> 
* Cyril David <cyx@heroku.com>
* Lincoln Stoll <lstoll@heroku.com>
* Stefan Nyman <stefan@precisely.se>


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2FPreciselyco%2Fheroku-buildpack-monorepo.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2FPreciselyco%2Fheroku-buildpack-monorepo?ref=badge_large)