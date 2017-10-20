# ansible-rails-pg

Setup environment for deploying rails application on a RPM based os (RHEL, CentOS, Fedora).
On RHEL base repo needs to be enabled using `subscription-manager`.

## Features

- System wide `rbenv` installation with ruby 2.4.2 and bundler gem
- PostgreSQL 10 with environment specific (staging or production) database and user with default configuration
- Nginx with minimal configuration (application specific configurations should be uploaded during rails application deployment). see [puma-deploy](https://github.com/puma-deploy)
- Some common dependencies required for rails applications
- Create deploy user with ssh access and specific sudo permission required to deploy rails application
- A sample Vagrantfile to test the playbook (on CentOS)

## Contributing

Bug reports and pull requests are welcome on GitHub at [ansible-rails-pg repository](https://github.com/eendroroy/ansible-rails-pg). 
This project is intended to be a safe, welcoming space for collaboration,
and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## Authors

* **indrajit** - *Owner* - [eendroroy](https://github.com/eendroroy)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

