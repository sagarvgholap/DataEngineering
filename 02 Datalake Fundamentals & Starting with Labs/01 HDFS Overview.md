# HDFS recap
- HDFS follows Master Slave architecture
    - Master is **name node**
    - Slaves are **data nades**

    - e.g.
     you have file1.txt with 500mb size and if whole while resides in 1 data node then it will be as good as monolitic system and not distributed system
    - there is something called as block size = 128MB and by default it is 128 MD for the latest version of Hadoop
    - 2nd block : 128 MB (data node)
    - 3rd block : 128 MB (data node)
    - 1st block : 128 MB (data node)
    - 4th block : 116 MB (data node)

    - the actual data is stored in data node 
    - now, how to know which file is stored where, here name node comes into picture
    - name node holds table with metadata which may looks like
        - file 1 block 1 DN1
        - file 1 block 2 DN1
        - file 1 block 3 DN1
        - file 1 block 4 DN1
            - if client wants to read file1 from HDFS
            - the request will go to name node
            - name node will tell from where to read the blocks
                - consider like a 1000 page notebook 
                - you have an index page at the start of the book
                - 1000 data pages
                - your index page is more like your name node
                - and your actual pages are more like your data nodes
    - Hadoop
        - __HDFS__ : storage
        - __Mapreduce__ : processing
        - __YRAN__ : Resource manager

    - if file1.txt is 150 MB
        - there will be 2 blocks
        - node 1
        - node1
    - if file is of 1 GB
        - there will be 8 blocks of 128MB
        - data node can handle multiple blocks

    ## **Why the block size is 128MB?**
    - what happens if we reduce the block size? to 64 MB?
        - 1GB - default block size is 128 MB then 8
        - 1GB - default block size is 64 MB then 16
        - 1GB - default block size is 32 MB then 32
        
        - if we reduce the block size leads to more number os blocks

            - Advantage : more nodes can result into more parallelism and faster output
            - Disadvantage : if block size is 1 MB and if file is 10 GB the there will be 10240 blocks
                - then the name node will have the enrey for all blocks and has to keep the metadata of all of it in tis table..
                - your name node will get over burdened with these many entries

    - what happens if we increase the block size? to 64 MB?
        - 1GB - default block size is 128 MB then 8
        - 1GB - default block size is 256 MB then 4
        - 1GB - default block size is 512 MB then 2

        - hence less parallelism

    - so, 128 MD is good number but admin can chnage this if required

    ## --
    - if your data grows then you can add more data nodes
    - when your datanodes increases to a certain level then your metadata also also would have grown up.. 
    - in Hadoop we have  **NAMENODE FEDERATION**
        - where we can have more than one name node. metadata is split across these name nodes
        - this make sure that name node will not be a bottle neck fo system thus, newer version of Hadoop has conceot called as **NAMENODE FEDERATION**
        - **NAMENODE FEDERATION** is to provide scalibity
        - 

    ## Replication factor
    - this is for data node failure
    - it is 3 by default
    - can be changed
    - e.g. for POC it can be even 1

    ## what is Name node fails
    - there is **Secondary Name node** : it is for **fault tolerence**
    - **NameNode Federation** is for **scalibility**

    ## Rack
    - if you are setting up a cluster 
        - 10 datanodes in Banglore (1 rack)
        - 10 datanodes in San Francisco (1 rack)
        - 10 datanodes in Austrilia (1 rack)
    - if 1 rack fails due to calamities then data is stored shouldn't get lost
    - admin will take care of these things


