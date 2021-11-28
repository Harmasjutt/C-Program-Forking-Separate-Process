# C-Program-Forking-Separate-Process
#include<sys/types.h>
#include<unistd.h>
int mian()
{
pid_t pid;
pid=fork();
if(pid<0)
{
fprintf(stderr, "Fork Failed");
return 1;
}
else if (pid==0) 
{
execlp("/bin/ls", "ls", NULL);
}
else
{
wait(NULL);
printf("child complete");
}
return 0;
}
