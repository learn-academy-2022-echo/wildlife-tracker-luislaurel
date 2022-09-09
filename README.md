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
<!-- End of Story 1 -->


<!-- Start Story 2 -->



git checkout -b sighting-crud-actions


Story 2: In order to track wildlife sightings, as a user of the API, I need to manage animal sightings.

Branch: sighting-crud-actions

Acceptance Criteria

Create a resource for animal sightings with the following information: latitude, longitude, date

<!-- Setup / Create Associations -->


rails generate resource Sighting animal_id:integer latitude:float longitude:float date:date

<!-- class Sighting < ApplicationRecord
    belongs_to :animal
end

class Animal < ApplicationRecord
    has_many :sightings
end -->



Hint: An animal has_many sightings (rails g resource Sighting animal_id:integer ...)
Hint: Date is written in Active Record as yyyy-mm-dd (“2022-07-28")
date:YYMMDD
Can create a new animal sighting in the database

Can update an existing animal sighting in the database
Can remove an animal sighting in the database


































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

 "common_name": "Buffalo",
    "scientific_binomial": "Babalus bubalis"
Bulbul

Molpastes cafer

Koel

Eudynamis scolopaccus

Pigeon

Columba livia
 "common_name": "Pigeon",
    "scientific_binomial": "Columba livia"

Indian Cobra

Naja naja

King cobra

Ophiophagus hannah

    "common_name": "King Cobra",
    "scientific_binomial": "Ophiophagus hannah"
Sea snake

Hydrophiinae
    "common_name": "Sea snake",
    "scientific_binomial": "Hydrophiinae"
Indian Python (Ajgar)

Python molurus
 "common_name": "Indian Python",
    "scientific_binomial": "Python molurus"