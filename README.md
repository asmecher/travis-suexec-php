travis-suexec-php
=================

This repository demonstrates how to configure Travis to execute PHP scripts using suEXEC and FastCGI. This permits PHP scripts to run under the "travis" account, rather than the default www-data used in a typical mod_cgi environment.

This can be important e.g. if you're mixing unit tests (invoked via phpunit from the command line, thus running as the "travis" user) and integration tests using a tool like Selenium (invoked via the web server, thus normally running as the "www-data" user). This configuration permits both methods to run under the same user account.

This setup modifies the Apache2 configuration to relocate the web root into the repository directory.

To use this in your project, bring the commands from .travis.yml into your project. No additional files are required.
