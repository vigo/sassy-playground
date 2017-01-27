require "bundler/setup"

task :default => ["run"]

SASS_SOURCE = "css/application.scss"
CSS_TARGET = "public/css/application.css"

desc "Run development server"
task :run, [:port] do |t, args|
  args.with_defaults(port: "5555")
  actions = [
    Process.spawn("guard start -i"),
    Process.spawn("sass --watch #{SASS_SOURCE}:#{CSS_TARGET} --style compressed"),
    Process.spawn("ruby -run -e httpd . -p #{args.port}"),
  ]  
  trap("INT") {
    actions.each{ |pid| Process.kill(9, pid) rescue Errno::ESRCH }
    exit 0
  }
  actions.each { |pid| Process.wait(pid) }
end
