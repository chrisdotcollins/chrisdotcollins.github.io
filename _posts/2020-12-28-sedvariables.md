---
title: sed Variables
#subtitle: 
date: 2020-12-28
categories: ["bash", "sed"]
layout: single
classes: wide
---
 
Working with variables in sed
 
```
cat hosts-escluster-nodes.cfg.2 | sed 's/\(node[0-9]*\)/\1.escluster/g'
```

Variables are within escaped brackets ```\(VARIABLE\)``` and inserted as \1.
Can have multiple variables, so can use \1 \2 etc
 
Example, above command changes:
 
```
139.222.146.1 node001
139.222.146.2 node002
139.222.146.3 node003
```

To


```
139.222.146.1 node001.escluster
139.222.146.2 node002.escluster
139.222.146.3 node003.escluster
```
