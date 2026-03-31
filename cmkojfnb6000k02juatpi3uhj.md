---
title: "Inside Git: How It Works and the Role of the .git"
seoTitle: "Inside Git: How It Works and the Role of the .git"
seoDescription: "This blog explains the .git folder, the inside view of the folder with its working."
datePublished: 2026-01-21T21:31:27.811Z
cuid: cmkojfnb6000k02juatpi3uhj
slug: inside-git-how-it-works-and-the-role-of-the-git
tags: git, git-folder, git-folder-architecture

---

Most of the developers works on git everyday:

```plaintext
git add .
git commit -m "message"
git push
```

But very few only knows the internal functionality of git. When something got break (merge conflicts, resetting HEAD, rebasing or corrupt git history), git feels like mysterious.

This article includes:

* Core model of Git
    
* Understand what the .git folder really is
    
* Learn how Git stores data
    
* Understand blob, tree, and commit objects
    
* See what actually happens during `git add` and `git commit`
    

This article is not for the beginners. **If you have just started learning git, you should check** [**Git for Beginners**](https://git-from-scratch.hashnode.dev/git-for-beginners) **article and learn the basics of git first**.

## The core model of git

We should first understand that git is not a file tracker. It is a snapshot database which stores the snapshot of your project and compare the changes with that snapshot.

What git doesn’t:

* Track files
    
* Track differences
    
* Track changes line-by-line
    

What git does:

* Stores snapshots of the project as a immutable (which cannot be change) objects.
    
* Connect them using hashes and pointers
    

Every commit creates a snapshot of a project but it is pretty smart to reuse the unchanged files and compare the previous snapshot with the newly generated.

## What is .git folder?

.git folder is the entire Git repository database. When you initialized the git in any project using `git init`, git creates a .git folder in the root of the project.

```plaintext
my-project
|--file1
|--file2
|--src/
|--.git/    -> git respository database
```

### .git folder structure

```plaintext
.git/
|-- objects/    -> Database: blobs, trees, commits
|-- refs/       -> Branch and tag pointers
|-- HEAD        -> Current position where you are
|-- index       -> Staging area which will be committed
|-- config      -> Repository config
```

### Understanding Git Objects

Git stores everything as a 3 main object types

* **Blob** - Blob is also known as Binary Large Objects. It only stores the content of a file. It does not stores the file name and its creation data.  
    When you use commands like git add, Git calculates the hash of the file's content and stores that content as a blob in the internal object database (located in the .git/objects directory).
    
    ```plaintext
    message.txt
    |
    |-- Good Morning -> Good Evening (message changed)
    
    Git does:
    
    hash("Good Evening") -> e.g. 557db03...
    ```
    
    Blob represents WHAT is in the file, not WHERE it is. Also If two files have the same content, Git stores only one blob.
    
* **Trees** - A tree represents a directory (folder). A tree doesn’t contains of file content instead it stores the file names, folder names and the blob or folders they are pointing to.  
    If your folder structure look like this:
    
    ```plaintext
    project
    |-- file1.txt
    |-- file2.txt
    |-- folder1
    |   |-- file3.txt
    |--.git
    ```
    
    Git creates a structure like below:
    
    ```plaintext
    Tree (root)
    |-- file1.txt -> blob
    |-- file2.txt -> blob
    |-- folder1   -> Tree
                     |-- file3.txt
    ```
    
* **Commits -** Commit represent the snapshot of entire project. Commit stores the pointer to main tree, pointer to parent commits, and it’s metadata (Author, Committer, Date, Commit Message).
    
    ```plaintext
    Commit
      |
      |
    Tree (root)
    |-- file1.txt -> blob
    |-- file2.txt -> blob
    |-- folder1   -> Tree
                     |-- file3.txt
    ```
    
    * So, internally if you changed something inside the `folder1/file3.txt`:
        
        * New blob created for file3.txt
            
        * New tree for folder1
            
        * New root tree
            
        * New commit created
            
        
        But reuses everything else and remains unchanged.
        

## What Really Happens During `git add` and `git commit`?

Let’s understand this with an example:

You created a file file1.text

```plaintext
Hello World
```

The file is created and untracked.

Then you run a command `git add file1.txt` . It adds snapshots of file content to the staging area.

Internally what happen is:

```plaintext
 Working Directory
        | 
    (git add)
        |
 Read file content
        |
        |
 Create blob object
        |
        |
Store in .git/objects
        |
        |
Update .git/index (staging area)
```

The index file here acts as a staging area for the individual blobs.

Then you run the command `git commit -m “message“`

```plaintext
git commit -m “message“
          | 
          |
 Reads the staging area
          |
          |
  Creates tree objects
          |
          |
 Creates a commit object
          |
          |
Updates the branch pointer
```

## Conclusion

Git is:

* A content-addressed object database
    
* That stores snapshots
    
* Uses hashes for identity & integrity
    
* And uses pointers for branches and HEAD