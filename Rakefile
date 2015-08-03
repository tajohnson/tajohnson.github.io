desc "Recompile Sass"
task :recompile_sass do
  puts "\n## Forcing Sass to recompile"
  status = system("touch -m css/application.scss")
  puts status ? "Success" : "Failed"
end

namespace :build do
  desc "Build _site/ for development"
  task :dev => :recompile_sass do
    puts "\n##  Starting Jekyll and recompiling Sass with source map"
    pids = [
      spawn("sass --sourcemap --watch css/application.scss:css/application.css"),
      spawn("jekyll serve -w")
    ]

    trap "INT" do
      Process.kill "INT", *pids
      exit 1
    end

    loop do
      sleep 1
    end
  end

  desc "Build _site/ for production"
  task :pro => :recompile_sass do
    puts "\n## Compiling Sass"
    status = system("sass --style compressed css/application.scss:css/application.css")
    puts status ? "Success" : "Failed"
    puts "\n## Building Jekyll to _site/"
    status = system("jekyll build")
    puts status ? "Success" : "Failed"
    Rake::Task["minify"].invoke
    puts "\n## Deleting Sass source map"
    status = system("rm -f _site/assets/css/*.map")
    puts status ? "Success" : "Failed"
  end
end

