require "rubygems"
require "tmpdir"

require "bundler/setup"
require "jekyll"


# Change your GitHub reponame
GITHUB_REPONAME = "mavenhive/mavenhive.github.io"


desc "Generate blog files"
task :generate do
  Jekyll::Site.new(Jekyll.configuration({
    "source"      => ".",
    "destination" => "_site"
  })).process
end


desc "Generate and publish blog to gh-pages"
task :publish => [:generate] do
  Dir.mktmpdir do |tmp|
    puts "Working in tmp dir: #{tmp}"
    pwd = Dir.pwd

    cp_r "#{pwd}/.git", tmp

    Dir.chdir tmp
    system "git reset -q && git checkout -q . && git clean -dfq"
    system "git checkout master"
    system "git pull origin master"

    cp_r "#{pwd}/_site/.", tmp
    system "git add ."

    message = "Site updated at #{Time.now.utc}"
    system "git commit -q -m #{message.inspect}"
    system "git push origin master"

    Dir.chdir pwd
  end
end
