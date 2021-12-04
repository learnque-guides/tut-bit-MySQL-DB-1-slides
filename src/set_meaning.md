# SET meaning

By a “set” we mean any collection M into a whole of definite, distinct objects m (which are called the “elements” of M) of our perception or of our thought.

A set should be considered a single entity.

The word distinct means that every element of a set must be unique. Jumping ahead to tables in a database, you can enforce the uniqueness of rows in a table by defining key constraints. Without a key, you won’t be able to uniquely identify rows, and therefore the table won’t qualify as a set. Rather, the table would be a multiset or a bag.

The formal notation for listing set elements uses curly brackets: {a, b, c}. Because order has no relevance, you can express the same set as {b, a, c} or {b, c, a}. Jumping ahead to the set of attributes (called columns in SQL) that make up the heading of a relation (called a table in SQL), an element is supposed to be identified by name—not by ordinal position.

The set of tuples (called rows by SQL) that make up the body of the relation; an element is identified by its key values—not by position. Many programmers have a hard time adapting to the idea that, with respect to querying tables, there is no order among the rows. In other words, a query against a table can return table rows in any order unless you explicitly request that the data be sorted in a specific way, perhaps for presentation purposes. 