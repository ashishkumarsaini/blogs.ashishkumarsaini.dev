---
title: "Why Version Control Exists: The Pendrive Problem"
seoTitle: "Why Version Control Exists: The Pendrive Problem"
seoDescription: "This article explains the problem version control is solving with a pen drive problem analogy."
datePublished: 2026-01-21T21:37:44.164Z
cuid: cmkojnppg000002la246k06bf
slug: why-version-control-exists-the-pendrive-problem
tags: version-control, version-control-systems, pendrive-analogy, pendriveproblem

---

Before tools like Git, GitHub, or any modern version control system existed, software development was… chaotic.

Not a little mess but more like where the code goes? who changes the code? or which is the final version of the code?

In order to understand the problem, let’s go back how the developers works before the version control was introduced.

## The Pen drive Analogy in Software Development

Imagine a you (Developer 1) working on a project. You create the `feature1` and save it on your computer. You know what code you have written and what changes you have done. You can modify the code as per your requirements.

Before Version control, the developer used to exchange the code by the help of pen drive in which they updates the code and share with the next developer.

There is:

* One pen drive (or Google Drive / email thread)
    
* One project folder inside it
    
* Everyone copies the project, works on it, and sends it back
    

Now, if you start working with one more developer (Developer 2), you will code, copies the code in pen drive and pass the pen drive to second developer.

When Developer 2 code the new feature “`feature2`” and pass it back to the Developer 1. Seems like fine but here where the problems start.

* **Tracking code**: Developer 1 doesn’t know what has changed, which file has changed and for what reason the existing code is changed.
    
* **Working at same time:** Individual developer which has the pen drive can only work on the project at a time.
    
* Bug Fix issue: If the previous developer fixes some code the current developer does not know what has been fixed.
    

Now let’s assume the same situation with more than 2 developers.

### The “final”, “final\_v2”, “latest\_final” Era 😄

Almost every developer has seen folders like these

```plaintext
project/
  final/
  final_v2/
  final_v3/
  final_latest/
  final_latest_really/
  final_latest_this_one/
```

Or files like:

```plaintext
app.js
app_new.js
app_new_fixed.js
app_new_fixed_final.js
app_new_fixed_final2.js
```

Why did this happen?

Because there was no reliable way to track history.

So developers did the only thing they could:

* Make copies
    
* Rename folders
    
* Pray they didn’t delete something important
    

## The Pendrive Problem at Scale

Now imagine this same workflow:

* Not for 3 people
    
* But for **50 developers**
    
* Working for **2 years**
    
* On **millions of lines of code**
    

It becomes **completely impossible** to manage.

This is the moment the industry realized that, we don’t just need storage. We need **history**, **tracking**, **merging**, and **safety**.

## **Why Version Control become mandatory?**

Problems faced before Version Control

* Override Each other code: Two developers start from the same code.
    
    * Dev A adds a payment feature.
        
    * Dev B fixes some bugs.
        
    
    Both send back their versions.
    
    Now what?
    
    * If you copy Dev A’s code → you lose Dev B’s bug fixes
        
    * If you copy Dev B’s code → you lose Dev A’s feature
        
    
    There is **no automatic way to merge changes**.
    
    Someone has to compare files and code manually ensuring nothing has broken.
    
* Losing changes forever: Lets assume if the previous version of the code is working fine.
    
    * There is no history of the changes which can be reverted back.
        
    * Once lost → lost forever
        
* Cannot track the developer who has worked / fixed the code.
    
* Fear of changing the code.
    

Version Control Systems (VCS) were created to solve exactly these problems:

They allow you to:

* Keep full history of every change
    
* Know who changed what and why
    
* Go back to any previous version
    
* Work in parallel without overwriting others
    
* Merge changes intelligently
    
* Experiment safely without fear
    

### The timeline concept in Version Control

Instead of this:

```plaintext
project_final/
```

You now have this:

```plaintext
Version 1 → Version 2 → Version 3 → Version 4 → Version 5 → ...
```

Each version is called a **commit** (in Git).

Each commit is:

* A snapshot of your project
    
* Plus metadata (author, time, message)
    

So your project becomes a **timeline of snapshots**.

## Conclusion

From chaos to control, From the era of pen drive to folders to version control, the industry has learned that without tracking you can not build a scalable projects. And now Git has become a mandatory for individuals or organizations for build softwares.