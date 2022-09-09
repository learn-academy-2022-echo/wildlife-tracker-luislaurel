<!-- Setup -->
cd Desktop
rails new wildlife_api -d postgresql - T
cd wildlife_api
rails db:create
git remote add
code .
git status
git add .
git commit -m
git push origin main
bundle add rspec-rails
rails g rspec:install
rails s

rails generate resource Animal common_name:string scientific_binomial:string

rail routes -E
rails db:migrate
delete views folder


skip_before_action :verify_authenticity_token add to application_controller.rb
<!-- End Setup -->







Story 1: In order to track wildlife sightings, as a user of the API, I need to manage animals.

Branch: animal-crud-actions

Acceptance Criteria

<!-- Create a resource for animal with the following information: common name and scientific binomial  -->
```ruby

 def index
        animals = Animal.all
        render json:animals
    end

```

<!-- Can see the data response of all the animals -->
```ruby

  def show
        animal = Animal.find(params[:id])
        render json: animal
    end

```
<!-- Can create a new animal in the database -->
```ruby
 def create
        animal = Animal.create(animal_params)
           if animal.valid?
            render json: animal
          else
            render json: animal.errors
        end
    end
```
<!-- Can update an existing animal in the database -->
```ruby
 def update
        animal = Animal.find(params[:id])
        animal.update(animal_params)
          if animal.valid?
            render json: animal
          else
            render json: animal.errors
        end
    end

```


<!-- Can remove an animal entry in the database -->

```ruby

def destroy
        animal = Animal.find(params[:id])
        if animal.destroy
            render json: animal
        else 
            render json: animal.errors
        end
    end

```



































--[ Route 1 ]-------------------------------------------------------------------
Prefix            | animals
Verb              | GET
URI               | /animals(.:format)
Controller#Action | animals#index
--[ Route 2 ]-------------------------------------------------------------------
Prefix            | 
Verb              | POST
URI               | /animals(.:format)
Controller#Action | animals#create
--[ Route 3 ]-------------------------------------------------------------------
Prefix            | new_animal
Verb              | GET
URI               | /animals/new(.:format)
Controller#Action | animals#new
--[ Route 4 ]-------------------------------------------------------------------
Prefix            | edit_animal
Verb              | GET
URI               | /animals/:id/edit(.:format)
Controller#Action | animals#edit
--[ Route 5 ]-------------------------------------------------------------------
Prefix            | animal
Verb              | GET
URI               | /animals/:id(.:format)
Controller#Action | animals#show
--[ Route 6 ]-------------------------------------------------------------------
Prefix            | 
Verb              | PATCH
URI               | /animals/:id(.:format)
Controller#Action | animals#update
--[ Route 7 ]-------------------------------------------------------------------
Prefix            | 
Verb              | PUT
URI               | /animals/:id(.:format)
Controller#Action | animals#update
--[ Route 8 ]-------------------------------------------------------------------
Prefix            | 
Verb              | DELETE
URI               | /animals/:id(.:format)
Controller#Action | animals#destroy
--[ Route 9 ]-------------------------------------------------------------------

<!-- Animals  -->
Gavial or Gharial

Gavialis gangeticus



Buffalo

Babalus bubalis



