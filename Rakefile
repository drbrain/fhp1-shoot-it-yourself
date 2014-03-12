# move to gem, or at least into /lib
def sluggify(text, separator="-")
  text.downcase.gsub(/_|\s|\W/, separator).gsub(/-{2,}/, separator).gsub(/(-)+$/, "")
end


desc "Default task. Run with `rake`"
task default: ["book"]

desc "Builds the whole book"
task book: ["book:table_of_contents", "book:pages", "book:vars"]

namespace :book do
  desc "Creates the table of contents for the book"
  task :table_of_contents do

    File.open("pages.txt", "r").each_line do |line|
      page_title = line.chomp
      page_slug  = sluggify(page_title)

      puts page_title
      puts page_slug
      puts
    end

    # puts "book:table_of_contents - creates the table of contents for the book"
    # File.open(local_filename, 'w') { |f| f.write(doc) }
  end

  desc "Creates the pages for the book"
  task :pages do
    puts "book:pages - creates the pages for the book"
    # File.open(local_filename, 'w') { |f| f.write(doc) }
  end

  desc "Prints variables for the book"
  task :vars do
    require 'yaml'
    meta = YAML.load_file('meta.yml')
    require "pp"; pp meta
  end
end