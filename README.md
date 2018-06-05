# ansible-rails-pg

[![Contributors](https://img.shields.io/github/contributors/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/graphs/contributors)
[![GitHub last commit (branch)](https://img.shields.io/github/last-commit/eendroroy/ansible-rails-pg/master.svg)](https://github.com/eendroroy/ansible-rails-pg)
[![license](https://img.shields.io/github/license/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/blob/master/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/issues)
[![GitHub closed issues](https://img.shields.io/github/issues-closed/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/issues?q=is%3Aissue+is%3Aclosed)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/pulls)
[![GitHub closed pull requests](https://img.shields.io/github/issues-pr-closed/eendroroy/ansible-rails-pg.svg)](https://github.com/eendroroy/ansible-rails-pg/pulls?q=is%3Apr+is%3Aclosed)

Setup environment for deploying rails application on a `Debian` or `RPM based` os
(`Debian`, `Ubuntu`, `RHEL`, `CentOS`, `Fedora`).
Base repo needs to be enabled using `subscription-manager` on `RHEL`.

## Description

Works on Debian and RedHat os family.

Tested on `Ubuntu 14.04`, `Ubuntu 16.04`, `CentOS 7`, and `RedHat 7`

- System wide `rbenv` installation with ruby 2.5.0 and bundler gem
- PostgreSQL 10 with environment specific (staging or production) database and user with default configuration
- Nginx with minimal configuration (application specific configurations can be uploaded during rails application deployment).
  See [puma-deploy](https://github.com/eendroroy/puma-deploy)
- Some common dependencies required for rails applications
- Create deploy user with ssh access and specific sudo permission required to deploy rails application

A sample Vagrantfile is included to test the playbook (Ubuntu 16.04 and CentOS 7)

## Variables

```bash
# group_vars/all.yml
ruby_version: 2.5.0
deploy_user:  deployer
app_name:     application
deploy_path:  '/apps'
app_env:      staging

databases:
  - { db_name: '{{ app_name }}_production', db_user: 'production_user', db_password: 'production_pass' }
  - { db_name: '{{ app_name }}_staging',    db_user: 'staging_user',    db_password: 'staging_pass' }

postgres_data_dir:       /var/lib/postgres/databases
postgres_listen_address: '*'
postgres_port:           5432
```

See here: [group_vars/all.yml](group_vars/all.yml)

## Contributing

Bug reports and pull requests are welcome on GitHub at [ansible-rails-pg repository](https://github.com/eendroroy/ansible-rails-pg). 
This project is intended to be a safe, welcoming space for collaboration,
and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Authors

* **indrajit** - *Owner* - [eendroroy](https://github.com/eendroroy)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

