## Drupal Workshops:

### Acquia

- Drupal 8 in a Day

### Blisstering Software

- Building Front-end /Mobile Application using Headless Drupal 8

- Prateek Jain
- Swarad Mokal
- Aditya Ghan

### Benefits of going Headless :




### Considerations before going to Headless :

 - Routing : URLS , Clean URLS , Navigations
 - caching & aggregation : Page , Block, CSS , JS
 - Templating : data wrapped in HTML Templates
 - Interactivity : Forms, Authentication, permissions
 - Public API: Authentication


 ### Challenges :
 - Performance
 - SEO
 - Theme Layer and render pipeline
   - ( Drupal supports big pipe( Facebooks) out-of-box)
 - Security vulnerablity


### Architecture Considerations:

### Models :

- Traditional:
     CMS -> Renderer -> Page

- Fully Decoupled
    CMS -> Endpoints -> Page  

- Progressively Decoupled

    CMS -> Renderer -> Page
    CMS -> Endpoints -> Pages

    e.g [http://www.weather.com](http://www.weather.com) is an good example built on Drupal

    ### Hands On TODO Application

    -Install Drupal 8

    -Create TODO content type

      - added Todo
      - added boolean complete


    -Install admin toolbar

    -Install rest ui

    - nodejs already installed.

    - hal_json , with self discovery  

    - give permission
       -- Patch is unique to php frameworks
    - install DHC client

    localhost:8888/drupal-8.0.3/node/1
      => gets you a raw html

    - localhost:8888/drupal-8.0.3/node/1?_format=hal_json

    This will return 403 forbidden

    -  you need to set permissions to content to enable this.

    - set Authorization header as well

     you set this by giving admin user name/ password

     This should get your web request to work


     -- TODO a POST

 Fetch token first

 send out a POST

 Body :

     {
   "_links":{
     "type":{
       "href":"http://localhost:8888/drupal-8.0.3/rest/type/node/todo"
     }
   },
   "title":[
     {
       "value":"My second todo."
     }
   ],
   "field_complete":[
   {
       "value": "0"
   }
 ]
}

There is bug with Authentication (8.0)

using patch it has to be fixed

'''
swarad07 [12:28 PM]
https://www.drupal.org/node/2228141
Problem/Motivation Currently, the only way to add authentication to a REST View is through RouteSubscriberBase->alterRoutes(). We could add the Authentication setting to REST Views so users could select the supported authentication methods for a particular Views display. It would look like the following screenshot:

[12:29]
https://www.drupal.org/files/issues/add_authentication-2228141-93.patch

'''


git apply -v add_authentication-2228141-93.patch

### Angular 2


Supports Js, Typescript, Dart

Why Typescript

 Better overall readability

 Typescript,

 Has modules , each module is a file of its own
 ```
 import {Component} from 'angular2/core';

 @Component({
     selector: 'sample-app',
     template: `<div class="sample">
         <h1> Hello world, this is {{ name }} </h1>
     </div>`
 })
 
 export class SampleComponent {
     name: string;
     constructor() {
         this.name = 'Angular2 !';
     }
 }

 ```

 -Component is unique to angular 2 , not present in angular 1

Components Metadata options

-selector
-template
-templateUrl => give the path
-providers
-directives
-style
-styleUrls
