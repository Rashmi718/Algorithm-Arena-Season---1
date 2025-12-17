# SET 1 - QUESTIONS

## Question 1 ) [Selection Sort](https://www.geeksforgeeks.org/problems/selection-sort/1)

- class Solution {
  
      void selectionSort(int[] arr) {
      
          int n = arr.length;
      
          for(int i = 0 ; i < n ; i++){
              int minIndex = i ;
              for(int j = i + 1 ; j < n ; j++){
                  if (arr[minIndex] > arr[j]){
                      minIndex = j ;
                  }
              }
      
              if(minIndex != i){
                  int temp = arr[i] ;
                  arr[i] = arr[minIndex];
                  arr[minIndex] = temp;
              }
          }
      }
  
  }

## Question 2 ) [Bubble Sort](https://www.geeksforgeeks.org/problems/bubble-sort/1)

- class Solution {
  
      public void bubbleSort(int[] arr) {
      
          int n = arr.length;
      
          for(int i = 0 ; i < n ; i++){
              for(int j = 0 ; j < n - i - 1 ; j++){
                  if(arr[j] > arr[j + 1]){
                      int temp = arr[j];
                      arr[j] = arr[j + 1];
                      arr[j + 1] = temp ;
                  }
              }
          }
      }
  
  }
  
  ## Question 3 ) [Merge Sort ](https://www.geeksforgeeks.org/problems/merge-sort/1)
  
  - class Solution {
    
        void mergeSort(int arr[], int l, int r) {
        
            if(l >= r){
                return ;
            }
        
            int mid = l + (r - l)/2;
        
            mergeSort(arr , l  , mid);
            mergeSort(arr , mid + 1 , r);
        
            merge(arr , l , r , mid);
        }
        
        private void merge(int[] nums , int l , int r , int mid){
        
            int n1 = mid - l + 1 ;
            int n2 = r - mid ;
        
            int[] left = new int[n1];
            int[] right = new int[n2];
        
            for(int i = 0 ; i < n1 ; i++){
                left[i] = nums[l + i];
            }
        
            for(int j = 0 ; j < n2 ; j++){
                right[j] = nums[mid + j + 1];
            }
        
            int x = 0 , y = 0 , k = l ;
        
            while(x < n1 && y < n2){
                if(left[x] <= right[y]){
                    nums[k++] = left[x++];
                }
                else{
                     nums[k++] = right[y++];
                }
            }
        
            while(x < n1){
                 nums[k++] = left[x++];
            }
            while (y < n2){
                 nums[k++] = right[y++];
            }
        }
    
    }
    
    ## Question 4 ) [Problem - 339A - Codeforces](https://codeforces.com/problemset/problem/339/A)
    
    - import java.util.Scanner;
      
      public class HelpfulMaths {
      
          public static void main(String[] args) {
              Scanner sc = new Scanner(System.in);
              String s = sc.next();
          
              int count1 = 0, count2 = 0, count3 = 0;
          
              for (int i = 0; i < s.length(); i++) {
                  char ch = s.charAt(i);
                  if (ch == '1') count1++;
                  else if (ch == '2') count2++;
                  else if (ch == '3') count3++;
              }
          
              StringBuilder result = new StringBuilder();
          
              while (count1-- > 0) {
                  result.append("1+");
              }
          
              while (count2-- > 0) {
                  result.append("2+");
              }
          
              while (count3-- > 0) {
                  result.append("3+");
              }
          
              result.deleteCharAt(result.length() - 1);
          
              System.out.println(result);
          }
      
      }
      
      ## Question 5 ) [Problem - 160A - Codeforces](https://codeforces.com/problemset/problem/160/A)
      
      import java.util.Arrays;
      import java.util.Scanner;
      
      public class Main {
      
          public static void main(String[] args){
              Scanner ob = new Scanner(System.in);
              int n = ob.nextInt();
              int[] coins = new int[n];
          
              for(int i = 0 ; i < n ; i++){
                  coins[i] = ob.nextInt();
              }
          
              Arrays.sort(coins);
          
              int total = 0;
              for(int i : coins){
                  total += i;
              }
          
              int sum = 0;
              int count = 0;
          
              for(int i = n - 1 ; i >= 0 ; i--){
                  sum += coins[i];
                  count++;
                  if(sum > total - sum){
                      break;
                  }
              }
          
              System.out.println(count);
          }
      
      }
