# Set-Mismatch-using-Java-Leetcode

    class Solution {
        public static void sort(int[] arr){
            int i = 0;
            while(i<arr.length){
                int correct = arr[i]-1;
                if(i<arr.length && arr[i]!=arr[correct]){
                    swap(arr,i,correct);
                }
                else{
                    i++;
                }
            }
    
        }
        public static void swap(int[] arr, int i, int correct){
            int temp;
            temp = arr[i];
            arr[i] = arr[correct];
            arr[correct]=temp;
        }
        public int[] findErrorNums(int[] nums) {
            int arr[] = new int[2];
            Solution obj = new Solution();
            obj.sort(nums);
            for(int i =0; i<nums.length;i++){
                if(i+1 != nums[i]){
                    arr[0]= nums[i];
                    arr[1] = i+1;
                }
            }
            return arr;
        }
    }
