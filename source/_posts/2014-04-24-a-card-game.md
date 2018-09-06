---
layout: post
title: A quite simple card game implemented in C language 
description: A small card game.
category: 技术
tags: C
---

Here I am going to implement a game process using python and C. I have no
idea about its name in English. I will call it as PDT, the same as the project
name.
<!--more-->

## **0x00 Description**

In the game, each player will hold half of all cards in disorder, and they
will cast one card by turn to compose a list card after card. If the list have two cards
with the same number, the player will gain the cards between them. The game
ends once one of the players has no cards.

## **0x01 Analysis**

As we can see. the game contains two basic data structure: queue and
stack. The cards held by the players works like a queue. Cards that first in
will fisrt out. (As usual, we will insert the cards we gains to the buttom of 
the  cards.) So we onstruct bellow Queue type:

``` c
typedef struct Queue
{
  int *content;  // all cards
  int length; // the current size of the queue
  int front;  // the index of the first card 
  int rear;   // the index of the last card
} Queue;
```

We construct five basic method for the queue:

 > queue_init: create a Queue according to the max number of the cards(52)
 > and return a pointer to the Queue.
 > queue_push: insert an item to the rear of the content.
 > queue_npush: insert more than one items to the rear of the cntent.
 > queue_pop: cast a item from the head of the content. 
 > queue_len: the sizes of the content.

And the list works like a stack, as the cards that fist in will be out
last. So the structure like below:

``` c
typedef struct Stack
{
  int *content;
  int top;   // the index of the top cards
  int length; // the current size of the cards
} Stack;
```

Also we have six basic method for the stack, the two different ones like
below:

 > stack_npop: remove more than one items from the stack.
 > stack_isin: check if one item is in the stack or not.

Then What we need to do is wash the cards and play the game. The
array_shuffle method descripe how to wash the cards, in fact, randomly. So we
can use

``` c
srand(time(NULL));
```

as a seed to generate numbers differently. 
And the while loop in `main.c` file shows to play the games: if one
player cast a card and he can gain series of cards, he will play the next
round, otherwise the other player will cast.

The C source code can be seen in the project: [PDT](https://github.com/Qiwihui/PDT)
As for python, it is more easy to implete this game since we can get
existing queue and stack from the standard librar, or we can easily use list
as a replacement. It is what I did.

The project is here: PDT2(https://github.com/Qiwihui/PDT2)

## **0x02 Further**

We can finally see the whole process that each player cast and gain cards.
But will it end in the last or it maybe stuck at a loop? Any idea, please
comment on here.
