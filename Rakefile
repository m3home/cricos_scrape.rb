require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new

require_relative 'lib/cricos_scrape'
namespace :import do
  
  task :institutions do
    file_output = {
      'data' => ENV['OUTPUT_DATA_FILE'] || 'institutions.json',
      'id' => ENV['OUTPUT_ID_FILE'] || 'last_institution_id.json'
    }

    min_id     = ENV['MIN_ID'] || 1
    max_id     = ENV['MAX_ID'] || 10000
    file_input = ENV['FILE_INPUT']

    CricosScrape::BulkImportInstitutions::new(file_output ,min_id, max_id, file_input).perform
  end

  task :courses do
    file_output = {
      'data' => ENV['OUTPUT_DATA_FILE'] || 'courses.json',
      'id' => ENV['OUTPUT_ID_FILE'] || 'last_course_id.json'
    }

    min_id     = ENV['MIN_ID'] || 1
    max_id     = ENV['MAX_ID'] || 10000
    file_input = ENV['FILE_INPUT']

    CricosScrape::BulkImportCourses::new(file_output ,min_id, max_id, file_input).perform
  end

  task :contacts do
    output_file  = ENV['OUTPUT_FILE'] || 'contacts.json'
    CricosScrape::BulkImportContacts::new(output_file, ENV['OVERWRITE']).perform
  end

end