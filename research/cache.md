#Efficiency
Here is the example, some one CPU's L1 cache is 16KB, cache line size is 64B, and L2 cache is 256KB, cache line size is 4KB. So for the following snip of code, which one is better?

This is the A:

    int matrix[1023][15];
    const char *str = "hello world";
    int i, j, sum = 0;

    tmp = strlen(str);
    for ( i = 0; i<1023; i++){
        for ( j = 0; j<15; j++){
            sum += matrix[i][j] + tmp;
        }
    }

And this is the B:

    int matrix[1025][17];
    const char *str = "hello world";
    int i, j, sum = 0;

    for ( i = 0; i<17; i++){
        for (j = 0; j<1025; j++){
            sum += matrix[i][j] + strlen(str);
        }
    }

Sure, first one is better.
