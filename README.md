# EasyMultiProcessing
A auto-wrapped multiprocessing tool using Multiprocessing.


### usage
To use this tool, you can download and put the EasyMultiProcessing under your project directory or add into the system path.

```python
from EasyMultiProcessing import EMP  
from time import sleep
	
# define a function you want run with multiprocessing 
# the first parameter will be various across the threads
# the rest parameters will be static. 
	
def f(n,stime=1):
	sleep(stime)   
	print n
	
# set f() and number of threads
emp = EMP(f,10)
# pass first parameters list
emp.set_jobs(range(10))
emp.execute()  
```  

[out]:(The order could be different every times. )

	1
	2
	0
	3
	4
	5
	6
	7
	8
	9  
If verbose,	

```python    
emp.execute(verbose=1)
```
[out]:

	1
	2
	0
	Job: 1 executed by #1, elasped time: 1.0
	Job: 2 executed by #2, elasped time: 1.0
	Job: 0 executed by #0, elasped time: 1.0
	4
	3
	Job: 3 executed by #3, elasped time: 1.0
	Job: 4 executed by #4, elasped time: 1.0
	5
	6
	Job: 5 executed by #5, elasped time: 1.0
	Job: 6 executed by #6, elasped time: 1.0
	8
	7
	Job: 7 executed by #7, elasped time: 1.0
	Job: 8 executed by #8, elasped time: 1.0
	9
	Job: 9 executed by #9, elasped time: 1.0
or pass more parameters to f( ):


```python
emp.set_args(stime=2)
emp.execute(verbose=1)  
```
			
[out]:     

	0
	1
	2
	Job: 1 executed by #1, elasped time: 2.0
	Job: 2 executed by #2, elasped time: 2.0
	Job: 0 executed by #0, elasped time: 2.0
	3
	Job: 3 executed by #3, elasped time: 2.0
	4
	Job: 4 executed by #4, elasped time: 2.0
	5
	Job: 5 executed by #5, elasped time: 2.0
	7
	6
	Job: 7 executed by #7, elasped time: 2.0
	Job: 6 executed by #6, elasped time: 2.0
	8
	Job: 8 executed by #8, elasped time: 2.0
	9
	Job: 9 executed by #9, elasped time: 2.0
	