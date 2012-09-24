Gun C Zero Array
==================
1. 节省空间
* 实现动态扩展，按需要分配
* 缺点？
	$ git status
	# On branch master

	#
	# Changes to be committed:
	#
	#	modified:   benchmarks.rb
	
	#
	# Changed but not updated:
	#
	#	modified:   benchmarks.rb
	#	
	int num;
    #define NO 3
    #include <stdlib.h>
    #include <stdio.h>
    struct device{
    int num;
    int count;
    /* reserve 地址紧随结构体device之后 */
     int reserve[0];
    ;
	
    int main()
    {
    int next_val = 0;
    int for_reserve[NO] = {1, 2 ,3};
    struct device * p_dev =
    (struct device *) malloc (sizeof(struct device) + sizeof(for_reserve));
		p_dev->reserve[0] = 4;
		p_dev->reserve[1] = 5
		p_dev->reserve[2] = 6;
	   	int next_val = *(&p_dev->count + 1); 
	    	printf("next_val = %d\n", next_val);
		printf("sizeof(struct device) = %d\n",sizeof(struct device));
	}
