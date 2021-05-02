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
1. Initialize a [Node.js] package by creating a [package.json] file
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
    image: postgres:13-alpine
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
want to create. Our VM will use an image called [postgres:13-alpine] which is essentially a snapshot of an
[Alpine Linux] operating system with [PostgreSQL] v13 already installed on it for us.

Next, open the [Integrated Terminal (VSCode)] or [Terminal Emulator (WebStorm)] and start up you virtual PostgreSQL
server by running the following command:

```shell
docker-compose up -d
```

The [docker-compose up] command brings up any and all services defined in `docker-compose.yml`. The `-d` flag causes
these services to run in 'detached mode', which just means they run in the background. If you omit `-d` it will still
run, but you will not be able to use your terminal to run any other commands and closing the terminal will stop any
docker containers that were started.

The first time you run [docker-compose up] it will download a [postgres:13-alpine] image file, which may take a few
minutes. Once it has finished, your database server will be up and running and listening on port `5432`. You can
confirm this by running the following command in the terminal:

```shell
docker-compose ps
```

...and you should see:

```shell
          Name                        Command                 State               Ports         
------------------------------------------------------------------------------------------------
learn-to-code_database_1   docker-entrypoint.sh postgres   Up (healthy)   0.0.0.0:5432->5432/tcp
```

If, after running `docker-compose up -d`, you encounter an error like this:

```shell
ERROR: for learn-to-code_database_1  Cannot start service database: driver failed programming external connectivity on
endpoint learn-to-code_database_1 (...): Bind for 0.0.0.0:5432 failed: port is already allocated
```

...it means you already have a program running on your computer (maybe another instance of PostgreSQL?) that is using
port `5432`. In this case, you can either shut down the other program (if you know how and if it is safe to do so), or
you can modify the [docker-compose ports config] in your `docker-compose.yml` file:

```yaml
    ports:
      - "9999:5432"
```

In this case, you are telling your computer (referred to as the 'host') to listen on port `9999` and forward any
requests it receives to your virtual database server (referred to as the 'container'), which is listening on its port
`5432` (the default port used by [PostgreSQL]).

## Run [PGWeb], a web-based [PostgreSQL] browser, in a [virtual machine] using [Docker Compose]

Now that you have a database container up and running, you should be wondering: "How do I use it?"

There are a few different ways to connect to a remote database server. There is a Command Line Interface ([CLI])
program called [psql], for example, as well as a [Node.js] library we will install later called [node-postgres]. There
is also a program you can run in your web browser called [PGWeb] that has a nice Graphical User Interface ([GUI]).

Let's install [PGWeb] by adding another [Docker] container to our `docker-compose.yml` file:

```yaml
  pgweb:
    image: sosedoff/pgweb
    restart: always
    environment:
      - DATABASE_URL=postgres://mydbuser:mydbpassword@database:5432/mydbname?sslmode=disable
    ports:
      - "8081:8081"
    links:
      - database:database
```

Be sure the indentation is correct! Indentation has meaning in [YAML] files. The service name `pgweb` should be at the
same indentation level as `databse` and one level deeper than `services`.

Putting it all together, your `docker-compose.yml` file should now look like this:

```yaml
version: "3.7"

services:
  database:
    image: postgres:13-alpine
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

  pgweb:
    image: sosedoff/pgweb
    restart: always
    environment:
      - DATABASE_URL=postgres://mydbuser:mydbpassword@database:5432/mydbname?sslmode=disable
    ports:
      - "8081:8081"
    links:
      - database:database
```

The [PGWeb] container is created using an image called [sosedoff/pgweb]. Like [postgres:13-alpine], this image is a
snapshot of an [Alpine Linux] operating system with a program (in this case, [PGWeb]) already installed on it.

One thing to pay attention to here is the [docker-compose environment config]:

```yaml
    environment:
      - DATABASE_URL=postgres://mydbuser:mydbpassword@database:5432/mydbname?sslmode=disable
```

Here, we are setting the `DATABASE_URL` [environment variable] to something that looks like a URL. This is a
[libpq connection URI] used by [PGWeb] to connect to the instance of [PostgreSQL] running in our `database` container.

If you look closely at the `DATABASE_URL`, you will see the following parts that correspond to [environment variable]
and other settings in the `database` service configuration:

* `mydbuser` should match the value of the `POSTGRES_USER` [environment variable]
* `mydbpassword` should match the value of the `POSTGRES_PASSWORD` [environment variable]
* `database` should match the name of container that uses the [postgres:13-alpine] image
* `5432` should match the database container host port
* `mydbname` should match the value of the `POSTGRES_DB` [environment variable]

**NOTE:** If you had to change the host port of your database container due to the default port `5432` already being in
use by another program, be sure to use the same port in the `DATABASE_URL` for the [PGWeb] container.

To start this new container, run the same command as before:

```shell
docker-compose up -d
```

Now if you run `docker-compose ps`, you should see:

```shell
          Name                        Command                  State               Ports         
-------------------------------------------------------------------------------------------------
learn-to-code_database_1   docker-entrypoint.sh postgres    Up (healthy)   0.0.0.0:5432->5432/tcp
learn-to-code_pgweb_1      /usr/bin/pgweb --bind=0.0. ...   Up             0.0.0.0:8081->8081/tcp
```

Notice the [docker-compose ports config] for this container is set to `8081:8081`, meaning any request to port `8081`
on your local 'host' computer will be forwarded to port `8081` on the virtual web server running in this container.

Now open your favorite web browser and make a request to port `8081` by visiting:

http://localhost:8081/

If everything is configured correctly, you should see the [PGWeb] interface.

![Screenshot of PGWeb Query tab](/docs/screenshot-pgweb-query-tab.png)

## Create a database table in [PostgreSQL] using [SQL]

With [PGWeb] open in your web browser, click the `Query` tab and paste the following [SQL] query into the text area:

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
    username      TEXT UNIQUE NOT NULL,
    password_hash TEXT UNIQUE NOT NULL,
    salt          TEXT UNIQUE NOT NULL,
    created_at    TIMESTAMP NOT NULL DEFAULT now(),
    updated_at    TIMESTAMP
);
```

...and then click the `Run Query` button.

Two things should have happened: Below the `Run Query` button it should say "No records found", and in the navigation
menu on the left side of the screen, under `Tables`, you should now see a link to the newly created `users` table.

Clicking on the `users` table in the side nav menu will open up the `Rows` tab. Again, you will again see the message
"No records found" because no records have been inserted into that table yet.

Now click on the `Structure` tab, and you will see a table with information describing the table schema defined in the
[CREATE TABLE] query above.

![Screenshot of PGWeb users table Structure Tab](/docs/screenshot-pgweb-users-structure-tab.png)

Let's break down that [SQL] query line by line.

```postgresql
CREATE TABLE IF NOT EXISTS users (
```

The first line should be fairly self-evident. It instructs [PostgreSQL] to create a new database table called `users`
only if that table does not already exist. If you run the query again from the `Query` tab, nothing will happen. If you
remove the `IF NOT EXISTS` clause, it will raise an error: `pq: relation "users" already exists`.

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
```

The second line states that the `users` table should have a column called `id`. This column uses the [SERIAL] data type,
which means the value must be an [INTEGER] that is [NOT NULL] and will be assigned an auto-incrementing [DEFAULT] value
that is derived from a [sequence generator] (in this case, `users_id_seq`). It will also serve as the [PRIMARY KEY] for
this table, which means it must be [UNIQUE] and [NOT NULL].

As a general rule for any [relational database], every table should have a [PRIMARY KEY].

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
    username      TEXT UNIQUE NOT NULL,
```

The third line specifies a column called `username`. Data in this column must be of the [TEXT] data type. Although this
is not the [PRIMARY KEY], it does have the same [UNIQUE] and [NOT NULL] constraints.

If you attempt to [INSERT] two records with the same `username` value, the second attempt would raise an error: `pq: 
duplicate key value violates unique constraint "users_username_key"`.

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
    username      TEXT UNIQUE NOT NULL,
    password_hash TEXT UNIQUE NOT NULL,
```

The forth line adds another [TEXT] column called `password_hash` with [UNIQUE] and [NOT NULL] constraints. This column
will be used to store a cryptographic [hash] of the user's password, which will be explained later.

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
    username      TEXT UNIQUE NOT NULL,
    password_hash TEXT UNIQUE NOT NULL,
    salt          TEXT UNIQUE NOT NULL,
```

The fifth line adds yet another [TEXT] column called `salt` with [UNIQUE] and [NOT NULL] constraints. The value stored
in this column will be a Universally Unique Identifier ([UUID]) and will be combined with the user's password to
generate a unique cryptographic [hash]. Again, this will be explained in greater detail later.

```postgresql
CREATE TABLE IF NOT EXISTS users (
    id            SERIAL PRIMARY KEY,
    username      TEXT UNIQUE NOT NULL,
    password_hash TEXT UNIQUE NOT NULL,
    salt          TEXT UNIQUE NOT NULL,
    created_at    TIMESTAMP NOT NULL DEFAULT now(),
    updated_at    TIMESTAMP
);
```

The last two lines add [TIMESTAMP] columns called `created_at` and `updated_at`. You will notice that `created_at` has
a [NOT NULL] constraint as well as a [DEFAULT] value. This means that, if you [INSERT] a row without specifying a
`created_at` value, a timestamp for the current date and time will be assigned by the built-in [now()] function.

The `updated_at` column has no constraints, meaning it will be set to `NULL` by default. If we want to get clever, we
can make it that any time we [UPDATE] a row, a timestamp for the current date and time automatically gets assigned by
the built-in [now()] function as well. However, that requires adding a [trigger function].

```postgresql
CREATE OR REPLACE FUNCTION users_table_but()
    RETURNS TRIGGER
    SET SCHEMA 'public'
    LANGUAGE plpgsql
    SET search_path = public
    AS '
    BEGIN
        NEW.updated_at := now();
        RETURN NEW;
    END;
    ';

CREATE TRIGGER users_table_but
    BEFORE UPDATE ON users
    FOR EACH ROW EXECUTE PROCEDURE users_table_but();
```

There is a lot to unpack there, but essentially this [SQL] query creates a custom function in [PostgreSQL] called
`users_table_but` (the `but` suffix being an acronym for `before update trigger`) that intercepts all [UPDATE] queries
on the `users` table and sets the new `updated_at` column value to [now()].

## Install [Node.js] & Node Package Manager ([NPM]) using Node Version Manager ([NVM])

TODO

## Initialize a [Node.js] package by creating a [package.json] file

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
[CREATE TABLE]: https://www.postgresql.org/docs/13/sql-createtable.html
[CRUD]: https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
[crypto.createHash]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#crypto_crypto_createhash_algorithm_options
[CSS]: https://en.wikipedia.org/wiki/CSS
[DAO]: https://en.wikipedia.org/wiki/Data_access_object
[DEFAULT]: https://www.postgresql.org/docs/13/ddl-default.html
[Docker]: https://www.docker.com/get-started
[docker-compose]: https://docs.docker.com/compose/reference/
[docker-compose environment config]: https://docs.docker.com/compose/compose-file/compose-file-v3/#environment
[docker-compose ports config]: https://docs.docker.com/compose/compose-file/compose-file-v3/#ports
[docker-compose up]: https://docs.docker.com/compose/reference/up/
[Docker Compose]: https://docs.docker.com/compose/
[Docker Desktop]: https://www.docker.com/products/docker-desktop
[environment variable]: https://en.wikipedia.org/wiki/Environment_variable
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
[GUI]: https://en.wikipedia.org/wiki/Graphical_user_interface
[hash]: https://en.wikipedia.org/wiki/Cryptographic_hash_function
[HTML]: https://en.wikipedia.org/wiki/HTML
[HTTP]: https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol
[HTTP cookie]: https://en.wikipedia.org/wiki/HTTP_cookie
[IDE]: https://en.wikipedia.org/wiki/Integrated_development_environment
[INSERT]: https://www.postgresql.org/docs/13/sql-insert.html
[Install Docker Desktop (MacOS)]: https://docs.docker.com/docker-for-mac/install/
[Install Docker Desktop (Windows)]: https://docs.docker.com/docker-for-windows/install/
[INTEGER]: https://www.postgresql.org/docs/13/datatype-numeric.html#DATATYPE-INT
[Integrated Terminal (VSCode)]: https://code.visualstudio.com/docs/editor/integrated-terminal
[IntelliJ Ultimate Edition]: https://www.jetbrains.com/idea/
[JavaScript]: https://en.wikipedia.org/wiki/JavaScript
[Jest]: https://jestjs.io/docs/getting-started
[JSON]: https://en.wikipedia.org/wiki/JSON
[JWT]: https://en.wikipedia.org/wiki/JSON_Web_Token
[libpq connection URI]: https://www.postgresql.org/docs/13/libpq-connect.html#LIBPQ-CONNSTRING
[Node.js]: https://nodejs.org/dist/latest-v14.x/docs/api/index.html
[node-postgres]: https://node-postgres.com/
[NOT NULL]: https://www.postgresql.org/docs/13/ddl-constraints.html#id-1.5.4.6.6
[now()]: https://www.postgresql.org/docs/13/functions-datetime.html#FUNCTIONS-DATETIME-CURRENT
[NPM]: https://www.npmjs.com/get-npm
[NVM]: https://github.com/nvm-sh/nvm
[package.json]: https://docs.npmjs.com/cli/v6/configuring-npm/package-json
[PGWeb]: https://sosedoff.github.io/pgweb/
[postgres:13-alpine]: https://hub.docker.com/_/postgres
[PostgreSQL]: https://www.postgresql.org/docs/13/index.html
[PRIMARY KEY]: https://www.postgresql.org/docs/13/ddl-constraints.html#DDL-CONSTRAINTS-PRIMARY-KEYS
[psql]: https://www.postgresql.org/docs/13/app-psql.html
[pull request]: https://git-scm.com/docs/git-request-pull
[React]: https://reactjs.org/
[relational database]: https://en.wikipedia.org/wiki/Relational_database
[REST]: https://en.wikipedia.org/wiki/Representational_state_transfer
[RTFM]: https://en.wikipedia.org/wiki/RTFM
[sequence generator]: https://www.postgresql.org/docs/13/sql-createsequence.html
[SERIAL]: https://www.postgresql.org/docs/13/datatype-numeric.html#DATATYPE-SERIAL
[session management]: https://en.wikipedia.org/wiki/Session_(computer_science)#Session_management
[setting up Git]: https://docs.github.com/en/github/getting-started-with-github/set-up-git#setting-up-git
[sosedoff/pgweb]: https://hub.docker.com/r/sosedoff/pgweb/
[SQL]: https://en.wikipedia.org/wiki/SQL
[Terminal Emulator (WebStorm)]: https://www.jetbrains.com/help/webstorm/terminal-emulator.html
[TEXT]: https://www.postgresql.org/docs/13/datatype-character.html
[TIMESTAMP]: https://www.postgresql.org/docs/13/datatype-datetime.html
[trigger function]: https://www.postgresql.org/docs/13/plpgsql-trigger.html
[UNIQUE]: https://www.postgresql.org/docs/13/ddl-constraints.html#DDL-CONSTRAINTS-UNIQUE-CONSTRAINTS
[UPDATE]: https://www.postgresql.org/docs/13/sql-update.html
[user registration]: https://en.wikipedia.org/wiki/Registered_user
[UUID]: https://en.wikipedia.org/wiki/Universally_unique_identifier
[VCS]: https://en.wikipedia.org/wiki/Version_control
[virtual machine]: https://en.wikipedia.org/wiki/Virtual_machine
[Visual Studio Code]: https://code.visualstudio.com/
[Vue.js]: https://vuejs.org/
[web server]: https://en.wikipedia.org/wiki/Web_server
[WebStorm]: https://www.jetbrains.com/webstorm/
[YAML]: https://en.wikipedia.org/wiki/YAML
