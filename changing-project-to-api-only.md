alterando projeto para ser api only
config/application.rb - `config.api_only = true`

config/enviroments/development - `config.debug_exception_response_format = :api`

app/controller/application_controller.rb - `class ApplicationController < ActionController::API`

http://edgeguides.rubyonrails.org/api_app.html#changing-an-existing-application
