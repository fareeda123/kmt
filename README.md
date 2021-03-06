# Knowledge Management Tool
## Features
### Knowledge Creation
- Requirement 1: Have the ability to easily create “knowledge articles” (KAs).
- These can be original records (e.g., specific work instructions or content) and/or packages of content, including documents, user-configurable forms, tables, and workflows
- Requirement 2: Have the ability to provide multiple levels and formats of information in KAs (e.g., bullet points for senior technical levels, scripted specific details for junior/non-technical staff)
- Requirement 3: Allow for role-based security access, to allow control of access and level of information by login
### Knowledge Sharing
- Requirement 4: Allow for the promotion of process and information across systems and channels, as required
- Requirement 5: Have the ability to create user-defined rules for creation (e.g., mandatory fields) and lifecycle management (e.g., who, how, when revised and updated)
- Requirement 6: Trigger escalation processes (e.g., automated emails/texts to approvers, reminders) for lifecycle activities
revised and updated)
### Knowledge Development
- Requirement 7: Have the ability to update and improve KAs and access the value of usage as input to predicting new records or record types
- Requirement 8: Show innovation by learning from existing records (e.g., types, content, usage) and prompting to create new KAs


# DHSKnowledgeManagement

## Development

Before you can build this project, you must install and configure the following dependencies on your machine:

1. [Node.js][]: We use Node to run a development web server and build the project.
   Depending on your system, you can install Node either from source or as a pre-packaged bundle.
2. [Yarn][]: We use Yarn to manage Node dependencies.
   Depending on your system, you can install Yarn either from source or as a pre-packaged bundle.

After installing Node, you should be able to run the following command to install development tools.
You will only need to run this command when dependencies change in [package.json](package.json).

    yarn install

We use yarn scripts and [Webpack][] as our build system.


Run the following commands in two separate terminals to create a blissful development experience where your browser
auto-refreshes when files change on your hard drive.

    ./mvnw
    yarn start

[Yarn][] is also used to manage CSS and JavaScript dependencies used in this application. You can upgrade dependencies by
specifying a newer version in [package.json](package.json). You can also run `yarn update` and `yarn install` to manage dependencies.
Add the `help` flag on any command to see how you can use it. For example, `yarn help update`.

The `yarn run` command will list all of the scripts available to run for this project.

### Service workers

Service workers are commented by default, to enable them please uncomment the following code.

* The service worker registering script in index.html

```html
<script>
    if ('serviceWorker' in navigator) {
        navigator.serviceWorker
        .register('./sw.js')
        .then(function() { console.log('Service Worker Registered'); });
    }
</script>
```

Note: workbox creates the respective service worker and dynamically generate the `sw.js`

### Managing dependencies

For example, to add [Leaflet][] library as a runtime dependency of your application, you would run following command:

    yarn add --exact leaflet

To benefit from TypeScript type definitions from [DefinitelyTyped][] repository in development, you would run following command:

    yarn add --dev --exact @types/leaflet

Then you would import the JS and CSS files specified in library's installation instructions so that [Webpack][] knows about them:
Edit [src/main/webapp/app/vendor.ts](src/main/webapp/app/vendor.ts) file:
~~~
import 'leaflet/dist/leaflet.js';
~~~

Edit [src/main/webapp/content/css/vendor.css](src/main/webapp/content/css/vendor.css) file:
~~~
@import '~leaflet/dist/leaflet.css';
~~~
Note: there are still few other things remaining to do for Leaflet that we won't detail here.

For further instructions on how to develop with JHipster, have a look at [Using JHipster in development][].

### Using angular-cli

You can also use [Angular CLI][] to generate some custom client code.

For example, the following command:

    ng generate component my-component

will generate few files:

    create src/main/webapp/app/my-component/my-component.component.html
    create src/main/webapp/app/my-component/my-component.component.ts
    update src/main/webapp/app/app.module.ts


## Building for production

To optimize the DHSKnowledgeManagement application for production, run:

    ./mvnw -Pprod clean package

This will concatenate and minify the client CSS and JavaScript files. It will also modify `index.html` so it references these new files.
To ensure everything worked, run:

    java -jar target/*.war

Then navigate to [http://localhost:8080](http://localhost:8080) in your browser.

## Testing

To launch your application's tests, run:

    ./mvnw clean test

### Client tests

Unit tests are run by [Karma][] and written with [Jasmine][]. They're located in [src/test/javascript/](src/test/javascript/) and can be run with:

    yarn test



For more information, refer to the [Running tests page][].

## Using Docker to simplify development (optional)

You can use Docker to improve your JHipster development experience. A number of docker-compose configuration are available in the [src/main/docker](src/main/docker) folder to launch required third party services.

For example, to start a mysql database in a docker container, run:

    docker-compose -f src/main/docker/mysql.yml up -d

To stop it and remove the container, run:

    docker-compose -f src/main/docker/mysql.yml down

You can also fully dockerize your application and all the services that it depends on.
To achieve this, first build a docker image of your app by running:

    ./mvnw verify -Pprod dockerfile:build

Then run:

    docker-compose -f src/main/docker/app.yml up -d

For more information refer to [Using Docker and Docker-Compose][], this page also contains information on the docker-compose sub-generator (`jhipster docker-compose`), which is able to generate docker configurations for one or several JHipster applications.

## Continuous Integration (optional)

To configure CI for your project, run the ci-cd sub-generator (`jhipster ci-cd`), this will let you generate configuration files for a number of Continuous Integration systems. Consult the [Setting up Continuous Integration][] page for more information.

[JHipster Homepage and latest documentation]: http://www.jhipster.tech
[JHipster 4.14.0 archive]: http://www.jhipster.tech/documentation-archive/v4.14.0

[Using JHipster in development]: http://www.jhipster.tech/documentation-archive/v4.14.0/development/
[Using Docker and Docker-Compose]: http://www.jhipster.tech/documentation-archive/v4.14.0/docker-compose
[Using JHipster in production]: http://www.jhipster.tech/documentation-archive/v4.14.0/production/
[Running tests page]: http://www.jhipster.tech/documentation-archive/v4.14.0/running-tests/
[Setting up Continuous Integration]: http://www.jhipster.tech/documentation-archive/v4.14.0/setting-up-ci/


[Node.js]: https://nodejs.org/
[Yarn]: https://yarnpkg.org/
[Webpack]: https://webpack.github.io/
[Angular CLI]: https://cli.angular.io/
[BrowserSync]: http://www.browsersync.io/
[Karma]: http://karma-runner.github.io/
[Jasmine]: http://jasmine.github.io/2.0/introduction.html
[Protractor]: https://angular.github.io/protractor/
[Leaflet]: http://leafletjs.com/
[DefinitelyTyped]: http://definitelytyped.org/
# Agile Methodology
## User Involvement in Design
On 2/21/18, DH Synergetech consultants interviewed users (firefighters) in person at the Butte County CalFire Emergency Command Center to identify a useful application for a Knowledge Management Tool (KMT) that would provide value to CalFire. The firefighters suggested a KMT that mimics the functionality of the “Magnet Board” used to model the firefighting resources available to the county for incident response.  Currently the magnet board is a physical board located in the Command Center.  The goal of the Magnet Board KMT would be to represent the information represented in this magnet board in electronic format, viewable from any location in a responsive format.  Underlying the Magnet Board is new functionality for a Knowledge Management Tool for the fire stations, engines, and other associated firefighting equipment.   
![Image of Magnet Board](https://github.com/dhsynergetech/kmt/blob/master/MagnetBoard.png)
Initial mockups based on the Magnet Board were developed and shared with development team in GitHub https://github.com/dhsynergetech/kmt/blob/master/CalFire%20Mockups%20v2.docx
## Sprint Planning
The DH Synergetech consultants began the scrum process on 2/22/18 with Sprint planning session to review draft user stories based on the interview with firefighters as well as requirements in the RFI.  User stories were developed, documented, and prioritized in the Kanban board in GitHub at https://github.com/dhsynergetech/kmt/projects/1
## Daily Scrum
The DH Synergetech consultants began daily 15 minute scrum calls on 2/23/18, with a plan to conduct two 1 (one) week sprints for the RFI.  Plan is to conduct sprint review's with firefighters to obtain feedback on the CalFire Magnet Board KMT tool. Daily collaboration for the team is enhanced via a Slack channel at https://dhsynergetech.slack.com/?redir=%2Fhome
## Sprint Reviews and Retrospectives
Insert information from sprint reviews and retrospectives here.
## Digital Services Playbook Requirements
Requirement | DH Synergetech Approach
-------------------- | --------------------
a.	Assigned one (1) leader and gave that person authority and responsibility and held that person accountable for the quality of the prototype submitted | Assigned Brendon Delong as Delivery Manager responsible for the prototype.
b.	Assembled a multidisciplinary and collaborative team that includes, at a minimum, five (5) of the labor categories as identified in Attachment B: PQVP AD-DS Labor Category Description | Multi-Disciplinary Team: Delivery Manager (Brendon DeLong), Product Manager (Jacob Hayes), Agile Coach (Pamela Jarrett), Technical Architect (Sabu Azeez), Front End Developer (Steve Hoang), Full Stack Web Developer (Shabna Shurafadeen).
c.	Understood what people needed by including people in the prototype development and design process | Involved users: Design of KMT, User Stories, Sprint Reviews, User Testing, and an iterative development process.
d.	Used at least a minimum of three (3) user-centric design techniques and/or tools | Used story boards, prototype testing, and an iterative process to interact with the firefighters (users).
e.	Used GitHub to document code commits | DH Synergetech used the following GitHub repository: Dhsynergetech / kmt
f.	Used Swagger to document the RESTful API, and provided a link to the Swagger API | Run time RESTful APIs were published in Swagger 
g.	Complied with Section 508 of the Americans with Disabilities Act and WCAG 2.0 | INSERT RESPONSE
h.	Created or used a design style guide and/or pattern library | Used jHipster framework with Reactive code.
i.	Performed usability tests with people | The Product Manager is a former firefighter who performed testing and facilitated user testing with the other firefighters.
j.	Used an iterative approach, where feedback informed subsequent work or versions of the prototype | The DHSynergetech KMT was developed in two iterations (sprints) and reviewed by users during each sprint review.
k.	Created a prototype that works on multiple devices, and presents a responsive design | INSERT RESPONSE
l.	Used at least five (5) modern and open-source technologies, regardless of architectural layer (frontend, backend, etc.) | INSERT RESPONSE
m.	Deployed the prototype on an Infrastructure as a Service (IaaS) or Platform as Service (PaaS) provider, and indicated which provider they used | INSERT RESPONSE
n.	Developed automated unit tests for their code | INSERT RESPONSE
o.	Setup or used a continuous integration system to automate the running of tests and continuously deployed their code to their IaaS or PaaS provider | INSERT RESPONSE
p.	Setup or used configuration management | INSERT RESPONSE
q.	Setup or used continuous monitoring | INSERT RESPONSE
r.	Deployed their software in an open source container, such as Docker (i.e., utilized operating-system-level virtualization) | INSERT RESPONSE
s.	Provided sufficient documentation to install and run their prototype on another machine; and | INSERT RESPONSE
t.	Prototype and underlying platforms used to create and run the prototype are openly licensed and free of charge | INSERT RESPONSE
