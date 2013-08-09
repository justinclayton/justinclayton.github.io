---
layout: post
title:      Use rspec-puppet To Organize Your Work
date:       2013-08-09 12:35:24 -0700
tags:
---

Use test-writing as your tasklist at the very start of your project!

{% highlight bash %}
$ rake spec

...*********.

Pending:
  getty::mms::job_server should create the app user
    # havent started yet
    # ./spec/classes/mms/job_server_spec.rb:5
  getty::mms::job_server should give the app user sudo access
    # havent started yet
    # ./spec/classes/mms/job_server_spec.rb:9
  getty::mms::job_server should install some sort of java
    # needs investigation
    # ./spec/classes/mms/job_server_spec.rb:12
  getty::mms::job_server should mount the sharedProcessingArea nfs share
    # havent started yet
    # ./spec/classes/mms/job_server_spec.rb:16
  getty::mms::job_server should install a bunch of language packs and fonts, i guess
    # needs investigation
    # ./spec/classes/mms/job_server_spec.rb:20
  getty::mms::job_server should ulimit for open files 90000
    # havent started yet
    # ./spec/classes/mms/job_server_spec.rb:25
  getty::mms::job_server might need to do some MTA config
    # needs investigation
    # ./spec/classes/mms/job_server_spec.rb:28
  getty::mms::job_server should have jamin's imagemagick
    # havent started yet
    # ./spec/classes/mms/job_server_spec.rb:32
  getty::mms::job_server needs epel but i dont know why
    # needs investigation
    # ./spec/classes/mms/job_server_spec.rb:35

Finished in 2.96 seconds
13 examples, 0 failures, 9 pending
{% endhighlight %}

Ipso Facto {{ page.title }}.
