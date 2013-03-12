# httperf cookbook

This cookbook can be included using Berkshelf or another library management tool by adding the following:

    # Berkshelf example
    cookbook "COOKBOOK_NAME", git: "git://github.com/rubyops/cookbook-COOKBOOK_NAME.git", branch: "master"

# Requirements

* [build-essentials](http://community.opscode.com/cookbooks/build-essential)
* [yum](http://community.opscode.com/cookbooks/yum)

## This has been tested on:

* CentOS 6.2
* CentOS 6.3
* Ubuntu 10.04.4 LTS (lucid64)

# Usage

    // file: nodes/host.json
    {
        // Required for build-essential.
        //
        // See build-essential docs for custom configs,
        // empty configs as below are acceptable for
        // defaults.
        "build_essential": {},

        // Include ruby recipe.
        "run_list": [ "recipe[ruby::source]" ]
    }

# Attributes

    // file: nodes/host.json
    {
       "ruby": {
           // defaults shown here
           "ruby_version":     "1.9.3-p392",
           "rubygems_version": "1.8.24",
           "source_location":  "http://ftp.ruby-lang.org/pub/ruby/1.9",

         /*
           for 2.0 variants
           "source_location":  "http://ftp.ruby-lang.org/pub/ruby/2.0",

           for 1.8 variants
           "source_location":  "http://ftp.ruby-lang.org/pub/ruby/1.8",

           both are untested
         */

           "source_cache_dir": "/usr/local/src",
           "destination_dir":  "/usr/local/bin"
       }
    }

# Author

Author:: Joshua P. Mervine (<joshua@mervine.net>)
