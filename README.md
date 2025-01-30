#include <stdio.h>
int main()
{
    int n,m;
    printf("Enter the number of rows and columns: ");
    scanf("%d %d", &n,&m);
    int matrix[n][m];
    printf("enter the matrix values: \n");
    for(int i = 0;i<n;i++){
        for(int j= 0; j<m; j++){
            scanf("%d", &matrix[i][j]);
        }
    }
    int left = 0,top = 0, right = m-1, bottom= n-1;
    while(left<=right && top<=bottom){
        for(int i =left;i<= right;i++){
            printf("%d ", matrix[top][i]);
        }
        top++;
        for(int i = top; i<=bottom; i++){
            printf("%d ", matrix[i][right]);
        }
        right--;
        if(top<=bottom){
            for(int i = right;i>=left;i--){
                printf("%d ", matrix[bottom][i]);
            }
            bottom--;
        }
        if(left<=right){
            for(int i=bottom;i>=top;i--){
                printf("%d ", matrix[i][left]);
            }
            left++;
        }
    }
    return 0;
}
