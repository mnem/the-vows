require 'json'

desc "Copy all bower files to the appropriate _site subfolders"
task :bower_copy do
    # Grab all the bower components paths
    paths = JSON.parse `bower list --paths --json`

    # How extensions to _site folders
    FILE_MAP = {
        /\.css$/ => 'css',
        /\.js$/ => 'js',
    }

    # Copy them
    paths.each do |mod, files|
        files.each do |file|
            FILE_MAP.each { |regex, dir| cp file, "#{dir}" if regex === file }
        end
    end
end
