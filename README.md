We built a time and space efficient Database Engine, using the fundamental database concepts such as
Storage Architecture, File Organization, Organization of Records in Files, Data-Dictionary Storage, Database Buffer, Indexing and Query Procesing.

The system design can be broadly divided into 4 components built on top of one another, namely:

 1. Record Based File Manager (rbf):
This layer consists of a paged file system (PF) which provides facilities for higher-level client components to perform file I/O in terms of pages.
In the PF component, methods are provided to create, destroy, open, and close paged files, to read and write a specific page
of a given file, and to add pages to a given file. The record manager is going to be built on top of the basic paged file system.
The RecordBasedFileManager class handles record-based operations such as inserting, updating, deleting, and reading records.

2. Relation Manager (rm):
The RelationManager class is responsible for managing the database tables. It handles the creation and deletion of tables.
It also handles the basic operations performed on top of a table (e.g., insert and delete tuples).

3. Query Engine (qe):
The QE component provides classes and methods for answering SQL queries. It is built upon 
rm and can also use ix if needed.

4. Index Manager (ix):
Facility of indexing can be provided in the rm and qe classes to make operations faster. This is an
optional component of our DBMS and can be extended if needed.

RUN Instructions:

1. Modify the "CODEROOT" variable in makefile.inc to point to the root of your code base if you can't compile the code.
2. In terminal, change directory to the class that you want to use. For instance say "rbf" and do:

    - make clean

    - make

    - ./rbftest1

    This will clean the existing executables, create new ones and run a testcase (here rbftest1).
    Similarly for other components i.e. rm, ix and qe.
