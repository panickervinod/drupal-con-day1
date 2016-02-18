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
