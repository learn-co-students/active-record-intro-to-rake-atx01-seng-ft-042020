namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do
    puts "hola de Rake!"
  end

end


task :environment do
  require_relative './config/environment'
end

desc 'drop into the pry console'
task :console => :environment do
  Pry.start
end

namespace :db do
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'  
  end

  desc 'drop table from database'
  task :drop_table => :environment do
    Student.drop_table
  end

  desc 'show all rows in table'
  task :show_rows => :environment do
    Student.all.each do |student|
      puts "     ID: #{student[0]}"
      puts "   NAME: #{student[1]}"
      puts "  GRADE: #{student[2]}"
      puts 
    end

  end
end


