# User Model

|Field  			 | Type |        |
|--------------|------|--------|
| name  			       | string  |
| email 			       | string  |
| url                | string  |
| password_digest	   | string  |
| admin 			       | boolean |

## Overview
The user model.

## Stories Covered
* As a user I want my password encrypted before being saved into the database
* As a user I want validations so that I do not forget any important information when creating my account


## Creating the Model
Before we start any major changes we should switch to a topic branch as explained in the git section of this book.

	$ git checkout -b add_users

Next using the table of attributes above we will created the user model

	$ rails g model user name email url password_digest admin:boolean

This will create a model at `app/models/user.rb` and a migration for the user attributes.

Next we need to run the migration to create the database table.

	$ rake db:migrate

Then open user model in `app/models/users`. Inside you will find a empty class. This is a good starting place. The next step is to add vaildations. But first we will need to add test.

T> ## Commit early and commit often!
T>
T>	$ git commit -m "Generated user model and migrations were ran."

### Test Setup
We will setup the tests for the user model. First we will create a user that will be used in the tests.

  require 'spec_helper'

  describe User do
    before do
      @user = User.new(name: 'Steve Jobs', email: 'stevejobs@apple.com',  password: 'stevejobs123', password_confirmation: 'stevejobs123')
    end

Next we will set the `subject` of the test. Setting the subject of the test easier to test.

    subject { @user }

Next we make sure that the test user is valid. It the test user is not valid it will make all of the other tests useless. In RSpec a test in wrapped in an `it` block. In this test we are using a one-liner `it` block. Inside the it block we are using the `should` method. Then we passed in the `be_valid` method. This test check if user object passes the validations defined in the validations.

    it { should be_valid }

Next we going write test make sure that the model has the proper attirbutes. First we will test the name. We will you use the `should` method again along with the `respond_to` method. The repsond method takes an method the will called on the object. When should with the `should` method the test will pass when the method given doesn't return in no method error. We will first do with the name.

  it { should respond_to(:name) }

The above method is the equivalent of calling `@user.name`. Which would return `Steve Jobs`. Next we will add tests for email, url, admin and, password.

    it { should respond_to(:email) }
    it { should respond_to(:password_digest) }
    it { should respond_to(:password) }