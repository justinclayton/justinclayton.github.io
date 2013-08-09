require 'fileutils'

include FileUtils

$post_boilerblate = <<-POST_BOILERBLATE
---
layout: post
title:      #{ENV['title']}
date:       #{Time.now}
tags:
---

Lorum Ipsum Or Something.

Example code:

{% highlight ruby linenos %}
EXAMPLE.code ||= 42
{% endhighlight %}

Ipso Facto {{ page.title }}.
POST_BOILERBLATE

desc 'Start new post (e.g. rake new_post title="How To Do That Thing" markup="md")'
task :new_post do
  create_file post_filename, $post_boilerblate
end

desc 'Promote a draft post to be a real boy (e.g. rake publish post="./_drafts/2013-01-01-how-to-do-that-thing.md")'
task :publish do
  # move draft post from _drafts into _posts
  # rename file to today's date
  # update date inside of post to Time.now
end

def post_filename
  # need to return filename in this format:
  # 2013-06-04-how-i-learned-to-stop-worrying-and-love-the-cloud.md
  date  = Time.now.strftime('%Y-%m-%d')
  if ENV['title']
    title = ENV['title'].downcase
    title.gsub!(/\s+/, '-')
    # title.gsub!(/\W+/, '')
  else
    fail 'error: must specify title, like this: rake new_post title="How To Do That Thing" markup="md"'
  end
  extension = (ENV['markup'] or 'md')

  return date + '-' + title + '.' + extension
end

def create_file(filename, contents)
  file = File.expand_path File.join('_drafts', filename)
  dir  =  Pathname.new(file).dirname.to_s
  # mkdir_p dir
  if File.exists? file
    puts " * #{file} already exists"
  else
    puts " + #{file}"
    File.open(file, 'w') { |f| f.write contents }
  end
end
