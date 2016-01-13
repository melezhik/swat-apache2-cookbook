# SYNOPSIS

[swat](https://github.com/melezhik/swat) smoke/integration tests for [apache2 cookbook](https://github.com/chef-cookbooks/apache2)

# Check list

* verify that `GET /` request succeeds
* verify that apache footprint exists in server response

# Sample Output

    C:\Users\melezal1\projects\apache2>kitchen verify swat
    -----> Starting Kitchen (v1.4.2)
    C:/opscode/chefdk/embedded/lib/ruby/gems/2.1.0/gems/httpclient-2.6.0.1/lib/httpclient/webagent-cookie.rb:458: warning: already initialized constant HTTPClient::CookieManager
    C:/opscode/chefdk/embedded/lib/ruby/gems/2.1.0/gems/httpclient-2.6.0.1/lib/httpclient/cookie.rb:8: warning: previous definition of CookieManager was here                   02:56-----> Verifying <swat-centos-65>...
           Preparing files for transfer
    -----> Busser installation detected (busser)
           Installing Busser plugins: busser-bash
           Plugin bash already installed
           Removing /tmp/verifier/suites/bash
           Transferring files to <swat-centos-65>
    -----> Running bash test suite
    -----> [bash] swat_test.bash
           Package perl-Test-Harness-3.17-141.el6_7.1.x86_64 already installed and latest version
           Sparrow is up to date. (0.0.13)
           get index updates from SparrowHub ...
           public@swat-apache2-cookbook is uptodate (0.0.2)
           project foo already exists - nothing to do here ...
    
           checkpoint foo/apache already exists at /usr/local/share/perl5/Sparrow/Commands/CheckPoint.pm line 39
            Sparrow::Commands::CheckPoint::check_add('foo', 'apache') called at /usr/local/bin/sparrow line 123
           set base_url
    
           set plugin to public@swat-apache2-cookbook
    
           # running export swat_my=/root/sparrow/projects/foo/checkpoints/apache/swat.my && cd /root/sparrow/plugins/public/swat-apache2-cookbook && carton exec 'swat ./ working.computers.biz' ...
    
           /root/.swat/.cache/10747/prove/00.GET.t ..
           ok 1 - GET working.computers.biz/ succeeded
           # response saved to /root/.swat/.cache/10747/prove/SgXPxMuuCG
           ok 2 - output match '200 OK'
           ok 3 - output match /Server: Apache/
           1..3
           ok
           All tests successful.
           Files=1, Tests=3,  0 wallclock secs ( 0.01 usr  0.00 sys +  0.04 cusr  0.00 csys =  0.05 CPU)
           Result: PASS
           Finished verifying <swat-centos-65> (0m5.95s).
    -----> Kitchen is finished. (0m10.46s)
    
# AUTHOR

[Alexey Melezhik](mailto:melezhik@gmail.com)


