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
