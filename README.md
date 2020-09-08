# Introduction to Git and GitHub

Git is a version control system that can be used to keep track of the entire
history of your software projects.  It is an industry standard and a using it
is a very useful skill to have.  

GitHub is a website that "hosts" your Git project.  That means you can upload
your project here which serves as a backup and allows you to share it with
others.

All homework assignments for this course will be submitted through GitHub,
so it is very important that you learn the basics.

## Envrionment Setup

First make an account at `https://github.com/`.  I advise you to choose a
professional name as GitHub profiles are often shared on resumes.

Git should already be installed on your terminal of choice by default.  If it
is not, see me and I will help you get it installed.

In order to connect your terminal to GitHub, you must run the following in your
terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "yourEmail@cooper.edu"

cd ~
mkdir -p .ssh
ssh-keygen -C "yourEmail@cooper.edu" -t rsa -f .ssh/id_rsa -N ""

cat .ssh/id_rsa.pub
```

Now in GitHub, click your icon in the top right, then `settings` then
`SSH and GPG keys` then `New SSH key`, paste the result from the previous
command in the box, and click `Add SSH Key`.

You can find more information [here](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

## Creating a new repository

A respository is a collection of code in Git or GitHub.

Create a new respository by going to `https://github.com/` and clicking `New`
in the upper left of the screen.  Type `hello-world` for the name and make sure
to check the box that says `Initialize this repository with a README`, then
click `Create Repository`.  Now, click `SSH` and copy the URL to the right of
it.  In your terminal, running the command `git clone {URL}` should produce a
new directory with your repository inside. 

Note that if you run `git remote -v`, you should see `origin` followed by a
url.  This should be the URL of the repository you cloned.  This URL will
be used in all future commands when uploading or downloading from the repo.

## Creating a new Branch

Now `cd` into the newly created repository.  You can create a new branch by
running `git branch newBranch`.  In order to start modifying this branch, you
must also run `git checkout newBranch`.  A shorthand that combines both of
these commands is `git checkout -b newBranch`.

## Modifying Content

Modifying a file takes a couple steps.  These steps may feel unintuitive and
confusing, but they will become second nature as you gain experience.

First, to view your status at any time, type `git status`

You can append to `README.md` by running the command `echo "first modification"
>> README.md`.  Run `git status` after to see what has changed.  Now run `git
add README.md` and run `git status` again.  Finally, run `git commit -m 'first
commit'` and `git status` one more time.  Finally, upload your change to GitHub
with `git push origin newBranch`.  Note that the `origin` refers to the URL
we saw earlier when running `git remote -v`.

This is a very common workflow which makes a change, adds the change to the
"staging area", commits the change to your local repository, and pushes the
change to GitHub (the remote repository).

If you remember:
* `add`
* `commit`
* `push`

You can do most of what you need to do, as a single user.

## Pull Requests

If you go back to your repository on GitHub, you (hopefully) not see any
changes in `README.md`.  However, you may see a notification with a button
that says `Compare & pull request`, and if you click the button that says
`Branch: master` you should see the new branch you created.

Navigate into the `Pull requests` tab and click `New pull request`.  The first
branch is the one you are pulling into, the second is the one that has
modifications.  Select the second branch and choose the new branch you created.
You will see any differences highlighted here.  Click `Create pull request`.
Do NOT click `Merge pull request` yet.

## Downloading Modified Content

Now what happens if another person uploads changes, and you need to apply those
changes to your own code?  One possible answer is to simply re-download or
re-clone the repo after they pushed the changes, though this is obviously a
little more work than necessary, and you would have to manually copy over your
own changes, if you had any.  The correct solution is to perform what is called
a `pull`.  This will download the code from the repo, and attempt to
automatically merge them with the code you have locally.  If you want to
perform this action with the master branch, you use the command `git pull
origin master`.  Technically this is performing two steps: *fetching* the
files, and *merging* them.  These can be performed as two separate commands,
but you will rarely have a need to do so.

## Conflicts

What do you think would happen if two different people performed the same
steps, but with different changes?  This is called a "conflict" It would be
quite rude of Git to assume that either person's changes should overwrite the
other, so Git will ask us manage the change ourseves.  These conflicts will
occur when pulling if the same contents of a given file were edited by 2
or more people.  You must simply modify the effected files to include the
correct merge of both changes, and then commit.

## Conclusion

There is a lot more to Git than this, and it might seem that you are just
memorizing arcane incantations, which is true.  However, this being an
introductory class, we are not yet in a place where we can discuss how Git
works at a deeper level.  If you want to try and learn more in depth, I highly
recommend this [MIT lecture](https://www.youtube.com/watch?v=2sjqTHE0zok)

## GitHub Classrooms

Assignments will be managed through GitHub Classrooms.

You may push all your changes directly to the `master` branch if you wish.
I will leave you feedback on the automatically created pull request to the
`feedback` branch.  Automated tests will also be run which will tell you if 
your output is correct.  Please do not merge this pull request.

## Demonstration

Lets go over a demonstration of how to complete these operations in the
`repl.it` page for a repository.  You can use this to complete your assignments
but I highly recommend you get set up on your local terminal, as it is
typically more reliable.

> Demonstrate Repl

---

# Introduction to C

Git is a version control system that can be used to keep track of the entire
history of your software projects.  It is an industry standard and a using it
is a very useful skill to have.  

GitHub is a website that "hosts" your Git project.  That means you can upload
your project here which serves as a backup and allows you to share it with
others.

All homework assignments for this course will be submitted through GitHub,
so it is very important that you learn the basics.

## Envrionment Setup

First make an account at `https://github.com/`.  I advise you to choose a
professional name as GitHub profiles are often shared on resumes.

Git should already be installed on your terminal of choice by default.  If it
is not, see me and I will help you get it installed.

In order to connect your terminal to GitHub, you must run the following in your
terminal:

```bash
git config --global user.name "Your Name"
git config --global user.email "yourEmail@cooper.edu"

cd ~
mkdir -p .ssh
ssh-keygen -C "yourEmail@cooper.edu" -t rsa -f .ssh/id_rsa -N ""

cat .ssh/id_rsa.pub
```

Now in GitHub, click your icon in the top right, then `settings` then
`SSH and GPG keys` then `New SSH key`, paste the result from the previous
command in the box, and click `Add SSH Key`.

You can find more information [here](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

## Creating a new repository

A respository is a collection of code in Git or GitHub.

Create a new respository by going to `https://github.com/` and clicking `New`
in the upper left of the screen.  Type `hello-world` for the name and make sure
to check the box that says `Initialize this repository with a README`, then
click `Create Repository`.  Now, click `SSH` and copy the URL to the right of
it.  In your terminal, running the command `git clone {URL}` should produce a
new directory with your repository inside.

## Creating a new Branch

Now `cd` into the newly created repository.  You can create a new branch by
running `git branch newBranch`.  In order to start modifying this branch, you
must also run `git checkout newBranch`.  A shorthand that combines both of
these commands is `git checkout -b newBranch`.

## Modifying content

Modifying a file takes a couple steps.  These steps may feel unintuitive and
confusing, but they will become second nature as you gain experience.

First, to view your status at any time, type `git status`

You can append to `README.md` by running the command 
`echo "first modification" >> README.md`.  Run `git status` after to see what
has changed.  Now run `git add README.md` and run `git status` again.  Finally,
run `git commit -m 'first commit'` and `git status` one more time.  Finally,
upload your change to GitHub with `git push origin newBranch`.  This is
a very common workflow which makes a change, adds the change to the "staging
area", commits the change to your local repository, and pushes the change
to GitHub (the remote repository).

If you remember:
* `add`
* `commit`
* `push`

You can do most of what you need to do.

## Pull Requests

If you go back to your repository on GitHub, you (hopefully) not see any
changes in `README.md`.  However, you may see a notification with a button
that says `Compare & pull request`, and if you click the button that says
`Branch: master` you should see the new branch you created.

Navigate into the `Pull requests` tab and click `New pull request`.  The first
branch is the one you are pulling into, the second is the one that has
modifications.  Select the second branch and choose the new branch you created.
You will see any differences highlighted here.  Click `Create pull request`.
Do NOT click `Merge pull request` yet.

## GitHub Classrooms

You join the classroom with [this link](https://classroom.github.com/classrooms/62485055-the-cooper-union-cs102)

Finish the [first assignment](https://classroom.github.com/a/xNJwXTU2) as fast
as possible so I know you are able to connect.

You may push all your changes directly to the `master` branch if you wish.
I will leave you feedback on the automatically created pull request to the
`feedback` branch.  Automated tests will also be run which will tell you if 
your output is correct.  Please do not merge this pull request.

The first of many languages we will learn here is called **C**.  It is called
*C* because it is the successor of a language called **B**, which is thought to
have been named after another language, **Basic Combined Programming Language**
(BCPL).

Here we show a very simple C program which prints the text "Hello, world"
to the screen.  

```
// hello.c
#include <stdio.h>

int main() {
    printf("Hello, world\n");
    return 0;
}
```

The "Hello, world" program is a common program used to introduce many
different programming languages, being the simplest program that 
produces output.

You can run this program in your shell by running `gcc hello.c -o hello`
followed by `./hello`.  These commands are  called **Compiling** the program
and **Executing** the program respectiely.

We will dissect this program soon, but first it is worth having a brief
discussion on what is happening when we run `gcc` and how the computer is
actually capable of running this code.

## How a C Porgram is Compiled

### Preprocessing

First the `#include <stdio.h>` serves to literally include the entire contents
of the file `stdio.h` into our file.  It is literally a simple cut and paste.
You probably won't see the file `stdio.h` in your current directory, but
the compiler, `gcc` is smart enough to look for it in other places on your
computer.  For example, on my personal computer, it is located at
`/Applications/Xcode.app/Contents/Developer/Platforms/AppleTVOS.platform/Developer/SDKs/AppleTVOS.sdk/usr/include/stdio.h`

### Compiling

While C is a very simple and "low-level" programming language, there are
languages which are even lower level.  These other languages are referred to as
"assembly languages".  In fact, programs written in assembly are the only ones
that can actually be run by computers.  All other programs are eventually
translated into this language to be run.  It is, however, extremely rare for
programmers to write in assembly

While they are lower level, and more directly tied to how the computer works,
they are much more difficult to write good programs in.  Let's take a look
at an example assembly program that prints "Hello, world" to the screen,
i.e. the equivalent to the 6 lines of C code above.

```asm
	.section	__TEXT,__text,regular,pure_instructions
	.build_version macos, 10, 15	sdk_version 10, 15, 4
	.intel_syntax noprefix
	.globl	_main                   ## -- Begin function main
	.p2align	4, 0x90
_main:                                  ## @main
	.cfi_startproc
## %bb.0:
	push	rbp
	.cfi_def_cfa_offset 16
	.cfi_offset rbp, -16
	mov	rbp, rsp
	.cfi_def_cfa_register rbp
	sub	rsp, 16
	mov	dword ptr [rbp - 4], 0
	lea	rdi, [rip + L_.str]
	mov	al, 0
	call	_printf
	xor	ecx, ecx
	mov	dword ptr [rbp - 8], eax ## 4-byte Spill
	mov	eax, ecx
	add	rsp, 16
	pop	rbp
	ret
	.cfi_endproc
                                        ## -- End function
	.section	__TEXT,__cstring,cstring_literals
L_.str:                                 ## @.str
	.asciz	"Hello, world\n"


.subsections_via_symbols
```

This assembly code is generated by the *Compiling* step of `gcc`.

You can see even though it is performing quite a simple task, the code
is anything but simple.  Luckily, you will not have to write any of this
code for this class, though if you'd like to learn more about it, you can
take the computer architecture course.  One of the reasons the code looks
so complex is that it was not written by a human, and it's not really meant
for human consumption, but computer consumption.

### Assembling

Now the computer is actually still not capable of reading this directly.  The
above is really only a human "readable" representation of what the computer
actually needs to read.  A representation closer to what the computer will
actually see is given below.  This is called "object code", and it can be
run directly by our computer.

```
cffa edfe 0700 0001 0300 0000 0100 0000  ................
0400 0000 0802 0000 0020 0000 0000 0000  ......... ......
1900 0000 8801 0000 0000 0000 0000 0000  ................
0000 0000 0000 0000 0000 0000 0000 0000  ................
9800 0000 0000 0000 2802 0000 0000 0000  ........(.......
9800 0000 0000 0000 0700 0000 0700 0000  ................
0400 0000 0000 0000 5f5f 7465 7874 0000  ........__text..
0000 0000 0000 0000 5f5f 5445 5854 0000  ........__TEXT..
0000 0000 0000 0000 0000 0000 0000 0000  ................
2a00 0000 0000 0000 2802 0000 0400 0000  *.......(.......
c002 0000 0200 0000 0004 0080 0000 0000  ................
0000 0000 0000 0000 5f5f 6373 7472 696e  ........__cstrin
6700 0000 0000 0000 5f5f 5445 5854 0000  g.......__TEXT..
0000 0000 0000 0000 2a00 0000 0000 0000  ........*.......
0e00 0000 0000 0000 5202 0000 0000 0000  ........R.......
0000 0000 0000 0000 0200 0000 0000 0000  ................
0000 0000 0000 0000 5f5f 636f 6d70 6163  ........__compac
745f 756e 7769 6e64 5f5f 4c44 0000 0000  t_unwind__LD....
0000 0000 0000 0000 3800 0000 0000 0000  ........8.......
2000 0000 0000 0000 6002 0000 0300 0000   .......`.......
d002 0000 0100 0000 0000 0002 0000 0000  ................
0000 0000 0000 0000 5f5f 6568 5f66 7261  ........__eh_fra
6d65 0000 0000 0000 5f5f 5445 5854 0000  me......__TEXT..
0000 0000 0000 0000 5800 0000 0000 0000  ........X.......
4000 0000 0000 0000 8002 0000 0300 0000  @...............
0000 0000 0000 0000 0b00 0068 0000 0000  ...........h....
0000 0000 0000 0000 3200 0000 1800 0000  ........2.......
0100 0000 000f 0a00 040f 0a00 0000 0000  ................
0200 0000 1800 0000 d802 0000 0200 0000  ................
f802 0000 1000 0000 0b00 0000 5000 0000  ............P...
0000 0000 0000 0000 0000 0000 0100 0000  ................
0100 0000 0100 0000 0000 0000 0000 0000  ................
0000 0000 0000 0000 0000 0000 0000 0000  ................
0000 0000 0000 0000 0000 0000 0000 0000  ................
0000 0000 0000 0000 5548 89e5 4883 ec10  ........UH..H...
c745 fc00 0000 0048 8d3d 1400 0000 b000  .E.....H.=......
e800 0000 0031 c989 45f8 89c8 4883 c410  .....1..E...H...
5dc3 4865 6c6c 6f2c 2077 6f72 6c64 0a00  ].Hello, world..
0000 0000 0000 0000 2a00 0000 0000 0001  ........*.......
0000 0000 0000 0000 0000 0000 0000 0000  ................
1400 0000 0000 0000 017a 5200 0178 1001  .........zR..x..
100c 0708 9001 0000 2400 0000 1c00 0000  ........$.......
88ff ffff ffff ffff 2a00 0000 0000 0000  ........*.......
0041 0e10 8602 430d 0600 0000 0000 0000  .A....C.........
1900 0000 0100 002d 1200 0000 0200 0015  .......-........
0000 0000 0100 0006 0100 0000 0f01 0000  ................
0000 0000 0000 0000 0700 0000 0100 0000  ................
0000 0000 0000 0000 005f 6d61 696e 005f  ........._main._
7072 696e 7466 0000                      printf..
```

the computer will only see all of the numbers and letters on the left.  The
right column is just a "readable" representation of the left column.

The letters and numbers in the left column above are, again, not really
what the computer sees but a more readable representation.  In reality
The computer reads *binary* which is better represented by the text below:

```
11001111 11111010 11101101 11111110 00000111 00000000
00000000 00000001 00000011 00000000 00000000 00000000
00000001 00000000 00000000 00000000 00000100 00000000
00000000 00000000 00001000 00000010 00000000 00000000
00000000 00100000 00000000 00000000 00000000 00000000
00000000 00000000 00011001 00000000 00000000 00000000
10001000 00000001 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 10011000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00101000 00000010 00000000 00000000 00000000 00000000
00000000 00000000 10011000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000111 00000000
00000000 00000000 00000111 00000000 00000000 00000000
00000100 00000000 00000000 00000000 00000000 00000000
00000000 00000000 01011111 01011111 01110100 01100101
01111000 01110100 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
01011111 01011111 01010100 01000101 01011000 01010100
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00101010 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00101000 00000010 00000000 00000000
00000100 00000000 00000000 00000000 11000000 00000010
00000000 00000000 00000010 00000000 00000000 00000000
00000000 00000100 00000000 10000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 01011111 01011111
01100011 01110011 01110100 01110010 01101001 01101110
01100111 00000000 00000000 00000000 00000000 00000000
00000000 00000000 01011111 01011111 01010100 01000101
01011000 01010100 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00101010 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00001110 00000000 00000000 00000000
00000000 00000000 00000000 00000000 01010010 00000010
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000010 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
01011111 01011111 01100011 01101111 01101101 01110000
01100001 01100011 01110100 01011111 01110101 01101110
01110111 01101001 01101110 01100100 01011111 01011111
01001100 01000100 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00111000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00100000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
01100000 00000010 00000000 00000000 00000011 00000000
00000000 00000000 11010000 00000010 00000000 00000000
00000001 00000000 00000000 00000000 00000000 00000000
00000000 00000010 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 01011111 01011111 01100101 01101000
01011111 01100110 01110010 01100001 01101101 01100101
00000000 00000000 00000000 00000000 00000000 00000000
01011111 01011111 01010100 01000101 01011000 01010100
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 01011000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
01000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 10000000 00000010 00000000 00000000
00000011 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00001011 00000000 00000000 01101000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00110010 00000000
00000000 00000000 00011000 00000000 00000000 00000000
00000001 00000000 00000000 00000000 00000000 00001111
00001010 00000000 00000100 00001111 00001010 00000000
00000000 00000000 00000000 00000000 00000010 00000000
00000000 00000000 00011000 00000000 00000000 00000000
11011000 00000010 00000000 00000000 00000010 00000000
00000000 00000000 11111000 00000010 00000000 00000000
00010000 00000000 00000000 00000000 00001011 00000000
00000000 00000000 01010000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000001 00000000 00000000 00000000 00000001 00000000
00000000 00000000 00000001 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
01010101 01001000 10001001 11100101 01001000 10000011
11101100 00010000 11000111 01000101 11111100 00000000
00000000 00000000 00000000 01001000 10001101 00111101
00010100 00000000 00000000 00000000 10110000 00000000
11101000 00000000 00000000 00000000 00000000 00110001
11001001 10001001 01000101 11111000 10001001 11001000
01001000 10000011 11000100 00010000 01011101 11000011
01001000 01100101 01101100 01101100 01101111 00101100
00100000 01110111 01101111 01110010 01101100 01100100
00001010 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00101010 00000000
00000000 00000000 00000000 00000000 00000000 00000001
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00010100 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000001 01111010 01010010 00000000 00000001 01111000
00010000 00000001 00010000 00001100 00000111 00001000
10010000 00000001 00000000 00000000 00100100 00000000
00000000 00000000 00011100 00000000 00000000 00000000
10001000 11111111 11111111 11111111 11111111 11111111
11111111 11111111 00101010 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 01000001
00001110 00010000 10000110 00000010 01000011 00001101
00000110 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00011001 00000000 00000000 00000000
00000001 00000000 00000000 00101101 00010010 00000000
00000000 00000000 00000010 00000000 00000000 00010101
00000000 00000000 00000000 00000000 00000001 00000000
00000000 00000110 00000001 00000000 00000000 00000000
00001111 00000001 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000111 00000000 00000000 00000000 00000001 00000000
00000000 00000000 00000000 00000000 00000000 00000000
00000000 00000000 00000000 00000000 00000000 01011111
01101101 01100001 01101001 01101110 00000000 01011111
01110000 01110010 01101001 01101110 01110100 01100110
00000000 00000000
```

These ones and zeros have many different ways of being physically represented
to the computer.  They could be magnetic spin, like in a hard drive, electric
charge of capacitors like in RAM, or the voltage on a device called a
"transistor" like in your computer's processor.  We leave discussion of
these devices to more advanced courses.

### Linking

In the case of our *hello world* program, we are using `printf` from `stdio.h
which represents code we did not write.  This code does not live in our
program, and it is not even present anywhere in the binary above.  In fact, the
code does not even live in the `stdio.h` file, but it was precompiled into
object code.  So how is it that out program can still be executed correctly?

The answer is that there is one final stage to all of this which is called
"Linking".  During the linking stage, our binary is somehow merged with their
binary to produce the final executable file, and that is all there is to it.

### Summary

To recap the overall operation of `gcc` here:

1. You write a program in C and run something like `gcc hello.c`
2. Your code is transformed into another C program (Preprocessing)
2. Your code is transformed to assembly (Compiling)
3. The assembly is automatically converted to object code (Assembling)
4. The object code is merged with other object code to produce a working
program (Linking)

## Dissecting Hello World

Now that we've gotten through some of the technical details of what is
going on when we run `gcc`, let's talk about how to interpret the code
itself.  The code is given below again for reference.

```
// hello.c
#include <stdio.h>

int main() {
    printf("Hello, world\n");
    return 0;
}
```

The first line, `// hello.c` is called a comment.  You can tell it is a
comment because it starts with `//`.  This tells the compiler to ignore
every character that follows.  This line will be completely removed by
the preprocessing step.  It is only there to serve as a guide to the reader
of the program, in this case giving the file name.

The second line, `#include <stdio.h>` is called a *preprocessor directive*
because is gives directions to the preprocessor, you could also just call it an
"include." This line says to find a file with the name `stdio.h` and replace
this line with the entire contents of that file, just before compiling.  We
need this line in order to get `printf` which is used leter.

The third line, `int main() {` is called a *function definition* This line says
that we are defining a *function* called main.  The empty `()` means the
function takes no *arguments* (no inputs).  The `int` means that the function
*returns* an integer value.  The curly brace `{` denotes the start of the
function, saying that everything that comes next will be executed when when the
function runs.  We will go over functions in more depth later, but the `main`
function is particularly important and special, because it is the first
function called when the program starts.

The fourth line, `printf("Hello, world\n");` is called a `statement` In this
statement, we are *calling* a function called `printf`, which we "got" from
`stdio.h`.  The thing in the parentheses, `"Hello, world\n"` is the argument
(input) to the function.  The `\n` is a special sequence of characters called
an *escape sequence* meaning it does not literally represent the characters you
see, but the "newline" character which represents something like hitting enter
on the keyboard.  The semicolon `;` signifes the end of the statement.  All
statements in C must end with a `;`.

The fifth line, `return 0;` is a special kind of statement called a *return
statement* which says we are done running the function, and whoever called it
should get the value given, in this case `0`.  Note that the value we return
here is an integer, just as our function promised on the line starting its
definition.

The sixth line, `}` says simply that we are done defining the function.

---

# Introduction to Makefiles

> If we have enough time

A Makefile is a file that helps you automate your development workflow.  It is
consumed by a simple yet powerful program called `make`.  Note that for all
examples, the file must be called `Makefile` or `make` will not detect it.

## A Simple Example

This is a very simple makefile.

```Makefile
greet:
	echo "hello"
```

There is one `target` named `greet` and one command associated with that
target, `echo "hello"`.  If you run `make greet` the command will be run.

Note one common mistake with creating makefiles: every command must be
started with a `tab`, not spaces.  If you were to uses spaces instead, you
would get the confusing error `Makefile:2: *** missing separator.  Stop.`

## Dependencies

You probably would not need a makefile if you only needed to run one command.
The general case is that there are many steps to getting a project ready, and
some of them depend on others.  This example shows a simple case of using
a dependency in a Makefile.

```Makefile
greet:
	echo "hello"

farewell: greet
	echo "goodbye"
```

Clearly, if you are to give someone a farewell, you must greet them first.

If you run `make farewell` you will see that `greet` is first run, and then
`farewell`  This is because `farewell: greet` says that `farewell` is dependent
on `greet`.

Note also, if you only run `make`, only the target `greet` will be run.  This
is because the top target is run by default.

## Files

The most common case for a Makefile is generating files from code which are not
otherwise stored because they are too large, not compatible with GitHub, or
dependent on the user's machine.  This is example will avoid that for
simplicity.  Instead, we will use a regular bash script which depends on a
file.  For example, you should never upload compiled C files.

```Makefile
build: hello.out

hello.out: hello.c
	gcc hello.c -o hello.out

clean:
	rm hello.out

test: hello.out
	./hello.out
```

Now we have file dependencies.  This `Makefile` says that the file we are
making, `hello.out` depends on `hello.c`.  This helps avoid the common
mistake of changing a source file, and then forgetting to recompile it.

Try running `make build`, you should see that `hello.c` has been generated.
Now if you run `make build` again, you should see the message `make: Nothing to
be done for 'build'.`.  `make` is saying that since the dependency `hello.c`
has not been updated since `hello.c` was created, there is not need to make it
again.

# Conclusion

With that, you should have a general understanding of what is happening when
you compile a C program, as well as the basic anatomy of the simplest possible
"Hello World" program.
