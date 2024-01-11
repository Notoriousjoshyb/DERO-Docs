Graviton
========

Graviton: ZFS for Key-Value Stores
----------------------------------

Standalone Alpha Release
------------------------

Graviton is an open source, simple, fast, versioned, authenticated and embeddable key-value store database written in Golang.

In short, Graviton can be described as â€œZFS for key-value stores,â€ in which every write is tracked, versioned and authenticated with cryptographic proofs. Additionally, it is possible to take snapshots of the database at any time and simple copy and rsync commands can be used for database backup, even during live updates without any possibilities of database corruption. The concept was derived from an immediate need for unique features that were currently unavailable in any other database.

Features
--------

The features included in Graviton provide the missing functionality that prevented Stargate RC1 from reaching deployment on our mainnet. The following features are critical for the success of our next release, but will also benefit many use cases in other domains.

-   Authenticated data store (all keys and values are backed by blake 256-bit checksums).
-   Append-only data store.
-   Support of 2â¶â' trees (theoretically) within a single data store. Trees can be named and thus used as buckets.
-   Support of values version tracking. All committed changes are versioned with ability to visit them at any point in time.
-   Snapshots (multi-tree commits in a single version causing multi bucket sync, each snapshot can be visited, appended and further modified, keys deleted, values modified, etc., new keys and values stored.)
-   Ability to iterate over all key-value pairs in a tree.
-   Ability to diff between two trees in linear time and report all changes of insertions, deletions and modifications.)
-   Minimal and simplified API.
-   Theoretically supports exabyte data stores, multi-terabyte tested internally.
-   Decoupled storage layer, allowing use of object stores such as Ceph, AWS, etc.
-   Ability to generate cryptographic proofs which can prove key existence or non-existence (cryptographic proofs are around 1 KB.)
-   Extremely fast proof generation time of around 1000 proofs per second, per core.
-   Support for disk based filesystem-based persistant stores.
-   Support for memory-based non-persistant stores.
-   100% code coverage

Benefits
--------

Graviton is open source and can be used in place of BoltDB, LMDB, LevelDB and more. While the included features may not be required for every use case, they provide novel improvements that can not be found anywhere else, such as the ability to traverse any and every commit, and diff between two trees in linear time. The end result is a robust and feature-rich database that will never corrupt data between backups and commits. The database code is also very readable and friendly to new Golang developers.

Below are some examples of how easy it is to use:

Save/edit a key

```
        tree, _ := ss.GetTree("root")

        // Insert a value
        tree.Put([]byte("answer"), []byte("44"))

        // Make the tree persistant by storing it in backend disk
        graviton.Commit(tree)

```

Get a value from a tree

```
    tree, _ := ss.GetTree("root")

    // Every key has a byte slice value
    v,_ := tree.Get([]byte("answer"))

    fmt.Printf("The answer is: %s\n", v)

```

Iterating over a tree

```
    // Assume "root" tree exists and has keys
    tree, _ := store.GetTree("root")

    // See cursor functions below
    c := tree.Cursor()

    for k, v, err := c.First(); err == nil; k, v, err = c.Next() {
        fmt.Printf("key=%s, value=%s\n", k, v)
    }

```

Functions available to the cursor (shown above)

```
    First()  Move to the first key.
    Last()   Move to the last key.
    Next()   Move to the next key.
    Prev()   Move to the previous key.

```

Learn More To view the code, seek out more examples, or learn about the internals of Graviton, please visit the following link: https://github.com/deroproject/graviton