# Simplificator Renovate preset

![Config Validator Workflow](https://github.com/simplificator/renovate-preset/actions/workflows/renovate-config-validation.yml/badge.svg)

A Renovate preset with common configuration for all Simplificator projects. The configuration currently applies the following:

* The Dockerfile versions preset, useful when you need to install certain versions of tools in your Dockerfile, for example bndler. A usage example can be found [here](https://github.com/renovatebot/docker-renovate-full/blob/main/Dockerfile#L1-L2).
* Regex manager for [background services on Semaphore CI](https://docs.semaphoreci.com/ci-cd-environment/sem-service-managing-databases-and-services-on-linux/).
* Regex manager to update the bundler version found in `Gemfile.lock`.
* Group all non-major updates for packages with versions above 1.0.0.
* Group all patch updates for packages below version 1.0.0.
* Apply the `bump` strategy for `npm`.
* Apply the `update-lockfile` strategy for `bundler`.
* Apply the `pin` strategy for `mix`.
* Create updates every monday (instead of always), except for security updates.
* Activate the dependency dashboard.

## How can I use the preset in my project?

This is the minimal configuration needed to use this preset in your project:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "github>simplificator/renovate-preset"
  ]
}
```

## License

MIT / BSD
