# Codingame Summer Challenge 2025 - SoakOverflow
This is a fork of the original referee, adding the ability to run it through commandline.
## Usage

For a shorter command, rename the compiled `summer-challenge-2025-super-soaker-1.0-SNAPSHOT.jar` to `summer-2025.jar`

Example Run

```bash
java -jar ./summer-2025.jar -p1 "summerChallenge2025.exe" -p2 "summerChallenge2025.exe" -s
```  
This will launch the game in server mode. You can view the result at [http://localhost:8888/test.html](http://localhost:8888/test.html).

You can run the game using any programming languages. For example, to run a game between Player 1 written in C++ and Player 2 written in Ruby:
```bash
java -jar ./summer-2025.jar -p1 "summerChallenge2025.exe" -p2 "ruby summerChallenge.rb"
```

Running with a Specific Seed and server mode:
```bash
java -jar ./summer-2025.jar -p1 "summerChallenge2025.exe" -p2 "ruby summerChallenge.rb" -s -seed 4810290338070827112 
```

#### Available Flags

-   `-h`: Print the help
-   `-p1` _<command>_: **Required.** Player 1 command line.
-   `-p2` _<command>_: **Required.** Player 2 command line.
-   `-s`: Server mode
-   `-league` _<level>_: League level
-   `-seed` _<seed>_: Seed
-   `-l` _<file>_: File output for logs
-   `-d`: Referee initial data

#### brutaltester
https://github.com/dreignier/cg-brutaltester
Example Run with brutaltester

```bash
java -jar cg-brutaltester.jar -r "java -jar summer-2025.jar" -p1 "summerChallenge2025.exe" -p2 "ruby summerChallenge.rb" -t 3 -n 15 -l "./logs/"
```
This command runs the game using brutaltester with the following options:

-   `-r "java -jar winter-2024.jar"`: Specifies the game runner.
-   `-p1 "summerChallenge2025.exe"`: Command for Player 1.
-   `-p2 "ruby summerChallenge.rb"`: Command for Player 2.
-   `-t 3`: Number of threads to use.
-   `-n 15`: Number of games to run.
-   `-l "./logs/"`: Directory for log outputs.

### Build and use the jar
Building the JAR with a functional viewer has some requirements:
- JDK 17
- Maven
- a recent Node version (successfully tested with Node >= v20.14)
Steps:
- First build the viewer:
  ```bash
  cd src/main/resources
  npm install
  npm run build
  ```
- Then, build the JAR from the root project directory:
  ```bash
  mvn package
  ```
You can then run the built Jar (located in `target/summer-challenge-2025-super-soaker-1.0-SNAPSHOT.jar`) with the command `java -jar summer-challenge-2025-super-soaker-1.0-SNAPSHOT.jar`.