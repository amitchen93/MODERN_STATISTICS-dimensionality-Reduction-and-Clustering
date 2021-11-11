 Amit Chen

# Question 1

## Q1.a:



### PCA

![image-20210830142946789](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830142946789.png)

The classes are not clearly separable but the mean of each class seems to be  different , the occlusion still exists as expected by a linear reduction algorithm , also the distribution of each class exhibits linear patterns , in other words , gaussians in some shape of form , which is also expected as PCA is not the strongest dimension reduction algorithm. 

Note for image:

1. X Label - PC1 of PCA
2. Y Label - PC2 of PCA
3. Description: We can see 10 not so separated clusters of the original data





### UMAP

![image-20210830142524897](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830142524897.png)

Here we can see a much higher precision with regard to separation even at an extremely high DPI , the clusters are still clearly visible , the major difference between PCA and UMAP is that UMAP uses a non-linear algorithm , and as a result the clusters he managed to conjure also exhibit non-linear patterns , in other words his ability extract patterns from the datasets is superior to PCA in quite a margin.

Note for image:

1. X Label - first COMP of UMAP
2. Y Label - second COMP of UMAP
3. Description: 10 separated clusters of the original data



## Q1b:

#### Whole Dataset:

59 PC'S

![image-20210830151025116](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151025116.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (59)

### Class 0

22 PC'S

![image-20210830150344248](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150344248.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (22)

##### Class 1 :

7 PC'S

![image-20210830150421020](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150421020.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (7)

##### Class 2:

21 PC'S

![image-20210830150437615](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150437615.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (21)

##### Class 3:

17 PC'S

![image-20210830150508909](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150508909.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (17)

##### Class 4 :

15 PC'S

![image-20210830150534471](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150534471.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (15)

##### Class 5 :

106 PC'S

![image-20210830150547863](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150547863.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (106)

##### Class 6 :

35 PC'S

![image-20210830150607239](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150607239.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (35)

##### Class 7 :

19 PC'S

![image-20210830150621119](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150621119.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (19)

##### Class 8 :

55 PC'S

![image-20210830150635370](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150635370.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (55)

##### Class 9 :

20 PC'S

![image-20210830150652427](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830150652427.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (20)

We can therefor see the amount needed to maintain for each class is different from the whole combined , while we were not asked to explain the graphs we believe that different datasets have different patterns , and the increase in need of the X stems from the rise in complication , it is understandable that more variance is present in the whole datasets which combines different types of cloth rather then only in variation in the class itself. When the object main shape is constant , finding variation in color or some small changes is much easier to detect and encapsulate into a visualization with fewer dimensions, but trying to reduce the dimension by taking into account not only the inter-class variation but also the variation between those classes highly increases the algorithm need for more dimensions to express that variance which a rose between the inter-class objects and the classes themselves.

## Q1c:

The results as reported are :

##### Comparison between 2 components only

| Algorithm      | Accuracy            | Comp |
| -------------- | ------------------- | ---- |
| K-Means        | 0.47381666666666666 | 2    |
| K-Means++      | 0.47381666666666666 | 2    |
| K-Means++ PCA  | 0.375               | 2    |
| K-Means++ UMAP | 0.9645              | 2    |

Therefor we can see that the worse algorithm is actually PCA on top of K-Means++ , and best is as expected UMAP.

The results can be explained perhaps as PCA which decreases all his variation only into 2 components is  allows less data for KMeans to operate on , of course K-Means using on all the original data would preform better , even if the K-Means algorithm isn't extremely good , he still has access to 784 dimensions instead of only 2 , i.e. , he can access all the variation , instead of a lossy compressed  version given by the PCA.

The UMAP is out performing the rest by far , mostly because he has the ability to first compressed in a non-linear way the variation into much smaller dimensions and in a highly separate way , therefor as we saw in the graphs in Q1a , for K-Means++ to perform a clustering on such a well seperated data is a task we expect him to be succesfull on.

### Amount of components and accuracy :

#### PCA

As we increase the amount of components we can see that a sweet point exists for PCA  + KMeans++ , afterwards the performance declines ,  in other words the function is an approximation of a bell , as we can see below:

(The  x axis means 2^1 , 2^2 , 2^3 , 2^4... 2^8)

![image-20210830144055329](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830144055329.png)

Too much dimensions from the PCA  would mean we include dimensions with a miniscule amount of variation , those dimensions would reduce performance because the confusion they a rise in KMeans++ which now have to succefully ignore the noise that exists in the remaining dimensions , in other words while they create a more complete understanding of the data , the miniscule amount of variation included in those dimensions with comparison to the amount of the dimensions we add would only hinder KMeans++ performance.

#### UMAP

We expect UMAP to exhibit the same trend , since the idea of extra dimensions only complicated things with out much added value should remain true here as well , with out any dependence on the dimensional reduction algorithm we choose. 

![image-20210830145348290](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830145348290.png)

And as expected , we see that at 8 components we managed to probably encapsulate most of the variation of the data , compared to the PCA which managed to do it at a much higher dimensions which stems from his linear capabilities , and we see a stagnation but not a direct descent after the optimal point , nevertheless the same patterns exhibits which imply that more dimensions are hindering KMeans++ capabilities to cluster well.

In conclusion , UMAP vastly outperformed the rest , mostly because his ability to express non-linear patterns in the data , therefor a linear algorithm in such cases would almost surly prove itself inferior.



Higher components then 128 in the case of UMAP and 256 in the case of PCA wasn't computed because :

1. PCA doesn't take more time to compute 256 of 512 components , but KMeans++ time complexity depends on the dimensions of the data , therefor performing KMeans++ on 512 dimensions took a large amount of time.
2. In contrast to PCA , more dimensions for UMAP require more time , therefor even computing UMAP on 256 dimensions and then applying KMeans++ on top of it required a large amount of time.





# Question 2 :

## Q2.a:



#### $\sigma=1$

59 PC'S

![image-20210830151439793](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151439793.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (59)

#### $\sigma=2$​

60 PC'S

![image-20210830151556023](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151556023.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (60)

#### $\sigma=4$​

61 PC'S

![image-20210830151606907](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151606907.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (61)

#### $\sigma=8$​

67 PC'S

![image-20210830151619407](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151619407.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (67)

#### $\sigma=16$

97 PC'S

![image-20210830151632119](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151632119.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (97)

#### $\sigma=32$​

284 PC'S

![image-20210830151644324](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151644324.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (284)

#### $\sigma=64$​

558 PC'S

![image-20210830151728956](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151728956.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (558)

#### $\sigma=128$​

665 PC'S

![image-20210830151742041](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151742041.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (665)

#### $\sigma=256$​

681 PC'S

![image-20210830151758900](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151758900.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (681)

#### $\sigma=512$​

687 PC'S

![image-20210830151811080](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830151811080.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (687)

## Q2.b:

In all cases , even a little bit of noise completely destroies our accuracy and keeps her in the same range , there are slight variations at each row , in the first row using as little components as possible is better , or using 32 components.

The rows signify noise , column the amount of components

![image-20210830171338915](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830171338915.png)

$\sigma=1$​​  - 32 CP's

$\sigma=2$​​​​​  -16 CP'S

$\sigma=4$​​​   32 CP'S

$\sigma=8$​​  - 16 CP'S

 $\sigma=16$​  - 32 CP'S

$\sigma=32$​​  - 8 CP'S



#### UMAP

![image-20210830175216160](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830175216160.png)

$\sigma=1$​​  8 CP'S

$\sigma=2$​​​​  - 32 CP'S

$\sigma=4$​​​    8 CP'S

$\sigma=8$​  - 32 components

 $\sigma=16$​  - 4 components , which is a surprise and probably an representing sample

$\sigma=32$​  - 32 components , while the accuracy in all of them is fairly low , 32 components seems to behave best.



#### Which one is better

UMAP on the other hands keeps his performance level very high despite the noise, in fact he never dropped beneath 98% accuracy and in fact seems quite unaffected by the noise , which I find weird , after failing to find a bug in my code I realized that maybe UMAP is just that good , PCA on the other hand sees a decline in performance as the noise increases , the highest being around 57%~ and lowest around 35%~ , therefor a direct decrease as the noise increases , thus UMAP is far superior in handling noisy data.







## Q2.c:

Repeat exatcly the same code but change the noise this time to spike , then compare the robustnuss and which one should we take care of.



##### Q2.c.a :

Repeating and observing the PC components with dependent on the noise level , using spike noise :

##### 2^-9 : 63 CP'S

![image-20210831210609725](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210609725.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (63)

##### 2^-8 : 67 CP'S



![image-20210831210707845](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210707845.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (67)

##### 2^-7 :76 CP'S6

![image-20210831210718958](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210718958.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (76)

##### 2^-6 99 CP'S6

![image-20210831210814972](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210814972.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (99)

##### 2^-5 :162 CP'S:

![image-20210831210835975](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210835975.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (162)

##### 2^-4 : 315 CP'S

![image-20210831210909421](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210909421.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (315)

##### 2^-3 :477 CP'S

![image-20210831210930240](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210930240.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (477)

##### 2^-2 :584 CP

![image-20210831210956534](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831210956534.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (584)

##### 2^-1 :651 CP'S

![image-20210831211014397](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831211014397.png)

Note for image:

1. X Label - # Principal Components
2. Y Label - Cumulative explained variance from model
3. Description: # of PC's are needed to maintain 90% of the variance of each class (651)

#####

PCA Heat map

![image-20210831195903316](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831195903316.png)

$\sigma=2^{-9}$​​​  8 CP'S

$\sigma=2^{-8}$​​​​​  - 8 CP'S

$\sigma=2^{-7}$​​​​    32 CP'S

$\sigma=2^{-6}$​​​​  - 8 components

 $\sigma=2^{-5}$​​  - 16 components , which is a surprise and probably an representing sample

$\sigma=2^{-4}$​​​​  - 16 components , while the accuracy in all of them is fairly low , 32 components seems to behave best.

$\sigma=2^{-3}$ - 16 comps

$\sigma=2^{-2}$​  8 comps

$\sigma=2^{-1}$  8 comps

```
[[0.98105    0.9838     0.98386667 0.98391667 0.98435    0.98421667]
 [0.9181     0.98435    0.98453333 0.9841     0.98405    0.9846    ]
 [0.96808333 0.98331667 0.9836     0.98315    0.9839     0.98373333]
 [0.9685     0.98456667 0.98456667 0.98436667 0.98445    0.98456667]
 [0.98288333 0.98093333 0.98338333 0.98328333 0.98345    0.98371667]
 [0.97176667 0.98423333 0.98458333 0.98475    0.98461667 0.98461667]
 [0.98293333 0.98373333 0.9833     0.98325    0.98316667 0.98283333]
 [0.97876667 0.97841667 0.97898333 0.9791     0.9791     0.97875   ]
 [0.82326667 0.86141667 0.86176667 0.86153333 0.86395    0.862     ]]
```

![image-20210831205513343](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210831205513343.png)

$\sigma=2^{-9}$​​​  32 CP'S

$\sigma=2^{-8}$​​​​​  - 32 CP'S

$\sigma=2^{-7}$​​​​    16CP'S

$\sigma=2^{-6}$​​​​  - 8 components

 $\sigma=2^{-5}$​​​  - 8 components 

$\sigma=2^{-4}$​​​​  - 16 components

$\sigma=2^{-3}$​​ - 2  comps

$\sigma=2^{-2}$​  16 comps

$\sigma=2^{-1}$  16 comps



##### Would we use another method?

We never saw any algorithm that's even comparable with UMAP in this exercise , UMAP outshine any other algorithm with any regard , therefor even a dip to 85%~ accuracy is still vastly better then other alternative we have seen in this project by a wide margin.

# Question 3 :

## Q3.a

We can see that the seperation between PCA is much worse now ,

![image-20210830195021596](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830195021596.png)

Note for image:

1. X Label - PC1 of PCA
2. Y Label - PC2 of PCA
3. Description: We can see 10 not so separated clusters of the original data

 because they were a kin to guassian , centering guassain around the same mean would only spread them in different ways but since their patterns are linear our ability to distinct between them is always none.



On the other hand , UMAP managed to separate them to some degree ,

![image-20210830194849918](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830194849918.png)

Note for image:

1. X Label - first COMP of UMAP
2. Y Label - second COMP of UMAP
3. Description: 10 separated clusters of the original data

while still much worse then before , mainly because he finds non-linear patterns , e.g. if one class creates a ring around the mean , and another one creates a triangle , a non-linear algorithm would find those difference and the mean wouldn't matter , but a non-linear one would just try to see them as gaussian since a ring and a triangle is a non-linear form , therefor he'll center them in a gaussian way.

### Q3.b:

he accuracies are as follows :

##### 

```
PCA : 0.347
UMAP : 0.59735
Kmeans :0.47883333333333333
KMeans ++ 0.5501333333333334
```



The major difference is the "hit in accuracy" each algorithm suffered. Umap went from 0.99%~ to 0.59735 , while PCA  accuracy went from 48%~  to 0.347%~ on 2 CP'S , thus UMAP is still miles better. While Kmeans and Kmeans++ doesn't seem to be much influenced by the noise.

## Q3.c:

####  Between cluster angles



![image-20210830152904659](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830152904659.png)

#### Within clusters angles :

![image-20210830152953119](C:\Users\David Pitts\AppData\Roaming\Typora\typora-user-images\image-20210830152953119.png)



A big difference can be seen , the distribution of the angle between clusters is much smaller , i.e. the degrees between the vector from the same cluster is smaller then the latter , in other words , as we expect , images from the same class tends to be closer to each other with regard to the range their components have , which a smaller angle between them because of their similarity. 



 

Q3.4:

```

Algorithm: SSC-OMP. acc: 0.43134285714285714
```

Surprisingly so UMAP is still vastly better and outperform an algorithm that was specialized for cases such as that , it does seem strange and might be as a result of a bug , but maybe UMAP is just substansly better. 

Therefor UMAP is the best , followed by SCC and then by PCA