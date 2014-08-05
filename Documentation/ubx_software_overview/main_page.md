---
layout: page
title: Ubx Software Overview
---

## Software Design

The current implementation is : CoMinG SoOn! :-)

## What is a Block?

* Computation Block (cblock)
* interaction Block (iblock)

## What is a Port?

## What is a Type?

## What is a Module?

In Ubx context, a ___module___ is a compiled container for types and blocks implementation.
A module contains
Further details can be found in [anatomy of a module](/Documentation/module_explained)

## What is a Node?

## Where is the Trigger?

With respect to the metamodel, there is no explicit implementation of trigger.
In fact, a trigger mechanism is already implemented through calling the step function of the
target cblock.

### What the difference between block types and instances?

First: to create a block instance, it is cloned from an existing block
and the `block->prototype` char ponter set to a newly allocated string
holding the protoblocks name.

There's very little difference between prototypes and instances:

- a block type's `prototype` (char) ptr is `NULL`, while an instance's
  points to a (copy) of the prototype's name.
  
- Only block instances can be deregistered and freed (`ubx_block_rm`),
  prototypes must be deregistered (and freed if necessary) by the
  module's cleanup function.

### Module visibility

The default Makefile defines `-fvisibility=hidden`, so there's no need
to prepend functions and global variables with `static`