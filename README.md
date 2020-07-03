# JETTINGS

Jettings is a super simple JSON based settings file manager.
Jettings will help you quick start your python projects.
With Jettings you can quickly:

- Create a jettings file
- Store a jetting value in that file
- Retrieve a jetting value from that file
- Delete a jetting value in that file

You can have as many jetting files as you need for your application.
Each Jettings file you create will store your settings as readable JSON.

## USAGE

## First Import Jettings
    from jettings import Jettings
## Create a Jettings file
    app_settings=Jettings("~/.yourappsettings/settings.cfg")
## Add a jetting value using sets
    app_settings.sets(['myFirstJetting'],'1')
## Retrieve a jetting value using gets
    a_jettings_value=app_settings.gets(['myFirstJetting'])
## Delete a jetting value using dels
    app_settings.dels(['myFirstJetting'])


# NESTED JETTINGS 

You can also create nested jettings.
Jettings simplifies key nesting by using the following syntax:

    ['key1','key2','key3'] 

which is equivalent to the JSON form

    ['key1']['key2']['key3']

The jettings key format should help you manage your keys 
using python lists.

## Add nested jettings using sets
    app_settings.sets(['Customers','1','firstname'],'John')
    app_settings.sets(['Customers','1','secondname'], 'Johnson')
    app_settings.sets(['Customers','2','firstname'],'Julie')
    app_settings.sets(['Customers','2','secondname'],'Julieson')



## Retrieve a nested jetting using gets
    a_jettings_value=app_settings.gets(['Customers','2','firstname'])

## Retrieve a dictionary jetting of nested jettings by using gets
    a_jettings_dict=app_settings.gets(['Customers','1'])

## Delete a nested jetting by using dels
    app_settings.dels(['Customers','1'])

## Check if a jetting exists.
    does_this_jetting_exist=app_settings.exists(['Customers','1'])
