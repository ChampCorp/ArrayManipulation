# ArrayManipulation
static long arrayManipulation(int n, int[][] queries) {

        long[] ar=new long[n];

        for(int i=0;i<n;i++)
        {
            ar[i]=0;
        }
        int lower;
        int upper;
        long sum;

        for(int i=0;i<queries.length;i++)
        {
            lower=queries[i][0];
            upper=queries[i][1];
            sum=queries[i][2];

            ar[lower-1]+=sum;
            if(upper<n)
            {
                ar[upper]-=sum;
            }
        }
        long max=0;
        long temp=0;
        for(int i=0;i<n;i++)
        {
            temp+=ar[i];
            if(max<temp)
            {
                max=temp;
            }
        }

return max;
    }
