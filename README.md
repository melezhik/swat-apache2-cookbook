# SYNOPSIS

[swat](https://github.com/melezhik/swat) smoke/integration tests for [apache2 cookbook](https://github.com/chef-cookbooks/apache2)

# Check list

* verify that landing page request (`GET /`)  succeeds
* verify that apache footprint exists in server response
* verify that given string exists at landing page

# Environment variables

* landing_page_line - optional. verify that given string exists at landing page 

Example:

    landing_page_line="Hello World"


# Sample output

    $ kitchen verify swat-debian                                                                                                               10:32-----> Starting Kitchen (v1.4.2)
    -----> Verifying <swat-debian-76>...
           Preparing files for transfer
    -----> Busser installation detected (busser)
           Installing Busser plugins: busser-bash
           Plugin bash already installed
           Removing /tmp/verifier/suites/bash
           Transferring files to <swat-debian-76>
    -----> Running bash test suite
    -----> [bash] swat_test.bash
           project foo already exists - nothing to do here ...
    
           checkpoint foo/apache already exists at /usr/local/share/perl/5.14.2/Sparrow/Commands/CheckPoint.pm line 39
            Sparrow::Commands::CheckPoint::check_add('foo', 'apache') called at /usr/local/bin/sparrow line 123
           set base_url
    
           set plugin to public@swat-apache2-cookbook
    
           # running export swat_my=/home/vagrant/sparrow/projects/foo/checkpoints/apache/swat.my && cd /home/vagrant/sparrow/plugins/public/swat-apache2-cookbook && carton exec 'swat ./ working.computers.biz' ...
    
           /home/vagrant/.swat/.cache/18283/prove/00.GET.t ..
           ok 1 - GET working.computers.biz/ succeeded
           # response saved to /home/vagrant/.swat/.cache/18283/prove/drIQlxuYOf
           ok 2 - output match '200 OK'
           ok 3 - output match /Server: Apache/
           ok 4 - output match 'Hello World'
           1..4
           ok
           All tests successful.
           Files=1, Tests=4,  0 wallclock secs ( 0.01 usr  0.01 sys +  0.04 cusr  0.00 csys =  0.06 CPU)
           Result: PASS
           Finished verifying <swat-debian-76> (0m14.54s).
    -----> Kitchen is finished. (0m19.20s)
    zlib(finalizer): the stream was freed prematurely.
        
# Author

[Alexey Melezhik](mailto:melezhik@gmail.com)


