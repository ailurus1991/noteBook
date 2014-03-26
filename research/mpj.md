#Before
Set MPJ_HOME and PATH variables:

    export MPJ_HOME=/path/to/mpj/
    export PATH=$PATH:$MPJ_HOME/bin

set them in a bash script, use `source xx.sh` to added them in to system variables.

#Usage
Sample code:

    import mpi.*;
    public class HelloWorld{
        public static void main(String main[]) throws Exception{
            MPI.Init(args);
            int me = MPI.COMM_WORLD.Rank();
            int size = MPI.COMM_WORLD.Size();
            System.out.println("Hi From <+me+>");
            MPI.Finalize();
        }
    }

#Run
First should compile: `javac -cp .:$MPJ_HOME/lib/mpj.jar HelloWorld.java`, then execute: `mpjrun.sh -np 2 HelloWorld`.

#Notes
Since the execute command is `mpjrun.sh -np 2 xxx`, so we can use `args[1]` to indicate the rankAll.
