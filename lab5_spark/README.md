The task of this lab is trying bigram on Spark with AWS EMR or NYU DUMBO.

# Tutorial resources 
* [Big Data Tutorial 1: MapReduce](https://wikis.nyu.edu/display/NYUHPC/Big+Data+Tutorial+1%3A+MapReduce)
* [Big Data Tutorial 3: Introduction to Spark](https://wikis.nyu.edu/display/NYUHPC/Big+Data+Tutorial+3%3A+Introduction+to+Spark)
* [Spark Programming Guide](http://spark.apache.org/docs/latest/rdd-programming-guide.html#spark-programming-guide)
* [Getting started with PySpark - Part 2](http://www.mccarroll.net/blog/pyspark2/)

# Command lines
## Submitting	a	Spark	Job
  Wordcount example
- Exit	pyspark (Ctrl+D)

- If	you	didn’t	before,	put	the	data	file	on	HDFS:
  `hadoop fs -copyFromLocal sherlock.txt`

- Run	the	wordcount Python	program	using	Spark:
  `spark-submit wordcount.py sherlock.txt`

- Output	can	be	found	in	wc.out
  - Use	the	saveAsTextFile() function	to	save	your	RDD
  - Then	use	“hadoop fs -getmerge…”	to	get	from	HDFS: 
    `hadoop fs -getmerge wc.out wc.out`

- Download the result from EMR:

  `scp -i ./googlrAmazonKeyPairs.pem hadoop@ec2-18-216-58-28.us-east-2.compute.amazonaws.com:/home/hadoop/b.out .`
  
  Refer to [How to download a file from EC2 instance to Local Computer](https://stackoverflow.com/questions/21861385/how-to-download-a-file-from-ec2-instance-to-local-computer)
