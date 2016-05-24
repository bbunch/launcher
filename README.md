
# Sbt Launcher Module For Oildex IntelliJ Support

This project is a fork of the sbt/launcher project that allows Oildex personnel to run activator or sbt projects that require the Oildex SbtGitUtils scala source file that is pulled down as a dependency through the $HOME/opt/bin/sbtGitActivator script.

The only two additions to the source code are an sbt/sbt.boot.properties file that matches IntelliJ's scala plugin sbt-launch.jar version, and a few additional lines added to the source file

# How To Build The sbt-launch JAR:

1. Set the JDK to a 1.7 JDK (sbt versions less that 1.0.x require a 1.7 JVM to compile):
```
    $ setJdk 1.7
```

2. Build the sbt-launch jar:
```
    $ sbt clean compile package
```

# How To Open An IntelliJ sbt Project Using The New sbt-launch JAR:

1. If the project was previous open up with IntelliJ and is currently having problems opening, delete any .idea directory or *.ipr files from the project's root directory

2. Open the root directory containing the project in IntelliJ.

3. Set the "SBT Project" settings as usual, but also expand the "Global SBT settings" section and set the "Launcher (sbt-launcher.jar)" value to point to the sbt-launcher.jar file you built above in the section "How To Build The sbt-launch JAR". For my machine, this ended up being something like "/Users/bbunch/git_repos/bbunch/launcher/target/sbt-launch-1.0.0-SNAPSHOT.jar".

4. The project should now load successfully in IntelliJ from this point forward.


See the original sbt launcher module README.md file here --> https://github.com/sbt/launcher/blob/0.13/README.md
