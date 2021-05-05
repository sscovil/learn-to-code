# Full-Stack Software Development
**Using Docker, PostgreSQL, Node.js & React**

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
1. Install [Node.js] & Node Package Manager ([NPM])
1. Initialize a [Node.js] package by creating a [package.json] file
1. Install a package as a dependency using [NPM]
1. Build a simple [web server] and [REST] endpoint using [Node.js]
1. Write unit tests using [Jest]
1. Create a Linux web server using [Docker] & [Docker Compose]
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

Follow this guide to [setting up Git] on your computer (if necessary), then [fork this repo] to make a copy of it in
your own GitHub account.

Finally, [clone your repo] to download a copy from your GitHub account onto your computer.

In the end, there will be three copies of this repo that concern you:

* `upstream` is the original copy of this repo, hosted at `https://github.com/sscovil/learn-to-code`
* `origin` is your forked copy of this repo, hosted at `https://github.com/your-username/learn-to-code`
* `local` is your cloned copy of this repo, which lives on your computer

The key to understand here is that you have two copies of the original repo and, whenever any of these three copies
(your two copies plus the original) changes, you will need to update the others to keep them all in sync.

If the original `upstream` copy changes after you have forked it, you can [git pull] those changes into your `local`
copy, then [git push] them to your `origin` copy.

If you make a change to your `local` copy, you need to [git add] the changes (which just marks them as 'staged' or
ready to commit), then [git commit] those changes (which actually updates the version history), then finally [git push]
those changes up to your `origin` copy to keep it in sync with your `local` copy.

> **IMPORTANT:** You should commit your code changes early and often. The power of version control is that it enables
> you to go back to previous versions of your code. Throughout this lesson, try and remember to commit your changes and
> push them up to your `origin` copy to keep it in sync.

From there, you can create a [pull request] to the original `upstream` copy and, if the owner or maintainer of that
repo approves, they will [git merge] your changes (or grant you permission to do so) and, at that point, all three
copies will be up to date.

For this project, you do not need to worry about making a [pull request]. This tutorial will be used by others, so your
changes will never get merged into the original `upstream` copy. However, you should occasionally [git pull] from the
`upstream master` branch to get the latest changes.

Read this guide to [configure an upstream remote] for your fork, then you can get the latest updates to this document
using the command:

```shell
git pull upstream master
```

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

[Visual Studio Code] is free and very popular among web developers. I personally use [IntelliJ], which is a bit pricey
but has plugins for every programming language. [WebStorm] is made by the same company (JetBrains), but it only supports
[JavaScript] and frameworks like [Node.js], [React], and [Vue.js].


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
      test: pg_isready -U ${POSTGRES_USER}
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

Next, open the [Integrated Terminal (VSCode)] or [Terminal Emulator (WebStorm)] and start up your virtual PostgreSQL
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

### Helpful [docker-compose] commands

To stop your running containers without removing them, use:

```shell
docker-compose stop
```

You can start them up again using:

```shell
docker-compose start
```

The `start` and `stop` commands are equivalent to turning your virtual machines on and off. When you start them up
again, they will be in the same state they were in when you turned them off.

Sometimes you will want to completely destroy your containers. To do this, use:

```shell
docker-compose down
```

You can always create new instances of your containers by running:

```shell
docker-compose up -d
```

If you ever want to see the logs for a container, use:

```shell
docker-compose logs database
```

Running that command, you should see output like this:

```shell
Attaching to learn-to-code_database_1
database_1  | The files belonging to this database system will be owned by user "postgres".
database_1  | This user must also own the server process.
database_1  | 
database_1  | The database cluster will be initialized with locale "en_US.utf8".
database_1  | The default database encoding has accordingly been set to "UTF8".
database_1  | The default text search configuration will be set to "english".
database_1  | 
database_1  | Data page checksums are disabled.
database_1  | 
database_1  | fixing permissions on existing directory /var/lib/postgresql/data ... ok
database_1  | creating subdirectories ... ok
database_1  | selecting dynamic shared memory implementation ... posix
database_1  | selecting default max_connections ... 100
database_1  | selecting default shared_buffers ... 128MB
database_1  | selecting default time zone ... UTC
database_1  | creating configuration files ... ok
database_1  | running bootstrap script ... ok
database_1  | sh: locale: not found
database_1  | 2021-05-02 13:26:50.561 UTC [30] WARNING:  no usable system locales were found
database_1  | performing post-bootstrap initialization ... ok
database_1  | syncing data to disk ... ok
database_1  | 
database_1  | initdb: warning: enabling "trust" authentication for local connections
database_1  | You can change this by editing pg_hba.conf or using the option -A, or
database_1  | --auth-local and --auth-host, the next time you run initdb.
database_1  | 
database_1  | Success. You can now start the database server using:
database_1  | 
database_1  |     pg_ctl -D /var/lib/postgresql/data -l logfile start
database_1  | 
database_1  | waiting for server to start....2021-05-02 13:26:51.020 UTC [35] LOG:  starting PostgreSQL 13.2 on aarch64-unknown-linux-musl, compiled by gcc (Alpine 10.2.1_pre1) 10.2.1 20201203, 64-bit
database_1  | 2021-05-02 13:26:51.021 UTC [35] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
database_1  | 2021-05-02 13:26:51.024 UTC [36] LOG:  database system was shut down at 2021-05-02 13:26:50 UTC
database_1  | 2021-05-02 13:26:51.025 UTC [35] LOG:  database system is ready to accept connections
database_1  |  done
database_1  | server started
database_1  | CREATE DATABASE
database_1  | 
database_1  | 
database_1  | /usr/local/bin/docker-entrypoint.sh: ignoring /docker-entrypoint-initdb.d/*
database_1  | 
database_1  | waiting for server to shut down....2021-05-02 13:26:51.186 UTC [35] LOG:  received fast shutdown request
database_1  | 2021-05-02 13:26:51.187 UTC [35] LOG:  aborting any active transactions
database_1  | 2021-05-02 13:26:51.187 UTC [35] LOG:  background worker "logical replication launcher" (PID 42) exited with exit code 1
database_1  | 2021-05-02 13:26:51.187 UTC [37] LOG:  shutting down
database_1  | 2021-05-02 13:26:51.194 UTC [35] LOG:  database system is shut down
database_1  |  done
database_1  | server stopped
database_1  | 
database_1  | PostgreSQL init process complete; ready for start up.
database_1  | 
database_1  | 2021-05-02 13:26:51.300 UTC [1] LOG:  starting PostgreSQL 13.2 on aarch64-unknown-linux-musl, compiled by gcc (Alpine 10.2.1_pre1) 10.2.1 20201203, 64-bit
database_1  | 2021-05-02 13:26:51.300 UTC [1] LOG:  listening on IPv4 address "0.0.0.0", port 5432
database_1  | 2021-05-02 13:26:51.300 UTC [1] LOG:  listening on IPv6 address "::", port 5432
database_1  | 2021-05-02 13:26:51.301 UTC [1] LOG:  listening on Unix socket "/var/run/postgresql/.s.PGSQL.5432"
database_1  | 2021-05-02 13:26:51.304 UTC [49] LOG:  database system was shut down at 2021-05-02 13:26:51 UTC
database_1  | 2021-05-02 13:26:51.305 UTC [1] LOG:  database system is ready to accept connections
```

When a container is unhealthy or not working correctly, checking the logs should be one of the first things you do.

If you ever want to run a command from the terminal inside a container, use something like:

```shell
docker-compose exec database /bin/sh
```

This example transports you inside the [Alpine Linux] operating system of your `database` container by running
`/bin/sh`, a Command Line Interface ([CLI]) that uses the [shell] scripting language. You can then navigate the file
system and run commands as if you were using the [virtual machine].

To exit the [shell] and return to your host computer's terminal, use:

```shell
exit
```

Finally, when we create our own [Docker] service later on, any time you change the service’s [Dockerfile] or the
contents of its build directory, you will need to run:

```shell
docker-compose build
```

For now, you do not need to worry about building a [Docker] service. That will be covered in detail later. 


## 5. Run [PGWeb], a web-based [PostgreSQL] browser, in a [virtual machine] using [Docker Compose]

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

* `mydbuser` should match the value of the `POSTGRES_USER` environment variable
* `mydbpassword` should match the value of the `POSTGRES_PASSWORD` environment variable
* `database` should match the name of container that uses the [postgres:13-alpine] image
* `5432` should match the database container host port
* `mydbname` should match the value of the `POSTGRES_DB` environment variable

> **NOTE:** If you had to change the host port of your database container due to the default port `5432` already being
> in use by another program, be sure to use the same port in the `DATABASE_URL` for the [PGWeb] container.

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


## 6. Create a database table in [PostgreSQL] using [SQL]

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

Clicking on the `users` table in the side nav menu will open up the `Rows` tab. Again, you will see the message "No
records found" because no records have been inserted into that table yet.

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

The fourth line adds another [TEXT] column called `password_hash` with [UNIQUE] and [NOT NULL] constraints. This column
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
can make it so that any time we [UPDATE] a row, a timestamp for the current date and time automatically gets assigned by
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

Now that we have our database table created, let's [INSERT] some records into it.

```postgresql
INSERT INTO users (username, password_hash, salt) VALUES
    ('alice', 'foo', 'xxx'),
    ('bob', 'bar', 'yyy'),
    ('carol', 'baz', 'zzz');
```

Now let's [UPDATE] a record and confirm that the `updated_at` column automatically gets assigned a value.

```postgresql
UPDATE users SET username='candice' WHERE username='carol';
```

Finally, let's [DELETE] a row.

```postgresql
DELETE FROM users WHERE username='alice';
```

Keep in mind that if you destroy your [Docker] `database` container using `docker-compose down`, any tables you created
and any data you added will be lost. We will address that later when we create a [database migration] utility.


## 7. Install [Node.js] & Node Package Manager ([NPM])

Now that you have a [PostgreSQL] database server and a nice [GUI] web app to interact with your database, let's get
ready to write some actual code. We will begin with [Node.js], a server-side [JavaScript] framework.

Like any framework, [Node.js] is a collection of libraries that abstract away a lot of core functionality commonly
required to build an application. For example, [Node.js http] provides interfaces that are designed to support many
features of the [HTTP] protocol that can be difficult to work with, like large, possibly chunk-encoded, messages.

By using a well-supported open source framework like [Node.js], we are free to focus on the requirements of the
application we want to build instead of having to solve a bunch of problems that other engineers have already solved.

You could [install Node.js] by choosing a specific version and downloading the installer from their website, but I
recommend using a version manager instead. If you are on MacOS or Linux, try Node Version Manager ([NVM]); otherwise,
there is a similar tool called [Node Version Manager for Windows]. A version manager makes it easy to quickly install
any version of [Node.js] and switch between them as needed when working on multiple projects.

Whichever method you choose, install [Node.js] v14.x which is the current Long Term Support ([LTS]) version at the time
of this writing. Doing so will also automatically install Node Package Manager ([NPM]) v6.x, which will be used to
install other libraries we will use.

> **NOTE:** If you are using [WebStorm] or [IntelliJ], you will want to [enable coding assistance for Node.js].

### About version numbers

You will often see software version numbers like `14.16.1`, `14.x`, or `>=14` and you may be confused by it. Most modern
frameworks and libraries use a version format standard known as [semantic versioning], sometimes abbreviated 'semver',
where the numbers represent `major.minor.patch` releases. Bug fixes that do not affect the way the software is used will
increment the `patch` version. Backwards-compatible additions and changes will increment the `minor` version.
Backwards-incompatible or breaking changes will increment the major version.

This is important to consider when upgrading the frameworks or libraries you use in your applications. If your
application was written for [Node.js] v14.x, it should continue to work with any `minor` or `patch` version upgrade, but
there is a chance something will break with a `major` version upgrade. Reliable frameworks and libraries will maintain
a detailed [changelog] (ex: [Node.js changelog]).

It is also important to be sure you are reading the documentation for the correct version of any software you are using.
If you are reading the docs for a newer version of a library than the one you have installed, you will spend a lot of
time scratching your head and feel very silly when you figure out what went wrong. Trust me. 🤦


## 8. Initialize a [Node.js] package by creating a [package.json] file

With [Node.js] and [NPM] installed, let's initialize our application by creating a [package.json] file. [NPM] actually
provides a [CLI] that walks you through the process.

From the terminal, in your project folder, run:

```shell
npm init
```

...then fill in the information you are prompted for. Default values appear inside parentheses; to use them, just hit
enter. For example:

```shell
package name: (learn-to-code) 
version: (1.0.0) 
description: A crash course on full-stack software development with Docker, PostgreSQL, Node.js & React
entry point: (index.js) 
test command: jest
git repository: (https://github.com/sscovil/learn-to-code.git) 
keywords: docker,postgres,node,react,tutorial
author: Shaun Scovil <sscovil@gmail.com>
license: (ISC) UNLICENSED
```

Here, the default values for `name`, `version`, `entry point`, and `git repository` were used, but the other fields were
filled in. The [CLI] then generated the following [package.json] file:

```json
{
  "name": "learn-to-code",
  "version": "1.0.0",
  "description": "A crash course on full-stack software development with Docker, PostgreSQL, Node.js & React",
  "main": "index.js",
  "directories": {
    "doc": "docs"
  },
  "scripts": {
    "test": "jest"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/sscovil/learn-to-code.git"
  },
  "keywords": [
    "docker",
    "postgres",
    "node",
    "react",
    "tutorial"
  ],
  "author": "Shaun Scovil <sscovil@gmail.com>",
  "license": "UNLICENSED",
  "bugs": {
    "url": "https://github.com/sscovil/learn-to-code/issues"
  },
  "homepage": "https://github.com/sscovil/learn-to-code#readme"
}
```

A lot of this information really only matters if you publish your code on [npmjs.com], which you would only do if you
wanted to turn your project into an [open source] library for other developers to use. Every time you install a
dependency using [npm install], you are using code that someone else published to [npmjs.com].

We will not be building anything that you would publish to [npmjs.com], but we will be installing a few libraries as
dependencies for our application. For this reason, we need a [package.json] file.

### JSON vs. YAML

Earlier, we created a configuration file called `docker-compose.yml` that uses the [YAML] format. Now we have created a
configuration file called `package.json` that uses the [JSON] format. Both of these formats are standard ways to
describe data that is recognizable to most programming languages. The syntax is different, but they are effectively the
same thing. The correct format to use is determined by the software that will read the data. [Docker Compose] uses
[YAML], but most [JavaScript] applications use [JSON].


## 9. Install a package as a dependency using [NPM]

Now that we have initialized our [Node.js] application with a [package.json] file, we can install [dependencies]. A
dependency is a piece of software, usually written and maintained by someone else, that your code requires in order to
function in some way.

You can find libraries on [npmjs.com] that do just about everything, but anyone with an Internet connection and a pulse
can create and publish [Node packages] so you should be very selective about the packages you incorporate into your
project.

In general, you should:

* only add dependencies that provide functionality you absolutely need
* only choose packages that are actively maintained by professionals
* avoid dependencies for trivial code that is easy to write and maintain

One good example of a dependency you should include in your project is a testing framework like [Jest], [Mocha], or
[Jasmine]. You could test your code without a framework, using the built-in [Node.js assert] library or whatever, but
you will quickly find yourself spending more time writing complicated test functions than actual code or, worse, not
writing tests at all.

I highly recommend using [Jest] because it requires no configuration, offers a lot of really useful features, and is
actively maintained by Facebook and a huge community of contributors.

Let's install [Jest] as a development dependency. In the terminal, from the project folder, run:

```shell
npm install -D jest
```

The `-D` flag indicates that this is a _development dependency_, meaning it is not required to run the application in
production. Normally, you set up your code deployment pipeline so that tests are run automatically and must pass before
any code is deployed to production.

If you open your [package.json] file, you should see a `devDependencies` section has been added to the bottom:

```json
{
  "name": "learn-to-code",
  "version": "1.0.0",
  "description": "A crash course on full-stack software development with Docker, PostgreSQL, Node.js & React",
  "type": "module",
  "main": "index.js",
  "directories": {
    "doc": "docs"
  },
  "scripts": {
    "test": "jest"
  },
  "repository": {
    "type": "git",
    "url": "git+https://github.com/sscovil/learn-to-code.git"
  },
  "keywords": [
    "docker",
    "postgres",
    "node",
    "react",
    "tutorial"
  ],
  "author": "Shaun Scovil <sscovil@gmail.com>",
  "license": "UNLICENSED",
  "bugs": {
    "url": "https://github.com/sscovil/learn-to-code/issues"
  },
  "homepage": "https://github.com/sscovil/learn-to-code#readme",
  "devDependencies": {
    "jest": "^26.6.3"
  }
}
```

The `^` before the version number means that any `minor` or `patch` release greater than the version specified is
acceptable. See the [About version numbers](#about-version-numbers) section above for more about [semantic versioning].

You will also notice a new directory in your project folder called [node_modules]. If you look inside that directory,
you may be shocked to see an insane number of subdirectories, despite you having only installed one single dependency.
This is because [Jest] itself has dependencies, and many of those packages have dependencies, and so on. This is why
we need a package manager like [NPM] to manage downloading these things for us.

If you were paying attention earlier, you will recall that I said "you should be very selective about the packages you
incorporate into your project." Any package you include is a potential bug or security vulnerability you may be exposed
to. Of course, your own code is subject to those same risks, and an open source project actively maintained by a
community of developers is arguably more resilient than a library you build by yourself.

Here are some ways you can mitigate dependency risk:

* Run [npm audit] to scan your project for vulnerabilities & automatically install compatible updates
* Set up [GitHub Dependabot] to scan your repository for known security vulnerabilities
* Keep your code up to date and pay attention to release schedules for any packages you rely on


## 10. Build a simple [web server] and [REST] endpoint using [Node.js]

Up to this point, almost everything we have done has been to set up our local development environment and configure the
database and tools we will use to build our application. Now we are ready to start writing some code.

The first thing we will build is a simple [web server]. To keep our code organized, we will create a directory in our
project folder called `src` (a standard abbreviation for 'source', as in [source code]).

You can create the directory in your [IDE] from the `File` menu, or from the terminal using the command:

```shell
mkdir src
```

Then, inside the `src` directory, create a file called `server.js`. Again, you can do this from the [IDE] `File` menu,
or from the terminal using:

```
echo > src/server.js
```

If you are creating `server.js` using the [IDE] `File` menu, just be sure it ends up inside the `src` directory and not
alongside it in the root directory. Your project folder should look like this:

```
learn-to-code/
├─ node_modules/
├─ src/
│  └─ server.js
├─ .gitignore
├─ package.json
├─ package-lock.json
└─ README.md
```

Open `server.js` in your [IDE] and paste in the following code:

```javascript
const http = require('http')

const host = process.env.APP_HOST || 'localhost'
const port = process.env.APP_PORT || 8080

const router = async (req, res) => {
    let body
    let code

    if ('/ping' === req.url) {
        body = {status: 'healthy'}
        code = 200
    } else {
        body = {error: 'Resource not found'}
        code = 404
    }

    res.setHeader('Content-Type', 'application/json')
    res.writeHead(code)
    res.end(JSON.stringify(body))
}

const server = http.createServer(router)

server.on('listening', () => {
    console.log(`Server listening at http://${host}:${port}`)
})

try {
    server.listen(port, host)
} catch(err) {
    console.error(err, 'Error starting server')
}
```

There is a lot going on here, so let's break it down.

```javascript
const http = require('http')
```

At the top of the file, we import the [Node.js http] module and assign it to a constant (or [const]) called `http`.
Although the module is called 'http', we could just as easily name our constant something else, like `h` or `foo`, and
it would work the same way. Think of these names as aliases we assign to data, [objects] or [functions].

```javascript
const host = process.env.APP_HOST || 'localhost'
const port = process.env.APP_PORT || 8080
```

Here, we declare two more constants: `host` and `port`. This time, instead of importing their values from a module, we
assign them each the value of an [environment variable] (`APP_HOST` and `APP_PORT`, respectively). We also use the
[logical OR] operator `||` to assign default values, in case the environment variables are [undefined].

```javascript
const router = async (req, res) => {
    let body
    let code

    if ('/ping' === req.url) {
        body = {status: 'healthy'}
        code = 200
    } else {
        body = {error: 'Resource not found'}
        code = 404
    }

    res.setHeader('Content-Type', 'application/json')
    res.writeHead(code)
    res.end(JSON.stringify(body))
}
```

Here, we declare a constant called `router` and define it as an [async function] (more on this later) using an
[arrow function] expression. This function accepts two arguments, `req` and `res`, which are abbreviations for 'request'
(an [http.IncomingMessage] object) and 'response' (an [http.ServerResponse] object).

Let's examine the code inside the `router` function...

```javascript
    let body
    let code
```

The `router` function starts by declaring two variables using the [let] statement, which differs from [const] in that
the value of a [const] cannot be changed (thus it is constant). Since we will assign different values to the `body` and
`code` variables based on [conditional logic], we declare them using [let].

```javascript
    if ('/ping' === req.url) {
        body = {status: 'healthy'}
        code = 200
    } else {
        body = {error: 'Resource not found'}
        code = 404
    }
```

Using an [if...else] statement, we compare the [string] value `'/ping'` to the value of [req.url] which, as the name
implies, is the requested URL path. If our web server is listening at http://localhost:8080 and someone visits the URL
http://localhost:8080/ping then the value of `req.url` would be `'/ping'` and this condition would be true.

```javascript
    res.setHeader('Content-Type', 'application/json')
    res.writeHead(code)
    res.end(JSON.stringify(body))
```

Then we call some [http.ServerResponse] functions: [setHeader], [writeHead], and [end].

* `res.setHeader` is used to set the [Content-Type] response header, indicating that the [response body] will be in
  [JSON] format.
* `res.writeHead` sends a [response header] to the request with a 3-digit HTTP status code, like 200 (Success) or 404
  (Not Found).
* `res.end` send our `body` object, which we convert to a [JSON] string using [JSON.stringify], then signals to the
  server that all response headers and body have been sent and that the server should consider this request complete.

The `router` function will serve as a request listener, meaning it will be called whenever our [http.Server] receives
an HTTP request.

```javascript
const server = http.createServer(router)
```

Here, we pass the `router` function as a request listener to the [http.createServer] function which, as you may have
guessed, creates an [http.Server] object. We assign that object to a constant called `server`.

Our `server` object is an instance of the [http.Server] class, which is a type of [EventEmitter]. This means that it
will emit events whenever certain things happen. It also means that you can instruct `server` to listen for certain
events and, when they occur, run a function (called an 'event handler') to perform a desired action.

```javascript
server.on('listening', () => {
    console.log(`Server listening at http://${host}:${port}`)
})
```

Here we call the [server.on] function and pass it an event handler. When the server begins listening for incoming
requests, it emits a [listening] event that triggers our event handler, which then calls [console.log] and logs a
message informing us that the server is ready.

```javascript
try {
    server.listen(port, host)
} catch(err) {
    console.error(err, 'Error starting server')
}
```

Finally, we call the [server.listen] function with the `port` and `host` constants we defined earlier. If successful,
it will emit the [listening] event and trigger our event handler. However, if it throws an error, our [try...catch]
statement will catch the error and call [console.error] to log the error details to inform us what went wrong.

### Run your Node.js application

To run your web server, open the terminal and run the following command from your project folder:

```shell
node src/server.js
```

You should see the success message from your [listening] event handler:

```shell
Server listening at http://localhost:8080
```

If you see this error instead:

```shell
Error: listen EADDRINUSE: address already in use 127.0.0.1:8080
    at Server.setupListenHandle [as _listen2] (net.js:1318:16)
    at listenInCluster (net.js:1366:12)
    at GetAddrInfoReqWrap.doListen [as callback] (net.js:1503:7)
    at GetAddrInfoReqWrap.onlookup [as oncomplete] (dns.js:69:8)
Emitted 'error' event on Server instance at:
    at emitErrorNT (net.js:1345:8)
    at processTicksAndRejections (internal/process/task_queues.js:80:21) {
  code: 'EADDRINUSE',
  errno: -48,
  syscall: 'listen',
  address: '127.0.0.1',
  port: 8080
}
```

...that means some other program is already listening on port `8080`. You can stop the other program (if you know how
and if it is safe to do so), or you can change the `port` by setting the `APP_PORT` [environment variable]:

```shell
APP_PORT=9000 node src/server.js
```

On Windows, which uses [PowerShell], you need to add `$env:` before the environment variable name:

```shell
$env:APP_PORT=9000 node src/server.js
```

When your server is listening, visit http://localhost:8080 in your web browser. You will see:

```json
{"error":"Resource not found"}
```

This is the `404` error response we defined in the `router` that gets returned for all URL paths except `/ping`.

If you visit http://localhost:8080/ping you will see:

```json
{"status":"healthy"}
```

Congratulations! You just built a [web server]. Pretty soon, we'll make it do something useful.

### Running and debugging Node.js in your IDE

Going back to the terminal, you will notice that hitting enter does not run any commands you type. This is because the
terminal is busy running your server, similar to when you run `docker-compose up` without the `-d` flag. In order to
get your terminal back, you need to press `CTRL+C` to stop the server.

Your [IDE] also provides a way to run (and debug) your application without using the terminal. Take some time to
familiarize yourself with this feature. In particular, learn how the debugger works. It will become one of your most
important tools.

* [Visual Studio Code: Node.js debugging]
* [WebStorm: Running and debugging Node.js]


## 11. Write unit tests using [Jest]

TODO


## 12. Create a Linux web server using [Docker] & [Docker Compose]

TODO


## 13. Read the contents of a file using [fs.readFile]

TODO


## 14. Install and configure [node-postgres] using [NPM]

TODO


## 15. Create a database migration module using [fs.readFile] and [node-postgres]

TODO


## 16. Create a cryptographic one-way [hash] using [crypto.createHash]

TODO


## 17. Create a Command Line Interface ([CLI]) using [Node.js]

TODO


## 18. Create a Data Access Object ([DAO]) for performing [CRUD] operations

TODO


## 19. Create [REST] endpoints for [user registration] and [authentication]

TODO


## 20. Implement a [session management] strategy using an [HTTP cookie] header

TODO


## 21. Create a user login web page using [HTML] and [CSS]

TODO


## 22. Create a user profile web page that requires [authentication] to access

TODO


## 23. Create a user admin page that requires [authorization] to access

TODO


[Alpine Linux]: https://alpinelinux.org/
[API]: https://en.wikipedia.org/wiki/API
[arrow function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions
[async function]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function
[authentication]: https://en.wikipedia.org/wiki/Authentication
[authorization]: https://en.wikipedia.org/wiki/Authorization
[BitBucket]: https://bitbucket.org/product
[changelog]: https://en.wikipedia.org/wiki/Changelog
[CLI]: https://en.wikipedia.org/wiki/Command-line_interface
[clone your repo]: https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository
[CommonJS]: https://en.wikipedia.org/wiki/CommonJS
[CommonJS modules]: https://nodejs.org/docs/latest-v14.x/api/modules.html#modules_modules_commonjs_modules
[conditional logic]: https://en.wikipedia.org/wiki/Conditional_(computer_programming)
[configure an upstream remote]: https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/configuring-a-remote-for-a-fork
[console.error]: https://developer.mozilla.org/en-US/docs/Web/API/Console/error
[console.log]: https://developer.mozilla.org/en-US/docs/Web/API/Console/log
[const]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const
[Content-Type]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type
[CREATE TABLE]: https://www.postgresql.org/docs/13/sql-createtable.html
[CRUD]: https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
[crypto.createHash]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#crypto_crypto_createhash_algorithm_options
[CSS]: https://en.wikipedia.org/wiki/CSS
[DAO]: https://en.wikipedia.org/wiki/Data_access_object
[database migration]: https://en.wikipedia.org/wiki/Schema_migration
[DEFAULT]: https://www.postgresql.org/docs/13/ddl-default.html
[DELETE]: https://www.postgresql.org/docs/13/sql-delete.html
[dependencies]: https://docs.npmjs.com/cli/v6/configuring-npm/package-json#dependencies
[Docker]: https://www.docker.com/get-started
[docker-compose]: https://docs.docker.com/compose/reference/
[docker-compose environment config]: https://docs.docker.com/compose/compose-file/compose-file-v3/#environment
[docker-compose ports config]: https://docs.docker.com/compose/compose-file/compose-file-v3/#ports
[docker-compose up]: https://docs.docker.com/compose/reference/up/
[Docker Compose]: https://docs.docker.com/compose/
[Docker Desktop]: https://www.docker.com/products/docker-desktop
[Dockerfile]: https://docs.docker.com/engine/reference/builder/
[ECMAScript]: https://en.wikipedia.org/wiki/ECMAScript
[ECMAScript modules]: https://nodejs.org/docs/latest-v14.x/api/all.html#esm_modules_ecmascript_modules
[enable coding assistance for Node.js]: https://www.jetbrains.com/help/webstorm/configuring-javascript-libraries.html#ws_js_libraries_node_js_core
[end]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_response_end_data_encoding_callback
[environment variable]: https://en.wikipedia.org/wiki/Environment_variable
[EventEmitter]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#events_class_eventemitter
[export]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/export
[fs.readFile]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#fs_fs_readfile_path_options_callback
[fork this repo]: https://docs.github.com/en/github/getting-started-with-github/fork-a-repo
[functions]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions
[Git]: https://git-scm.com/
[git add]: https://git-scm.com/docs/git-add
[git commit]: https://git-scm.com/docs/git-commit
[git merge]: https://git-scm.com/docs/git-merge
[git pull]: https://git-scm.com/docs/git-pull
[git push]: https://git-scm.com/docs/git-push
[GitHub]: https://docs.github.com/en/github/getting-started-with-github/quickstart
[GitHub Dependabot]: https://docs.github.com/en/code-security/supply-chain-security/configuring-dependabot-security-updates
[GitLab]: https://about.gitlab.com/
[GUI]: https://en.wikipedia.org/wiki/Graphical_user_interface
[hash]: https://en.wikipedia.org/wiki/Cryptographic_hash_function
[HTML]: https://en.wikipedia.org/wiki/HTML
[HTTP]: https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol
[HTTP cookie]: https://en.wikipedia.org/wiki/HTTP_cookie
[HTTP status code]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status
[http.createServer]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_http_createserver_options_requestlistener
[http.IncomingMessage]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_class_http_incomingmessage
[http.Server]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_class_http_server
[http.ServerResponse]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_class_http_serverresponse
[IDE]: https://en.wikipedia.org/wiki/Integrated_development_environment
[if...else]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/if...else
[import]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/import
[INSERT]: https://www.postgresql.org/docs/13/sql-insert.html
[Install Docker Desktop (MacOS)]: https://docs.docker.com/docker-for-mac/install/
[Install Docker Desktop (Windows)]: https://docs.docker.com/docker-for-windows/install/
[install Node.js]: https://nodejs.org/en/download/
[INTEGER]: https://www.postgresql.org/docs/13/datatype-numeric.html#DATATYPE-INT
[Integrated Terminal (VSCode)]: https://code.visualstudio.com/docs/editor/integrated-terminal
[IntelliJ]: https://www.jetbrains.com/idea/
[Jasmine]: https://jasmine.github.io/index.html
[JavaScript]: https://en.wikipedia.org/wiki/JavaScript
[Jest]: https://jestjs.io/docs/getting-started
[JSON]: https://en.wikipedia.org/wiki/JSON
[JSON.parse]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse
[JSON.stringify]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify
[JWT]: https://en.wikipedia.org/wiki/JSON_Web_Token
[let]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let
[libpq connection URI]: https://www.postgresql.org/docs/13/libpq-connect.html#LIBPQ-CONNSTRING
[listening]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#net_event_listening
[logical OR]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR
[LTS]: https://en.wikipedia.org/wiki/Long-term_support
[Mocha]: https://mochajs.org/
[Node packages]: https://docs.npmjs.com/about-packages-and-modules
[Node Version Manager for Windows]: https://github.com/coreybutler/nvm-windows
[Node.js]: https://nodejs.org/dist/latest-v14.x/docs/api/index.html
[Node.js assert]: https://nodejs.org/docs/latest-v14.x/api/all.html#assert_assert
[Node.js changelog]: https://github.com/nodejs/node/blob/master/CHANGELOG.md
[Node.js http]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_http
[node-postgres]: https://node-postgres.com/
[node_modules]: https://docs.npmjs.com/cli/v6/configuring-npm/folders#node-modules
[NOT NULL]: https://www.postgresql.org/docs/13/ddl-constraints.html#id-1.5.4.6.6
[now()]: https://www.postgresql.org/docs/13/functions-datetime.html#FUNCTIONS-DATETIME-CURRENT
[NPM]: https://www.npmjs.com/get-npm
[npm audit]: https://docs.npmjs.com/cli/v6/commands/npm-audit
[npm install]: https://docs.npmjs.com/cli/v6/commands/npm-install
[npmjs.com]: https://www.npmjs.com/
[NVM]: https://github.com/nvm-sh/nvm
[objects]: https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics
[open source]: https://en.wikipedia.org/wiki/Open-source_software
[package.json]: https://docs.npmjs.com/cli/v6/configuring-npm/package-json
[PGWeb]: https://sosedoff.github.io/pgweb/
[postgres:13-alpine]: https://hub.docker.com/_/postgres
[PostgreSQL]: https://www.postgresql.org/docs/13/index.html
[PowerShell]: https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_environment_variables?view=powershell-7.1
[PRIMARY KEY]: https://www.postgresql.org/docs/13/ddl-constraints.html#DDL-CONSTRAINTS-PRIMARY-KEYS
[psql]: https://www.postgresql.org/docs/13/app-psql.html
[pull request]: https://git-scm.com/docs/git-request-pull
[React]: https://reactjs.org/
[relational database]: https://en.wikipedia.org/wiki/Relational_database
[req.url]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http2_request_url
[response body]: https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages#body_2
[response header]: https://developer.mozilla.org/en-US/docs/Glossary/Response_header
[REST]: https://en.wikipedia.org/wiki/Representational_state_transfer
[RTFM]: https://en.wikipedia.org/wiki/RTFM
[semantic versioning]: https://docs.npmjs.com/about-semantic-versioning
[sequence generator]: https://www.postgresql.org/docs/13/sql-createsequence.html
[SERIAL]: https://www.postgresql.org/docs/13/datatype-numeric.html#DATATYPE-SERIAL
[server.on]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#events_emitter_on_eventname_listener
[server.listen]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#net_server_listen
[session management]: https://en.wikipedia.org/wiki/Session_(computer_science)#Session_management
[setHeader]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_response_setheader_name_value
[setting up Git]: https://docs.github.com/en/github/getting-started-with-github/set-up-git#setting-up-git
[shell]: https://en.wikipedia.org/wiki/Shell_(computing)
[sosedoff/pgweb]: https://hub.docker.com/r/sosedoff/pgweb/
[source code]: https://en.wikipedia.org/wiki/Source_code
[SQL]: https://en.wikipedia.org/wiki/SQL
[string]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
[Terminal Emulator (WebStorm)]: https://www.jetbrains.com/help/webstorm/terminal-emulator.html
[TEXT]: https://www.postgresql.org/docs/13/datatype-character.html
[TIMESTAMP]: https://www.postgresql.org/docs/13/datatype-datetime.html
[trigger function]: https://www.postgresql.org/docs/13/plpgsql-trigger.html
[try...catch]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/try...catch
[undefined]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined
[UNIQUE]: https://www.postgresql.org/docs/13/ddl-constraints.html#DDL-CONSTRAINTS-UNIQUE-CONSTRAINTS
[UPDATE]: https://www.postgresql.org/docs/13/sql-update.html
[user registration]: https://en.wikipedia.org/wiki/Registered_user
[UUID]: https://en.wikipedia.org/wiki/Universally_unique_identifier
[VCS]: https://en.wikipedia.org/wiki/Version_control
[virtual machine]: https://en.wikipedia.org/wiki/Virtual_machine
[Visual Studio Code]: https://code.visualstudio.com/
[Visual Studio Code: Node.js debugging]: https://code.visualstudio.com/docs/nodejs/nodejs-debugging
[Vue.js]: https://vuejs.org/
[web server]: https://en.wikipedia.org/wiki/Web_server
[WebStorm]: https://www.jetbrains.com/webstorm/
[WebStorm: Running and debugging Node.js]: https://www.jetbrains.com/help/webstorm/running-and-debugging-node-js.html
[writeHead]: https://nodejs.org/dist/latest-v14.x/docs/api/all.html#http_response_writehead_statuscode_statusmessage_headers
[YAML]: https://en.wikipedia.org/wiki/YAML
