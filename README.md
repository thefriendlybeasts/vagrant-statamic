# vagrant-statamic
The Friendly Beasts' Vagrant setup.

## Provisions
- ubuntu/trusty64
- Apache2
- PHP5 (latest)
- Configured php.ini and apache2.conf

## Requirements
- VirtualBox
- Vagrant

## Usage
1. Place `Vagrantfile` above your site's root.
2. `vagrant up` in your project dir.

By default, this will sync `html` to your Vagrant machine. You can change the default by editing this line:

```ruby
ENV['SYNCED_FOLDER'] = "./html"
```

You can also sync a different folder on a per-case basis. Just define an environment variable before `vagrant up`.

For example, after we run our Grunt build script, we end up with a `dist` dir next to `html`. To review the built version of the site before deploying, we run:

```bash
SYNCED_FOLDER="./dist" vagrant up
```

If you've already `vagrant up`ped, it's significantly quicker to reload, than to destroy and re-up.

```bash
SYNCED_FOLDER="./dist" vagrant reload
