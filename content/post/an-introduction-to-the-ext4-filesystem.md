---
author: "Joseph LeRoy"
date: 2016-05-08
linktitle: An Introduction to the Ext4 Filesystem
nomenu:
  main:
    parent: tutorials
next: /tutorials/github-pages-blog
prev: /tutorials/automated-deployments
title: An Introduction to the Ext4 Filesystem
weight: 10
image: img/nidhogg.jpg
authorAvatar: img/petting-cat.jpg
---

A filesystem is a way in which binary data is organized on disk using a set of data structures and other programming methods to handle file and hardware properties. An operating system is formatted to a certain filesystem and thus logically organized using a directory structure or the location where files are stored. These properties include but are not limited to metadata, which is information about a file such as its filename, the directory in which it is located, permissions, creation date, along with other information as needed. 

A data structure is a procedure for arranging data in a computer so that it can make use of computing hardware and software in the most efficient way possible. There are dozens of data structures, but only some of them are suitable for organizing and accessing files on disk. The goal of this writing is to explain the Ext4 filesystem, the most commonly used filesystem found in modern Linux operating systems, using a high level approach, along with items that are important to the computer forensic community.

The Ext4 filesystem was adopted from the Ext2 and 3 filesystems, commonly referred to as ExtX. There are many improvements the fourth iteration of the Ext filesystem has over its predecessors, including a removed subdirectory limit, increased individual file size allowed on disk, larger volume size, more intelligent use of logical disk space and more. Previously the Ext filesystem was limited to 32,000 subdirectories, but that nuisance was removed, along with improvements to the way files are created and deleted, thus greatly improving the filesystem’s performance over Ext3.

Upon release of the Ext4 filesystem in Linux kernel 2.6.28, gathered from the Kernel Newbies website, there have been many improvements to maximum allowed file sizes and other limits imposed by previous versions of the filesystem. The maximum allowed file size in the Ext4 filesystem is set to a maximum of 16 TiB, which is short for Tebibyte. A Tebibyte is nearly equivalent in size to a Terabyte. One Tebibyte is equal to 1.100 Terabytes for the sake of comparison. The maximum allowed volume size was also increased to 1 Exbibyte, or EiB for short. 

An Exbibyte is several times larger than a Tebibyte, which is a familiar order of magnitude in consumer based hard drive sizes. For sake of comparison, an Eib is 1024^6 and a TiB is 1024^4, or a difference of six decimal digits, which makes for an incredibly large number. In the previous Ext3 filesystem only supported 16 TiB is because there are only 32 bits available to address data blocks which have a 4 KB default size, whereas in Ext4 the limit was increased to 48 bits, thus making the limit 1 EiB. A block basically contains all the code to make a program or file unique and operate based upon its instructions.

When a file is saved, or created, the files are first indexed by a number, or inode, where each inode has multiple attributes attached to it, often called metadata. These include the file permissions, name, creation date, etcetera. A HTree index, which is defined later on, is used for file extents, such that when a file needs more than 4 extents the inodes are stored in a way that allows faster seeking based on the data structure used to randomly find a number versus searching in a linear based list. This is what extents do, and how the Ext4 filesystem works when creating files and allocating space for those files.

When you delete a file in the Ext4 filesystem the inode is unlinked from the file name. However, if a program is still using the inode associated with the program and its files, meaning that a link is still open in the operating system, it is continually updated until the program is closed. A file is not permanently deleted until all the links are removed, but even then the data is still physically on the disk but now very difficult to recover. Deleted data can potentially be recovered from the filesystem either by examining HTrees or inode structures and extent index nodes when extent trees are created. 

The two terms, HTrees and extents have not yet been defined, but basically a HTree is a modified tree based data structure for directory indexing. It can only be either one or two levels deep and hashes the filename allowing for a low probability of collisions or duplicate file data identifiers. An extent is something unique to the Ext4 filesystem as it allows for a more efficient way to map blocks of data together, especially larger files, as it groups them together contiguously by performing multiblock allocation upon file creation which reserves a group of inodes together. As expected, this allows for improved file access time and reliability over filesystems which do not employ the use of extents.

Some other forensic implications involved with the Ext4 filesystem include the inode resident extents of a file are replaced with zeros upon deletion its deletion. This essentially means that when a file is trying to be recovered it’s nearly impossible to determine when a file starts and ends since the physical block address no longer has an associated start location for the first block and it no longer has a length, along with the file size value and number of extents value associated with the file. 

This in turn makes recovering the deleted file incredibly difficult and thus making computer forensics methods such as data carving necessary. Data carving is basically a method for piecing together a file to make it whole or interpretable without relying on the file’s metadata. For other forms of data recovery in the Ext4 filesystem, an analysis of the inodes HTree for uninitialized extents which could contain fragments of data.