# Puppet module: msmtp

## DEPRECATION NOTICE
This module is no more actively maintained and will hardly be updated.

Please find an alternative module from other authors or consider [Tiny Puppet](https://github.com/example42/puppet-tp) as replacement.

If you want to maintain this module, contact [Alessandro Franceschi](https://github.com/alvagante)


This is a Puppet module for msmtp
It provides only package installation and file configuration.

Based on Example42 layouts by Alessandro Franceschi / Lab42

Official site: http://www.example42.com

Official git repository: http://github.com/example42/puppet-msmtp

Released under the terms of Apache 2 License.

This module requires the presence of Example42 Puppi module in your modulepath.


## USAGE - Basic management

* Install msmtp with default settings

        class { 'msmtp': }

* Install a specific version of msmtp package

        class { 'msmtp':
          version => '1.0.1',
        }

* Remove msmtp resources

        class { 'msmtp':
          absent => true
        }

* Enable auditing without without making changes on existing msmtp configuration *files*

        class { 'msmtp':
          audit_only => true
        }

* Module dry-run: Do not make any change on *all* the resources provided by the module

        class { 'standard42':
          noops => true
        }


## USAGE - Overrides and Customizations
* Use custom sources for main config file 

        class { 'msmtp':
          source => [ "puppet:///modules/example42/msmtp/msmtp.conf-${hostname}" , "puppet:///modules/example42/msmtp/msmtp.conf" ], 
        }


* Use custom template for main config file. Note that template and source arguments are alternative. 

        class { 'msmtp':
          template => 'example42/msmtp/msmtp.conf.erb',
        }

* Automatically include a custom subclass

        class { 'msmtp':
          my_class => 'example42::my_msmtp',
        }



[![Build Status](https://travis-ci.org/example42/puppet-msmtp.png?branch=master)](https://travis-ci.org/example42/puppet-msmtp)
