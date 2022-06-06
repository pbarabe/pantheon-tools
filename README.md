# Pantheon Tools for QS2 Site Maintenance

- `terminus-update-dev`: Uses terminus + drush to apply Arizona Quickstart 2 upstream & Config Distro updates
- `terminus-update-test`: Uses terminus to pull updates from `dev` and clone database and files from `live`
- `terminus-update-live`: Users terminus to pull updates from `test`

You can execute any one of these scripts again all sites from the command-line:

```sh
# Update all dev sites
terminus site:list --field=name | xargs -I % sh -c 'SITE_NAME=% terminus-update-dev'

# Update all test sites
$ terminus site:list --field=name | xargs -I % sh -c 'SITE_NAME=% terminus-update-dev'

# Update all live sites
$ terminus site:list --field=name | xargs -I % sh -c 'SITE_NAME=% terminus-update-dev'
```

