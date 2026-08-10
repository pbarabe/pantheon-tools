# Pantheon Tools for QS2 Site Maintenance

## About

A few little tools to help simplify site maintainance on [pantheon.io](pantheon.io)

- `terminus-composer-update`: Run `composer update` on a Pantheon DEV site environment
- `terminus-create-site`: Quickly spin up a Quickstart 3 site in Pantheon
- `terminus-get-update-status`: Determine whether upstream updates are available for one or all DEV sites
- `terminus-update-dev`: Uses terminus + drush to apply Arizona Quickstart 3 upstream & Config Distro updates
- `terminus-update-test`: Uses terminus to pull updates from `dev`, apply Config Distro updates, and clone database and files from `live`
- `terminus-update-live`: Uses terminus to pull updates from `test` and apply Config Distro updates

## Requirements

- `bash`, `zsh`, or other shell environment
- A working installation of [terminus](https://pantheon.io/docs/terminus)

## Usage

### Update a single site

```sh
# Update a dev site
$ SITE_NAME=azgrad-mysite terminus-update-dev

# Update a test site
$ SITE_NAME=azgrad-mysite terminus-update-test

# Update a live site
$ SITE_NAME=azgrad-mysite terminus-update-live
```

### Update all sites

Execute any one of these scripts against all sites from the command-line:

```sh
# Update all dev sites
$ terminus site:list --field=name | sort | xargs -I % sh -c 'SITE_NAME=% terminus-update-dev'

# Update all test sites
$ terminus site:list --field=name | sort | xargs -I % sh -c 'SITE_NAME=% terminus-update-test'

# Update all live sites
$ terminus site:list --field=name | sort | xargs -I % sh -c 'SITE_NAME=% terminus-update-live'
```

