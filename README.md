# Full-Stack Software Development with Docker, PostgreSQL & Node.js

This is a crash course on full-stack software development intended for beginners. It does not assume any prior
programming experience, but the learner is expected to read beyond this text and experiment in order to fully grasp the
material. Web links are provided throughout to further explain key terms and technologies.

Using this document, the learner will:

1. Fork and clone this repository using [Git]
1. Install [Docker Desktop] for Windows or Mac
1. Install an [IDE] such as [Visual Studio Code] or [WebStorm]
1. Run a [PostgreSQL] database server in a [virtual machine] using [Docker Compose]
1. Run [PGWeb], a web-based [PostgreSQL] browser, in a [virtual machine] using [Docker Compose]
1. Create a database table in [PostgreSQL] using [SQL]
1. Install [Node.js] & Node Package Manager ([NPM]) using Node Version Manager ([NVM])
1. Create a Linux web server using [Docker] & [Docker Compose]
1. Build a simple [web server] and [REST] endpoint using [Node.js]
1. Install a package as a dependency using [NPM]
1. Write unit tests using [Jest]
1. Read the contents of a file using [fs.readFile]
1. Install and configure [node-postgres] using [NPM]
1. Create a database migration module using [fs.readFile] and [node-postgres]
1. Create a cryptographic one-way [hash] using [crypto.createHash]
1. Create a Command Line Interface ([CLI]) using [Node.js]
1. Create a Data Access Object ([DAO]) for performing [CRUD] operations
1. Create [REST] endpoints for [user registration] and [authentication]
1. Implement a [session management] strategy using an [HTTP cookie] header
1. Create a user login web page using [HTML] and [CSS]
1. Create a user profile web page that requires [authentication] to access
1. Create a user admin page that requires [authorization] to access

## Before we get started...

The material we cover here will get you up and running with the essential tools and foundational knowledge you need to
begin a career as a software developer. It is a hands-on-keyboard tutorial that is meant to be read and acted upon. It
does not attempt to define every term or explain every concept in great depth. Instead, links are provided for you to
drill down to whatever level of detail you like on any given topic.

### Always remember

* Solutions often seem obvious in hindsight. For this reason, it is very easy to get discouraged and convince yourself
  that you are not cut out for this. Every software developer out there has experienced this and (if they are still
  writing code) has had to overcome it. **Be resilient**.


* In the beginning, you need to learn many things in parallel. When you learn to drive a car, you learn to operate the
  machine itself as well as the rules of the road, the physics of objects in motion, the locations and meanings of
  various gauges and controls, and how to anticipate human behavior at high speeds. Eventually, with practice, you can
  just focus on where you are going and how to get there. Learning to code is no different. **Be patient.**


* Read the fucking manual ([RTFM]). The most important thing you can learn is how to find the answers you are looking for
  without asking for help. It's fine to ask for help, especially when you are just getting started, but most of the
  answers you seek are already written down somewhere and, in many cases, they are in the documentation for whatever
  language or library or framework you are using. **Be diligent.**


* When in doubt, write a test. Software developers are experimenters. If you want to understand how something works,
  try it for yourself in a controlled environment. We will cover how to write unit tests and integration tests early on,
  so you can develop this skill throughout the lessons. Do not just assume things will work, even if the documentation
  says they will. **Be certain.**


* Being able to write an application from scratch is great, but navigating a complex and evolving codebase written by
  many people over time, comprehending how its various components interact, identifying and diagnosing bugs,
  understanding business requirements and tradeoffs, surgically resolving issues while minimizing the testing
  surface of your changes... these are the things that separate _software engineers_ from _developers_. Through these
  lessons you will learn how to write an application from scratch. Getting to the next level requires professional
  experience in the industry. **Be humble.**

## 1. Fork and clone this repository using [Git]

[Git] is a Version Control System ([VCS]) that is widely used by software developers. [GitHub] is a popular web service
that provides hosting for public and private [Git] repositories (or "repos"). You can use [Git] without using [GitHub]
(there are other options like [GitLab] or [BitBucket]), but this repo is hosted on [GitHub] so for simplicity it will
be assumed that you are also using [GitHub].

Follow this guide to [setting up Git] on your computer (if necessary), then [fork this repo] to make yourself a copy.

Finally, [clone your repo] to make a copy on your computer.

In the end, there will be three copies of this repo that concern you:

* `upstream` is the original copy of this repo, hosted at `https://github.com/sscovil/learn-to-code`
* `origin` is your forked copy of this repo, hosted at `https://github.com/your-username/learn-to-code`
* `local` is your cloned copy of this repo, which lives on your computer

The key to understand here is that you have two copies of the original repo and, whenever any of these three copies
(your two copies plus the original) changes, you need to update the others to keep them all in sync.

If the original `upstream` copy changes after you have forked it, you can [git pull] those changes into your `local`
copy, then [git push] them to your `origin` copy.

If you make a change to your `local` copy, you need to [git add] the changes (which just marks them as 'staged' or
ready to commit), then [git commit] those changes (which actually updates the version history), then finally [git push]
those changes up to your `origin` copy to keep it in sync with your `local` copy.

From there, you can create a [pull request] to the original `upstream` copy and, if the owner or maintainer of that
repo approves, they will [git merge] your changes (or grant you permission to do so) and, at that point, all three
copies will be up to date.

There are a ton of resources and tutorials online that explain [Git] in depth. Before going any further, take the time
to wrap your head around how this tool works. It is a critical concept that you need to understand. Learning it later,
while you are trying to learn how to develop software, will make the whole process more stressful.

## 2. Install [Docker Desktop] for Windows or Mac

Before you get started, you will need to install [Docker] on your computer. [Docker] is a tool that enables developers
to run a [virtual machine] (or several VMs) on their computer. This is useful because many people have Windows or MacOS
as an operating system on their computer, but the code they write is often deployed to a server running some flavor of
Linux. Docker enables us to run our software in a local development environment that is identical to production.

* [Install Docker Desktop (MacOS)]
* [Install Docker Desktop (Windows)]

There is a lot to learn about [Docker], but we are only going to cover what you need to know as a software developer to
be productive with it in your local development environment. Feel free to dive deeper if it interests you.

## 3. Install an [IDE] such as [Visual Studio Code] or [WebStorm]

You will want to install an Integrated Development Environment ([IDE]), which is an application used by software
developers to write code more efficiently. You can write code in a plain old text editor if you prefer, just like you
can build a house with a hammer and hand saw, but if you are serious about becoming a software developer you should
learn the tools of the trade.

[Visual Studio Code] is free and very popular among web developers. I personally use [IntelliJ Ultimate Edition], which
is a bit pricey but has plugins for every programming language. [WebStorm] is made by the same company (JetBrains), but
it only supports [JavaScript] and frameworks like [Node.js], [React], and [Vue.js].

## 4. Run a [PostgreSQL] database server in a virtual machine using [Docker Compose]

Once you have [Git], [Docker Desktop], and your preferred [IDE] installed, and you have forked this repo and cloned a
copy of it on your computer, start your [IDE] and open the `learn-to-code` folder. This will be referred to as your
**project folder** going forward. The code you write throughout this tutorial will live in your project folder.

Start by creating a new file called `docker-compose.yml` and, in that file, copy/paste the following:

```yml
version: "3.7"

services:
  database:
    image: postgres:12.2-alpine
    restart: unless-stopped
    environment:
      - POSTGRES_USER=mydbuser
      - POSTGRES_PASSWORD=mydbpassword
      - POSTGRES_DB=mydbname
    healthcheck:
      test: pg_isready -U postgres
      interval: 5s
      retries: 10
      timeout: 5s
    ports:
      - "5432:5432"
    volumes:
      - .:/data/db
```

This is a [Docker Compose] configuration file that uses a format called [YAML] and describes a [virtual machine] we
will create. This VM uses an image called [postgres:12.2-alpine] which is essentially a snapshot of an [Alpine Linux]
operating system that has [PostgreSQL] v12.2 already installed on it.

Next, open the [Integrated Terminal (VSCode)] or [Terminal Emulator (WebStorm)] and start up you virtual PostgreSQL
server by running the following command:

```shell
docker-compose up -d
```

The command [docker-compose up] brings up all the services defined in `docker-compose.yml` and the `-d` flag
causes these services to run in 'detached mode', which just means they run in the background. If you omit that flag it
will still run, but you will not be able to use your terminal to run any other commands and closing the terminal will
stop the docker containers.

The first time you run [docker-compose up] it will download the [postgres:12.2-alpine] image file, which may take a few
minutes. Once it has finished, your database server will be up and running and listening on port 5432. However, you do
not yet have a convenient way to connect to it. We will address that in the next section...

## Run [PGWeb], a web-based [PostgreSQL] browser, in a [virtual machine] using [Docker Compose]

TODO

## Create a database table in [PostgreSQL] using [SQL]

TODO

## Install [Node.js] & Node Package Manager ([NPM]) using Node Version Manager ([NVM])

TODO

## Create a Linux web server using [Docker] & [Docker Compose]

TODO

## Build a simple [web server] and [REST] endpoint using [Node.js]

TODO

## Install a package as a development dependency using [NPM]

TODO

## Write unit tests using [Jest]

TODO

## Read the contents of a file using [fs.readFile]

TODO

## Install and configure [node-postgres] using [NPM]

TODO

## Create a database migration module using [fs.readFile] and [node-postgres]

TODO

## Create a cryptographic one-way [hash] using [crypto.createHash]

TODO

## Create a Command Line Interface ([CLI]) using [Node.js]

TODO

## Create a Data Access Object ([DAO]) for performing [CRUD] operations

TODO

## Create [REST] endpoints for [user registration] and [authentication]

TODO

## Implement a [session management] strategy using an [HTTP cookie] header

TODO

## Create a user login web page using [HTML] and [CSS]

TODO

## Create a user profile web page that requires [authentication] to access

TODO

## Create a user admin page that requires [authorization] to access

TODO



[Alpine Linux]: https://alpinelinux.org/
[authentication]: https://en.wikipedia.org/wiki/Authentication
[authorization]: https://en.wikipedia.org/wiki/Authorization
[BitBucket]: https://bitbucket.org/product
[CLI]: https://en.wikipedia.org/wiki/Command-line_interface
[clone your repo]: https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository
[CRUD]: https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
[crypto.createHash]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#crypto_crypto_createhash_algorithm_options
[CSS]: https://en.wikipedia.org/wiki/CSS
[DAO]: https://en.wikipedia.org/wiki/Data_access_object
[Docker]: https://www.docker.com/get-started
[docker-compose]: https://docs.docker.com/compose/reference/
[docker-compose up]: https://docs.docker.com/compose/reference/up/
[Docker Compose]: https://docs.docker.com/compose/
[Docker Desktop]: https://www.docker.com/products/docker-desktop
[fs.readFile]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#fs_fs_readfile_path_options_callback
[fork this repo]: https://docs.github.com/en/github/getting-started-with-github/fork-a-repo
[Git]: https://git-scm.com/
[git add]: https://git-scm.com/docs/git-add
[git commit]: https://git-scm.com/docs/git-commit
[git merge]: https://git-scm.com/docs/git-merge
[git pull]: https://git-scm.com/docs/git-pull
[git push]: https://git-scm.com/docs/git-push
[GitHub]: https://docs.github.com/en/github/getting-started-with-github/quickstart
[GitLab]: https://about.gitlab.com/
[hash]: https://en.wikipedia.org/wiki/Cryptographic_hash_function
[HTML]: https://en.wikipedia.org/wiki/HTML
[HTTP]: https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol
[HTTP cookie]: https://en.wikipedia.org/wiki/HTTP_cookie
[IDE]: https://en.wikipedia.org/wiki/Integrated_development_environment
[Install Docker Desktop (MacOS)]: https://docs.docker.com/docker-for-mac/install/
[Install Docker Desktop (Windows)]: https://docs.docker.com/docker-for-windows/install/
[Integrated Terminal (VSCode)]: https://code.visualstudio.com/docs/editor/integrated-terminal
[IntelliJ Ultimate Edition]: https://www.jetbrains.com/idea/
[JavaScript]: https://en.wikipedia.org/wiki/JavaScript
[Jest]: https://jestjs.io/docs/getting-started
[JSON]: https://en.wikipedia.org/wiki/JSON
[JWT]: https://en.wikipedia.org/wiki/JSON_Web_Token
[PGWeb]: https://sosedoff.github.io/pgweb/
[postgres:12.2-alpine]: https://hub.docker.com/_/postgres
[PostgreSQL]: https://www.postgresql.org/docs/12/index.html
[Node.js]: https://nodejs.org/dist/latest-v14.x/docs/api/index.html
[node-postgres]: https://node-postgres.com/
[NPM]: https://www.npmjs.com/get-npm
[NVM]: https://github.com/nvm-sh/nvm
[pull request]: https://git-scm.com/docs/git-request-pull
[React]: https://reactjs.org/
[REST]: https://en.wikipedia.org/wiki/Representational_state_transfer
[RTFM]: https://en.wikipedia.org/wiki/RTFM
[session management]: https://en.wikipedia.org/wiki/Session_(computer_science)#Session_management
[setting up Git]: https://docs.github.com/en/github/getting-started-with-github/set-up-git#setting-up-git
[SQL]: https://en.wikipedia.org/wiki/SQL
[Terminal Emulator (WebStorm)]: https://www.jetbrains.com/help/webstorm/terminal-emulator.html
[user registration]: https://en.wikipedia.org/wiki/Registered_user
[VCS]: https://en.wikipedia.org/wiki/Version_control
[virtual machine]: https://en.wikipedia.org/wiki/Virtual_machine
[Visual Studio Code]: https://code.visualstudio.com/
[Vue.js]: https://vuejs.org/
[web server]: https://en.wikipedia.org/wiki/Web_server
[WebStorm]: https://www.jetbrains.com/webstorm/
[YAML]: https://en.wikipedia.org/wiki/YAML
