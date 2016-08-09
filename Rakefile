require 'pathname'
require 'rsync'

desc "Deploys website"
task :deploy, [:user_host] do |task, args|

  site_path = (Pathname(File.dirname(__FILE__)) + '_site/').to_s

  system(%Q{jekyll build})
  system(%Q{rsync -avz "ssh -o StrictHostKeyChecking=no --progress" #{site_path} #{args[:user_host]}:/var/www/html/ntis-gov})
end
