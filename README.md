RailsAdminPdf Gem (Engine)
========

PDF Builder for RailsAdmin.

Installation
========

* Add to Gemfile and bundle install:

        gem "rails_admin_pdf", :git => "git://github.com/stephskardal/rails_admin_pdf.git"

* Add prawn to your main application, and create "#{class}Report" for every class that you would like to export.

```ruby
class OrderReport < Prawn::Document
  def to_pdf(object)
    # PDF content #
    render
  end
end
```

* If applicable, add right to :pdf action in CanCan ability class

* add action into rails_admin initializer

```ruby
config.actions do
  # root actions
  dashboard                     # mandatory
  # collection actions 
  index                         # mandatory
  new
  export
  history_index
  bulk_delete
  # member actions
  show
  edit
  delete
  history_show
  show_in_app
  pdf # RailsAdminPdf action
end
```

Usage
========


Copyright
========

Copyright (c) 2012 End Point & Steph Skardal. 
