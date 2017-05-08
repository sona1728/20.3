Ans:
# Writables and its Importance in Hadoop:

- Writable is an interface in Hadoop. Writable in Hadoop acts as a wrapper class to almost all the primitive data type of Java. That is how int of java has become IntWritable in Hadoop and String of Java has become Text in Hadoop.

- Writables are used for creating serialized data types in Hadoop. So, let us start by understanding what data type, interface and serilization is.

- Hadoop frame work definitely needs Writable type of interface in order to perform the following tasks:

> Implement serialization
> Transfer data between clusters and networks
> Store the deserialized data in the local disk of the system

- Implementation of writable is similar to implementation of interface in Java. It can be done by simply writing the keyword ‘implements’ and overriding the default writable method.

- Writable is a strong interface in Hadoop which while serializing the data, reduces the data size enormously, so that data can be exchanged easily within the networks. It has separate read and write fields to read data from network and write data into local disk respectively. Every data inside Hadoop should accept writable and comparable interface properties.

# Writable Comparable in Hadoop :
WritableComparable can be defined as a sub interface of Writable, which has the feature of Comparable too.

- Writable variables in Hadoop have the default properties of Comparable. For example:

- When we write a key as IntWritable in the Mapper class and send it to the reducer class, there is an intermediate phase between the Mapper and Reducer class i.e., shuffle and sort, where each key has to be compared with many other keys. If the keys are not comparable, then shuffle and sort phase won’t be executed or may be executed with high amount of overhead.

- If a key is taken asIntWritable by default, then it has comparable feature because of RawComparator acting on that variable. It will compare the key taken with the other keys in the network. This cannot take place in the absence of Writable.
