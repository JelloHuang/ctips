Gun C Zero Array
==================
1. 节省空间
* 实现动态扩展，按需要分配
* 缺点？
```c
#define NO 3
#include <stdlib.h>
#include <stdio.h>
struct device{
    int num;
    int count;
  /* reserve 地址紧随结构体device之后 */
    int reserve[0];
};

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
```


	$ git diff --cached
	diff --git a/benchmarks.rb b/benchmarks.rb
	index 3cb747f..e445e28 100644
	--- a/benchmarks.rb
	+++ b/benchmarks.rb
	@@ -36,6 +36,10 @@ def main
	          @commit.parents[0].parents[0].parents[0]
	        end

	+        run_code(x, 'commits 1') do
	+          git.commits.size
	+        end
	+
	        run_code(x, 'commits 2') do
	          log = git.commits('master', 15)
	          log.size