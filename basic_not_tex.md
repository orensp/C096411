

- [Introduction:type of learning](#intro)
- [Linear regression-2D-Model](#LR_2D)
  - [2D-Model-Generalization](#LR_G)
- [Linear regression-nD-Model](#LR_nD)
- [Perceptron](#PR)
- [Logistic Regression](#LR)
- [SVM](#SVM)



<a name='intro'></a>
## Quick Intro

This course is an introduction to machine learning basics theory and practice. There are 3 different types of learning:

### Supervised learning
supervised learning is maybe the most common modern way of teaching. In this method a "Teacher" shows you an example
and you are required to repeat the example logic on some other examples.

<p align="center">
	<img src="./Lesson_0/image1.PNG" />
</p>


### Unsupervised learning:

Unsupervised learning is a way to make Decisions based on correlation in the data.

<p align="center">
	<img src="./Lesson_0/Image2.PNG" align="middle" >
</p>

### Reinforcement learning:

Reinforcement learning is based on interaction with the environment. The learning is done using Trial and error. 

<p align="center">
	<img src="./Lesson_0/Image3.PNG" align="middle">
</p>


<a name='LR'></a>
## Linear regression 



### 2D Basic Model:
<a name='LR_2D'></a>
#### Notations:

<p align="center"><img src="/tex/22c334ae8bcb7e16305cf8fb11ac0b7e.svg?invert_in_darkmode&sanitize=true" align=middle width=500.97334319999993pt height=92.90415915pt/></p>



In linear regression we assume the connection between X and Y is linear:
<img src="/tex/0c30b8a45eb9c4b777e0681c018f1f45.svg?invert_in_darkmode&sanitize=true" align=middle width=110.50777649999998pt height=31.141535699999984pt/> trying to fit <img src="/tex/f4661f991f454717a2f55bca1bbb53ea.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> in order to achieve the lowest error.(we want <img src="/tex/39053daaabd24fd4a891b570d0e8b71f.svg?invert_in_darkmode&sanitize=true" align=middle width=14.194299900000003pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>)

<p align="center">
	<img src="./Lesson_1/Capture1.PNG" align="middle">
</p>

In order to achieve the learning goal(<img src="/tex/4be0688c6c52f0fe18ef69ee724c7114.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=31.141535699999984pt/> to be as close as possible to <img src="/tex/706e1c19ba787c7c4276ce74576768d6.svg?invert_in_darkmode&sanitize=true" align=middle width=14.19429989999999pt height=22.465723500000017pt/>) we want to minimize the sum of all  error(green line) as much as possible. 

#### Formulation:

<img src="/tex/d02322874875d8983fec512aac90f760.svg?invert_in_darkmode&sanitize=true" align=middle width=383.3007585pt height=44.51174640000002pt/>
	
The goal is to find <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/>that minimize the error.

##### Finding <img src="/tex/c7465abf79886de740526c2dd62ad830.svg?invert_in_darkmode&sanitize=true" align=middle width=41.69713019999999pt height=14.15524440000002pt/> that minimize this equation:

<p align="center">
	<img src="./Lesson_1/Capture4.PNG" align="middle">
</p>

<a name='LR_G'></a>
#### Generalization :


Our main goal is to do well on the real world not on our training set S. 
Let’s assume the real world model is not a linear model but it's possible to draw a line such that
<img src="/tex/a5a3c89b53bed887e7e194b0670abc9a.svg?invert_in_darkmode&sanitize=true" align=middle width=17.35165739999999pt height=24.657735299999988pt/>errors(green lines) would be 0. in this case we can imagine the error as a independent variable with a
variance <img src="/tex/8cda31ed38c6d59d14ebefa440099572.svg?invert_in_darkmode&sanitize=true" align=middle width=9.98290094999999pt height=14.15524440000002pt/> and mean=0:

<img src="/tex/80a688401b2d63aeb61914789c6784da.svg?invert_in_darkmode&sanitize=true" align=middle width=75.07395389999999pt height=31.141535699999984pt/>

##### such that:

<img src="/tex/1ec3912580fb1d17e3ff7a933d340d92.svg?invert_in_darkmode&sanitize=true" align=middle width=315.79105634999996pt height=31.141535699999984pt/>
<img src="/tex/990044b31ea09b9285e605a03b2cbb15.svg?invert_in_darkmode&sanitize=true" align=middle width=147.56832089999997pt height=24.65753399999998pt/>
<img src="/tex/16eace060c1897c05b280e5f00ef4f81.svg?invert_in_darkmode&sanitize=true" align=middle width=147.56832089999997pt height=24.65753399999998pt/>

##### Lets prove the equality for <img src="/tex/20a4327baf8921ad57cf2147ad7baf8d.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=22.831056599999986pt/> and <img src="/tex/c6d01153a10d0697e4ab58473caede07.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=22.831056599999986pt/> holds:

<p align="center"><img src="/tex/3458ec4e9d788b903089ed1dfcc6bc90.svg?invert_in_darkmode&sanitize=true" align=middle width=486.9725916pt height=167.67248684999998pt/></p>

<a name='LR_nD'></a>
### General case nD Model:


Until now we only dealt with 2-dimension case Y=w1x+b This section goal is to generalize to n Dimensions :

<p align="center"><img src="/tex/b19f2899fc690a170bfb567feb9dd070.svg?invert_in_darkmode&sanitize=true" align=middle width=157.88615865pt height=69.71700614999999pt/></p>

#### The equation is now:

<p align="center"><img src="/tex/6fc422262f6502040f3f70c54e85d136.svg?invert_in_darkmode&sanitize=true" align=middle width=239.41068689999997pt height=32.940961349999995pt/></p>

#### Finding <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that minimize this equation:

<img src="/tex/380e0bd4a705031f0b3ea2ee23979386.svg?invert_in_darkmode&sanitize=true" align=middle width=270.3127812pt height=34.099002299999995pt/>

<a name='PR'></a>
## Perceptron



Our main goal is to find a linear separation rule for data that can be separated by a line:
<p align="center">
	<img src="./Lesson_2/graph3.PNG" align="middle">
</p>

### Geometrical explanation(line point distance):

This section provide short explanation on how to compute distance between point and a line.  

<p align="center">
	<img src="./Lesson_2/graph1.PNG" align="middle">
</p> 

#### In general <img src="/tex/c3d34d8a63a41701e5954f9b612f25f9.svg?invert_in_darkmode&sanitize=true" align=middle width=100.96246379999998pt height=22.831056599999986pt/>=distance from line with normal  <img src="/tex/a166e09ebe3a9840702c0d0159854a2d.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=22.831056599999986pt/> and offset <img src="/tex/747fe3195e03356f846880df2514b93e.svg?invert_in_darkmode&sanitize=true" align=middle width=16.78467779999999pt height=14.15524440000002pt/>

### Perceptron algorithm:

<table>
	<tr>
		<td>

* Sample m datapoints

* intialize <img src="/tex/32902e719b16dec67b28c9943762cd89.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>

* loop time t:

	* loop samples m:

		* if wrong classification

			* update W
</td>
<td>
	
<p align="center"><img src="/tex/7135738a947389929a37bb3299d4ba00.svg?invert_in_darkmode&sanitize=true" align=middle width=282.23711999999995pt height=144.10433565pt/></p>
		</td>
	</tr>
	</table>
	

#### Understanding perceptron update rule:

<img src="/tex/674adff4f45b5ae8d3fae7a9370a1d76.svg?invert_in_darkmode&sanitize=true" align=middle width=118.63936259999998pt height=26.085962100000025pt/> means wrong classification we updated <img src="/tex/d5e78f926bd247c412fa80e755e437a1.svg?invert_in_darkmode&sanitize=true" align=middle width=119.45003564999998pt height=26.76175259999998pt/>. 
Lets check how the new <img src="/tex/763aa9768edf29e38a67642e3db1b250.svg?invert_in_darkmode&sanitize=true" align=middle width=32.43161954999999pt height=26.76175259999998pt/> is doing on the <img src="/tex/94c7199511ac0e9502948310ce626c41.svg?invert_in_darkmode&sanitize=true" align=middle width=34.88399804999999pt height=14.15524440000002pt/> example:

<p align="center"><img src="/tex/11d3aa5416cae805ac4e63831a8fdbd1.svg?invert_in_darkmode&sanitize=true" align=middle width=595.2313883999999pt height=42.202701749999996pt/></p>

#### Optimal soultion:

<table>
	<tr>
		<td>
			<img src="./Lesson_2/graph3.PNG" >	
		</td>
		<td>
			<img src="./Lesson_2/graph6.PNG" >
		</td>
	</tr>
	
</table>
	
The optimal solution is defined has the solution which produce the highest margin. 
In order to find this optimal solution let's go back to our equation:

distance=<img src="/tex/748de6f1b026b5ed4622a99baffb9d13.svg?invert_in_darkmode&sanitize=true" align=middle width=102.23534639999998pt height=22.831056599999986pt/> distance=<img src="/tex/1259a31d367c8c38a0b0e64b82c7daf4.svg?invert_in_darkmode&sanitize=true" align=middle width=103.23081614999998pt height=22.853275500000024pt/>

We can see that the distance is dependent in ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>||. The lower ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>|| is the bigger the distance is.
From this we can derive the second perceptron role: argmin ||<img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>||


####  Perceptron converges rule:

##### definitions: 

- B=||<img src="/tex/03bf6257eb4b5d50fd63aaa53d700d19.svg?invert_in_darkmode&sanitize=true" align=middle width=19.041115499999986pt height=15.296829900000011pt/>||, R=max||<img src="/tex/9fc20fb1d3825674c6a279cb0d5ca636.svg?invert_in_darkmode&sanitize=true" align=middle width=14.045887349999989pt height=14.15524440000002pt/>||

- <img src="/tex/53970d43610c488387e855d9433b2942.svg?invert_in_darkmode&sanitize=true" align=middle width=257.31636315000003pt height=24.65753399999998pt/>

- <img src="/tex/6568f309e8e4f886f0c80443d0469fce.svg?invert_in_darkmode&sanitize=true" align=middle width=48.333205799999995pt height=26.76175259999998pt/>(intialization to 0)


###### Assumptions:

Lets assume linear seperation is possible.

 ###### goal:
 
 We want to show that perceptron algorithm will stop after <img src="/tex/7c7d3a7854511a059790770fab7c4198.svg?invert_in_darkmode&sanitize=true" align=middle width=45.239853449999984pt height=26.76175259999998pt/> steps.
 
 In order to show that we wil proof that:
 
<img src="/tex/b582dfebdac8ce224e0948f8e5ce3ecc.svg?invert_in_darkmode&sanitize=true" align=middle width=169.96601489999998pt height=64.98593639999997pt/>

**It's easy to see that <img src="/tex/75ca610631ecb0c8123b521555a8e683.svg?invert_in_darkmode&sanitize=true" align=middle width=75.98248514999999pt height=33.20539859999999pt/> is equivalent to <img src="/tex/f23534ae3f27483fe70d757977b736a2.svg?invert_in_darkmode&sanitize=true" align=middle width=66.26136165pt height=26.76175259999998pt/>
 
##### proof:

left inequality : 

<img src="/tex/aa2157b190813cfbad2c9d7deec390cc.svg?invert_in_darkmode&sanitize=true" align=middle width=232.25560049999996pt height=96.21901409999997pt/>

The right inequality:

##### (1) <img src="/tex/9e2b68896587ef3a6470f22dec1aaa93.svg?invert_in_darkmode&sanitize=true" align=middle width=132.67835295pt height=27.6567522pt/> proof:

- The update term of the perceptron is:

	* <img src="/tex/0c28d3e7419815e882ada9fdea8d7915.svg?invert_in_darkmode&sanitize=true" align=middle width=119.45003564999998pt height=26.76175259999998pt/>

- In general we can write <img src="/tex/43613c3dd9fdff7ce34d1e976e2b2ed3.svg?invert_in_darkmode&sanitize=true" align=middle width=15.472805699999988pt height=27.15900329999998pt/>:

	* <img src="/tex/a23a0f0c54ba707df9925cf074c5eec2.svg?invert_in_darkmode&sanitize=true" align=middle width=135.76753904999998pt height=31.75825949999999pt/>

- This means we can write <img src="/tex/b25a79ea3630f9ea0167e75ed6210c07.svg?invert_in_darkmode&sanitize=true" align=middle width=36.999522449999986pt height=27.6567522pt/> as:

	* (P.1.1) <img src="/tex/734b32c714d73d536ed947528f09ffaa.svg?invert_in_darkmode&sanitize=true" align=middle width=278.55151005pt height=32.256008400000006pt/>

- Also by definition because <img src="/tex/03bf6257eb4b5d50fd63aaa53d700d19.svg?invert_in_darkmode&sanitize=true" align=middle width=19.041115499999986pt height=15.296829900000011pt/> is the soultion and we assume linear seperation:

	* (P.1.2) <img src="/tex/c3df0edc208d80ffd2a4fdc9de096c11.svg?invert_in_darkmode&sanitize=true" align=middle width=119.24458094999999pt height=22.465723500000017pt/>

- Using both (P.1.1)+(P.1.2) 

	* <img src="/tex/7d5d6104b5a3a904557af74bfb1f1c2c.svg?invert_in_darkmode&sanitize=true" align=middle width=286.22843865pt height=32.256008400000006pt/>
 
#####  (2)  <img src="/tex/b404999f17c717e01dfc95a94422cdab.svg?invert_in_darkmode&sanitize=true" align=middle width=116.42872394999998pt height=27.6567522pt/> proof:


  - <img src="/tex/712c82a89d883233d22ae641649fc7d7.svg?invert_in_darkmode&sanitize=true" align=middle width=486.37012379999993pt height=27.6567522pt/>
  
  	<img src="/tex/a5fc0e0e1084e567fef1a0f45c90bc1e.svg?invert_in_darkmode&sanitize=true" align=middle width=215.59230990000003pt height=27.6567522pt/>
  
  - now we can do the same repeatedly for <img src="/tex/8ba23cbb1c4581f0d9d2ad6552458e81.svg?invert_in_darkmode&sanitize=true" align=middle width=45.994941299999994pt height=27.6567522pt/> until we get:
  
	* <img src="/tex/b404999f17c717e01dfc95a94422cdab.svg?invert_in_darkmode&sanitize=true" align=middle width=116.42872394999998pt height=27.6567522pt/>
  
#### (1)/(2):

* <img src="/tex/3e902680172e3442533dfd97bd8c3224.svg?invert_in_darkmode&sanitize=true" align=middle width=141.03762255pt height=35.8209489pt/>   | devide-by  <img src="/tex/ff9a38cd49b9e03e40cd839b823f239e.svg?invert_in_darkmode&sanitize=true" align=middle width=79.82281065pt height=24.65753399999998pt/> 

* <img src="/tex/dafdb732e46ffe718273946f8364d5ea.svg?invert_in_darkmode&sanitize=true" align=middle width=137.856576pt height=43.068399000000014pt/>
 
<a name='LR'></a>
## Logistic regression:

The Perceptron rule <w,x> gave us distance which is between <img src="/tex/90562dba6bf49f79b1c70b8b77e31ded.svg?invert_in_darkmode&sanitize=true" align=middle width=62.10057149999999pt height=24.65753399999998pt/> when <img src="/tex/f7a0f24dc1f54ce82fecccbbf48fca93.svg?invert_in_darkmode&sanitize=true" align=middle width=16.43840384999999pt height=14.15524440000002pt/> is far in the positive side and 
<img src="/tex/1d5ba78bbbafd3226f371146bc348363.svg?invert_in_darkmode&sanitize=true" align=middle width=29.223836399999986pt height=19.1781018pt/> is in the far in the negetive side. if we think about it the bigger the distance the more likely that
the classification is right when 0 is 50% to each side.

Insted of working in distances space we want to talk about chances or probability to be a part of a class given some x , p(y|x).
to do so we need to change our space from <img src="/tex/90562dba6bf49f79b1c70b8b77e31ded.svg?invert_in_darkmode&sanitize=true" align=middle width=62.10057149999999pt height=24.65753399999998pt/> to [0,1]. A very usefull function to do so is the sigmoid function:

<p align="center">
	<img src="./Lesson_3/Capture1.PNG" align="middle">
</p>

The function in <img src="/tex/8860040216a2e61c344544a77b5cd2ce.svg?invert_in_darkmode&sanitize=true" align=middle width=16.43840384999999pt height=14.15524440000002pt/> is 1(heigh probability) and 0(low probability) in <img src="/tex/b9652934c10244a0a8922e2315545845.svg?invert_in_darkmode&sanitize=true" align=middle width=29.223836399999986pt height=19.1781018pt/>

#### Classes probability:

<p align="center"><img src="/tex/8e7a487149a8001fb6a36dc2bf283cf6.svg?invert_in_darkmode&sanitize=true" align=middle width=205.52482665pt height=34.3600389pt/></p>

<p align="center"><img src="/tex/fed0a164f2c02654792cc0c41d97b6f9.svg?invert_in_darkmode&sanitize=true" align=middle width=346.61284514999994pt height=34.3600389pt/></p>

So we can say in general that:

<p align="center"><img src="/tex/a0c3bb08b0edfc6c42d3b1e74388fee7.svg?invert_in_darkmode&sanitize=true" align=middle width=187.22124465pt height=34.3600389pt/></p>


#### Finding the optimal <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/>:

We can use maximum likelihood estimation method to find <img src="/tex/ae4fb5973f393577570881fc24fc2054.svg?invert_in_darkmode&sanitize=true" align=middle width=10.82192594999999pt height=14.15524440000002pt/> that will maximize the probability:

<p align="center"><img src="/tex/1df5b004798e038a30c9e86373998ab0.svg?invert_in_darkmode&sanitize=true" align=middle width=323.9386788pt height=44.89738935pt/></p>

because log is monotonic increasing function we can maximize log(P(y_1,y_2...y_m|x_1,x_2...x_,))

<p align="center"><img src="/tex/e7f7213a25a34231908aa9a21d05edf2.svg?invert_in_darkmode&sanitize=true" align=middle width=249.36182534999998pt height=44.89738935pt/></p>

This is same as:

<p align="center"><img src="/tex/b01e400e92d3bc19aef62ca564852934.svg?invert_in_darkmode&sanitize=true" align=middle width=242.8626057pt height=44.89738935pt/></p>

This equation is called log-loss loss function. while we already saw the mean square root loss: 

<p align="center"><img src="/tex/1421bd2ec6a07f1da22493b66d0b1bea.svg?invert_in_darkmode&sanitize=true" align=middle width=218.88848025pt height=44.89738935pt/></p>

This loss gives use the probability result between [0,1]


