require 'json'
require 'rake/clean'

CLEAN.include '.sass-cache'
CLOBBER.include '_site'

desc "Copy all bower files to the appropriate _site subfolders"
task :bower_copy do
    # Grab all the bower components paths
    paths = JSON.parse `bower list --paths --json`

    # How extensions to _site folders
    FILE_MAP = {
        /\.css$/ => 'css',
        /\.js$/ => 'js',
    }

    # Convenience lambda
    copy_to_subfolder = lambda do |file|
        FILE_MAP.each { |regex, dir| cp file, "#{dir}" if regex === file }
    end

    # Copy them
    paths.each do |mod, path|
        if path.kind_of? Array
            path.each do |p|
                copy_to_subfolder.call p
            end
        else
            copy_to_subfolder.call path
        end
    end
end
