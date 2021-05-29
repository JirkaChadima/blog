---
title: "reMarkable 2 on Steroids"
date: 2021-05-29T11:07:35+02:00
draft: false
---

I was always a fan of e-ink displays and paper-like digital experience. I still own
an old [Boogie Board Sync](https://www.amazon.com/Boogie-Board-LCD-Writing-Tablet/dp/B00E8CIGCA),
but I haven't used it for a while, because the inability to edit the files was a buzzkill.
But now, I bought a new toy: [reMarkable 2](https://remarkable.com/).

I'm still learning how to use it in a really efficient way in my daily life, but one thing I knew
I really, really wanted, was an online sync. And you can get that with a mobile app or a desktop app
(no Linux though). Not enough for me. I wanted git.

---

## Community!

There is a [huge list of extensions](https://github.com/reHackable/awesome-reMarkable) and tools
related to reMarkable tablet put together by an avid community. Since the tablet is running an
instance of Linux *and* offers an [SSH connection](https://remarkablewiki.com/tech/ssh) over the
USB cable, you can tinker with the system pretty easily.

First, there is a package manager called [Entware](https://github.com/evidlo/remarkable_entware).
A few shell commands are you are in business. After the installation and `opkg install git` you
just got yourself `git` on your e-ink tablet. How cool is that?

## Backing up

To take it one step further, you can set up an automatic backup with
[reGitable](https://github.com/after-eight/regitable). This sets up an OS-level service which listens
to changes on filesystem and when something happens, it creates a new commit and pushes it to your
remote repository of choice.

Now, this is great for keeping track of the history of your files, but it doesn't really help with
the workflow, because your scribbles are represented as proprietary binary `.rm` files. That format
is being referred to as _Lines_ and even though there are libraries that claim they can process the format
I was not successful in getting a usable picture out of them.

Truth to be told, there are JPG thumbnails on reMarkable's filesystem, but those have a really low resolution.

## Ideal workflow

What do I actually want? I want fully functioning live OCR, obviously. So I take a note on remarkable,
it is OCRed and it is stored in git repo where it gets versioned and I can work with it further. Easy peasy.

So what is the next step for me? I have two options:

1. Convert the Lines file which I already have in a repo into a picture and run OCR on top of that.
1. Use the OCR to email feature on the tablet and pull emails into the repo.

Both options are probably viable, but I would really like to learn how to convert the raw files into
something readable on my PC, because that opens up a whole another world of possibilities.

But that's going to be another blog post.
