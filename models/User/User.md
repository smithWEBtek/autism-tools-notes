<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

**Table of Contents** _generated with [DocToc](https://github.com/thlorenz/doctoc)_

- [FEATURE: User](#feature-user)
  - [description and user stories](#description-and-user-stories)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: User

data model

## description and user stories

- the user model holds all people
- a user has a user_type, in relation to the main user: the client_user

### columns

t.text :first_name
t.text :last_name
t.text :middle_name
t.text :nick_name
t.text :email
t.text :phone
t.text :address1
t.text :address2
t.text :address3
t.text :address_city
t.text :address_state
t.text :address_zip
t.text :age
t.text :weight
t.text :height
t.text :eyes_color
t.text :hair_color
t.text :description
t.text :diagnosis

### migration

rails g resource User first_name:text last_name:text middle_name:text nick_name:text email:text phone:text address1:text address2:text address3:text address_city:text address_state:text address_zip:text age:text weight:text height:text eyes_color:text hair_color:text description:text diagnosis:text

### ar relationships

### serializer
