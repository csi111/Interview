#Algorithm

### 정렬 알고리즘 중 아는 정렬 알고리즘에 대해 말하고 시간복잡도에 대해 말하기

**Bubble sort**

평균 : n^2
최악 : n^2

**Selection sort**

평균 : n^2
최악 : n^2

**Insertion sort**

평균 : n^2
최악 : n^2

**Quick sort**

평균 : nlogn
최악 : n^2

**Merge sort**

평균 : nlogn
최악 : nlogn

**Heap sort**

평균 : nlogn
최악 : nlogn


### 검색 알고리즘 중 아는 알고리즘에 대해 말하기

**Unordered Linear Search(무순서 선형 검색)**

**Sorted/Ordered Linear Search(정렬/순서 선형 검색)**

**Binary Search(이진 검색)**


### 1 ~ 1000까지 중 임의의 숫자를 찾는데 사용하는 기법 및 최대 몇번만에 찾을 수 있는지
- BinarySearch

### String reverse 기법


	 public class ReverseInPlace {

	  static char[]  str=null;

	    public static void main(String s[]) {
	      if(s.length==0)
		System.exit(-1);

	       str=s[0].toCharArray();

	       int begin=0;
	       int end=str.length-1;

	       System.out.print("Original string=");
	       for(int i=0; i<str.length; i++){
		 System.out.print(str[i]);
	       }

	       while(begin<end){
		  str[begin]= (char) (str[begin]^str[end]);
		  str[end]= (char)   (str[begin]^str[end]);
		  str[begin]= (char) (str[end]^str[begin]);

		  begin++;
		  end--;       
	       }

	       System.out.print("\n" + "Reversed string=");
	       for(int i=0; i<str.length; i++){
		 System.out.print(str[i]);
	       }

	    }
	}
 
	 public AbstractStringBuilder reverse() {
		    boolean hasSurrogate = false;
		    int n = count - 1;
		    for (int j = (n-1) >> 1; j >= 0; --j) {
			char temp = value[j];
			char temp2 = value[n - j];
			if (!hasSurrogate) {
			    hasSurrogate = (temp >= Character.MIN_SURROGATE && temp <= Character.MAX_SURROGATE)
				|| (temp2 >= Character.MIN_SURROGATE && temp2 <= Character.MAX_SURROGATE);
			}
			value[j] = temp2;
			value[n - j] = temp;
		    }
		    if (hasSurrogate) {
			// Reverse back all valid surrogate pairs
			for (int i = 0; i < count - 1; i++) {
			    char c2 = value[i];
			    if (Character.isLowSurrogate(c2)) {
				char c1 = value[i + 1];
				if (Character.isHighSurrogate(c1)) {
				    value[i++] = c1;
				    value[i] = c2;
				}
			    }
			}
		    }
		    return this;
		}
 


### String 검색 기법

### Heap과 Queue에 대해 설명

### 정렬되어 있지 않은 2 A,B 배열에서 A차집합, B차집합, 교집합을 구하는 알고리즘을 구하시오.



