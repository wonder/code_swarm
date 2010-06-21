code_swarm is an experiment in organic software visualization.

See http://vis.cs.ucdavis.edu/~ogawa/codeswarm for a picture of what we want
to produce.

Google Code Project :      http://code.google.com/p/codeswarm/
Google Group/Mailing List: http://groups.google.com/group/codeswarm 


# Building #

## Prerequisites ##

You will need the Apache ant build tool, at least version 5 of the Java SDK from Sun, and Python version 2.4 or later.  Linux users: we've been unable to get code_swarm to compile with the GNU toolchain, Sun's implementation is strongly recommended.  If you're able to get it to compile with another toolchain, we'll be glad to include instructions here on how to do so.


### Arch Linux ###

        # pacman -S apache-ant jre jdk

### git ###

A git fork of the main code_swarm repository is maintained at <http://github.com/rictic/code_swarm/tree/master>

This fork contains a number of patches which improve the speed of code_swarm significantly, 
as well as an executable, which makes running code_swarm a one-step process.

To obtain a clone of the repository, simply use:

    git clone git://github.com/rictic/code_swarm.git

### Subversion ###

The main code_swarm repository however is on Google Code:
<http://codeswarm.googlecode.com/>

To get the source, see <http://code.google.com/p/codeswarm/source/checkout>


## Running code_swarm ##

With Java and ant installed, and the code_swarm source downloaded, running it on a git, svn, or hg based project is easy:

* Add `code_swarm/bin` to your PATH.  A line like `export PATH=$PATH:/path/to/code_swarm/bin` in your `~/.profile` or `~/.bash_profile` should do it
* `cd project/to/visualize`
* `code_swarm`


## Other ways of running code_swarm ##

### Running manually ###

While code_swarm was developed to visualize source code repositories, its input format is generic, and some have experimented with visualizing other collaborative environments, including user activity on wikis and freebase.com.

code_swarm can be invoked by pointing it at a project config file, which contains a number of options for customizing the visualization.  The config file must point at a repository xml file, which contains a set of events, which each describe a file, edited by a person, at a specific time.  The time is specified as the number of milliseconds since January 1st, 1970.

Example config files can be seen in `data/sample.config` and `bin/config.template`

To invoke `code_swarm` with a given config file, use `./run.sh path/to/project.config`

#### SVN GUI ####
For an experimental GUI where you can specify a svn url to visualize:

* `cd path/to/code_swarm`
* `ant run`

Other commands:

* `ant` will build, but not run the project
* `ant all` will also generate Javadoc HTML documentation
* `ant clean` will delete all intermediate and binary files 


### OpenGL support ###

i686
* export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<path_to_code_swarm/lib/>
x86_64
* export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:<path_to_code_swarm/lib/linux-x86_64>
