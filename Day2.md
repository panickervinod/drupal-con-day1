How  publish module :
klausi


- Sandbox or experimental
 -Namespaced URL
 not everyone can make full projects

 Take over unmaintained projects.
  - if maintainer does not respond after 2-3


 https://www.drupal.org/node/251466

 Branch name 8.x-1.x

 Tag name 8.x-1.0-beta1

Coding standards

 https://www.drupal.org/coding-standards/

 every function will start with rules

Coder projects
phpcs --standard= Drupal example.module

for javascript

eslint --config drupal-8/.eslintrc example.js

Drupal 8 ships with .eslintrc

http:// pareview.sh

All licensing will be GPLv2+

Just tell uses to include it the link to where to use it from


Security

Team will support all stable releases.

Security Review
 should note be a threat
 abuse your module

https://www.drupal.org/writing-secure-code
mostly for D7 , but applicable to D8 also

XSS , most 51.5 %
accessbypass
CSRF (Cross site Request Forgery)
openredirects


SQL

XSS twig reduces this in D8

Good example of Script tag and print an

CSRF  use tokens and validate token

Workflow

- Review Checklist
Duplication
Security
Licensing
Documentation
Coding standards

Issue queue
Project Application

Apply permissions

Application workflow ,

needs review
Review finds problems : status needs work
needs review
reviewed & Tested by the community
Git admin approves :fixed
You get the git vetted user role

Review Bonus

Problem
 -Lack of Reviewers
 Solution
 - Applicants become Reviewers
 - Drupal Answers
 - IRC
 Blog about your Project


  Plans

  Automated reviews integrated into drupal.org

  https://www.drupal.org/node/2453587


  Every non-vetted user can promote 1 Sandbox

  No security team support for unstable releases


Join the group of Reviewers

 https://groups.drupal.org/code-review

 become git admin or drupal.org
 join the code sprints on Sunday

 https://events.drupal.org/asia2016/sprints
-----
  Drupal -hooks, plugins, events and services
- Kim.pepper (PreviousNext)


  ### Hooks

   - Discovered
   - Triggered

   hook
      info  // mostly gone  
      alter // remain , to be replaced with event listeners

      new hooks, avoid as there are better ways
      hard to understand what you need to implement

     procedural vs OO
     For :
      can't mock UT
      Global function
      Tightly coupled
    Against:
      interfaces
      dependency injections





 Extending D8 using OO  

  ### Plugins
   - Discover Plugins
    - Annotation
    - PS4 namespace
    - Must implement a plugin interfaces

    ```
    /**

     @Block

    **/


    ```

   When to make a plugin

   You need
   -annotation class
   -write a plugin interfaces
   -implement plugin implementation
   -pluginmanager
      - directory and namespace
      - annotation
      - interfaces
      -

    e.g SearchPluginManager extends DefaultPluginManager


    Plugin Systems PM Concepts
    - How they are Discovered
    -

    ### Plugins in core

    - Tagged services

     Symphony Containers





  ### Tagged services

  Services in yaml

  service:
   my_service:
      class: Drupal\mymodule\service

  Getting a services .

  user injection over procedural

  For A Tagged Service
    Need an interface
    Manager
    tags to our service definitions

    Manager - > manager & services
      addhandler // to add to the list of Services
      // function to do the business logic

       foreach
        if

      tags:
       -{ name: service_collector, tag : my_modules_mytag}  


  e.g.

  - Breadcrumb builders
  - Authentication providers
  - twig extension
  - Placeholder strategies (Big pipes, put placeholders and fill in the slow bits )


  ### Events

  Same as hooks
  Use Symphony2 EventDispatcher Component
  Register listeners
  Handled by callables and services methods

  What do you need

  - event class
  - Event subscribers

  Extends Event

  , EventManager
     -> EventDispatcher objects

   EventSubscriber -> EventSubscriberInterfaces

   services:
    myevent_manager:
         class: Drupal\mymodule\myevent_manager
         arguments:['@EventDispatcher']


   When to use events?

   Summary

   -Avoid hooks -> procedural
   -use events OO
   -use plugins for configuration => multiple instance admin
   -use tagged services -> business logic no configurations


   you still have to use form alter
