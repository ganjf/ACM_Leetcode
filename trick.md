## 精选技巧

### 1. 双指针    
- 3. 无重复字符的最长子串 [[problem]](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)   
- [x] (中等)leetcode 16. 最接近的三数之和[[problem]](https://leetcode-cn.com/problems/3sum-closest/)  





### 2. 二分  
[[二分讲解参考]](https://blog.csdn.net/CCSGTC/article/details/80586181)  

- 左闭右开  
[l,r）  
```cpp
int l=0,r=n;
while(l<r)
{
	r=middle;
	l=middle+1;
}
```



- 左闭右闭  
[l,r]   
```cpp
int l=0,r=n-1;
while(l<=r)
{
	r=middle-1;
	l=middle+1;
}
```

- 左开右开  
(l,r)   
```cpp
int l=-1,r=n;
while(l+1!=r)
{
	r=middle;
	l=middle;
}
```
- 二分模板 (求非下降序列的首次首次出现的位置) 
```cpp
int binary(int array[],int n,int target)
{
    int left,right,middle;
    left=-1,right=n;
    while(left+1!=right){
        middle=left+(right-left)/2;
        if(array[middle]>=target){
            right=middle;
        }else{
            left=middle;
        }
    }
    if(right==n||array[right]!=target)
        return -1;
    return right;
}
```

#### 快速幂(也算是二分的一种思想)  

```cpp
Matrix quickPower(Matrix A, int k){
    Matrix result=I;
    while(k>0)
    {
        if(k%1==1)result=result*A;
        k=k/2;
        result=result*result;
    }
    return result;
}
```






- 二分搜索题集 [[leetcode]](https://leetcode-cn.com/tag/binary-search/)     
- [ ] (困难)Leetcode 4. 寻找两个有序数组的中位数 [[problem]](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/)    
- [x] (中等)Leetcode 29. 两数相除 [[problem]](https://leetcode-cn.com/problems/divide-two-integers/)  
- [x] (中等)Leetcode 33.搜索旋转排序数组  [[problem]](https://leetcode-cn.com/problems/search-in-rotated-sorted-array/) [[题解]](https://blog.csdn.net/Fire_to_cheat_/article/details/104196694)    
- [x] (中等)Leetcode 34. 在排序数组中查找元素的第一个和最后一个位置 [[problem]](https://leetcode-cn.com/problems/find-first-and-last-position-of-element-in-sorted-array/)    
- [x] (中等)Leetcode 50. Pow(x, n) [[problem]](https://leetcode-cn.com/problems/powx-n/)  
- [x] (中等)Leetcode 74. 搜索二维矩阵 [[problem]](https://leetcode-cn.com/problems/search-a-2d-matrix/)    
- [x] (中等)Leetcode 81. 搜索旋转排序数组 II [[problem]](https://leetcode-cn.com/problems/search-in-rotated-sorted-array-ii/)  
- [ ] (中等)Leetcode 153. 寻找旋转排序数组中的最小值 [[problem]](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array/)   
- [ ] (困难)Leetcode 154. 寻找旋转排序数组中的最小值 II [[problem]](https://leetcode-cn.com/problems/find-minimum-in-rotated-sorted-array-ii/)   
- [ ] (中等)Leetcode 162. 寻找峰值 [[problem]](https://leetcode-cn.com/problems/find-peak-element/)   








### 3. 排序

- **归并排序**  
时间复杂度： O(nlogn)   
归并排序是基于分治思想的排序方法。  
归并排序a[l,r]的算法，简要描述为：  
（1）将a[l,r]拆成a[l,mid],a[mid+1,r]两部分  
（2）调用MergeSort(l,mid)和MerSort(mid+1,r),将这两部分分别排好序  
（3）合并排好序的两部分，覆盖a[l,r]  
关于合并过程：  
（1）如果A取完，那么直接从B中取；  
（2）如果B取完，那么直接从A中取；  
（3）如果A，B都没取完，那么从A，B的头部，取更小的那个；    
```cpp
int source[100],target[100];
void merge(int left,int mid,int right)
{
    int i=left,j=mid+1,k=left;
    while(i<=mid&&j<=right)
    {
        if(source[i]<source[j])
        {
            target[k++]=source[i++];
        }
        else
        {
            target[k++]=source[j++];
        }
    }
    while(i<=mid)
    {
       target[k++]=source[i++];
    }
    while(j<=right)
    {
        target[k++]=source[j++];
    }
    for(int ss=left;ss<=right;++ss)
        source[left]=target[left];

}
void MergeSort(int left,int right)
{
    int mid=(left+right)/2;
    MergeSort(left,mid);
    MergeSort(mid+1,right);
    merge(left,mid,right);
}

```

- **快排**     
时间复杂度：O(nlogn)   
以身高排序为例：  
（1）选择一个人  
（2）将比这个人矮的放到左边去  
（3）将比这个人高的放到右边去  
（4）对这个人坐便和右边分别进行相似的递归排序  
```cpp
template<class Type>
int partition(Type array[],int left,int right)
{
    int flag=array[left];
    while(left<right)
    {
        //put all x < flag to left
        while(left<right&&array[right]>=flag)
        {
            right--;
        }
        if(left<right)
        {
            array[left]=array[right];
            left++;
        }
        //put all x>flag to right
        while(left<right&&array[left]<=flag)
        {
            left++;
        }
        if(left<right)
        {
            array[right] = array[left];
            right--;
        }
    }
    //left and right 重合时，将flag放置中间
    array[left]=flag;
    return left;
}
template<class Type>
void quick_sort(Type array[],int left,int right)
{
    if(left<right)
    {
        int position=partition(array,left,right);
        quick_sort(array,left,position-1);
        quick_sort(array,position+1,right);
    }
}
```