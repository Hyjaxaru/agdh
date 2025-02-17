# A Game Developer's Handbook

![ADGH Logo](docs/assets/hero_transparent.png)

http://agdh.hyjaxaru.dev

A fun little resource to help out with the new L6 Game Design course.

Made in collaboration with [INSERT SCHOOL NAME HERE] (Im not doxxing myself ❤)

Thanks for an amazing year :]

# Contributing

If you want to contribute to the site,
then you should fork the repository and make a pull request when you're done.

Every page has "View source for this page" and "Edit this page" buttons,
so making changes shouldn't be too hard.
The GitHub repo also has a Code Space set up for development.

If you **DO** contribute to a page,
your GitHub account will be displayed at the bottom of the respective page on the site.
Ensuring you are given credit for your work!

# Working with MKDocs 

> [!NOTE]
> This is assuming you are doing development on your local machine.
> If you are using the provided GitHub Code Space, you can skip this.
>
> You may also follow these steps if you are setting up a new GitHub Code Space.
> You won't need visual studio however, as those parts are pre-installed.

AGDH uses MKDocs to build the site,
and Material for MKDocs for site theming.
These can be installed using `pip` in a Python environment of your choosing.

```bash
pip install mkdocs
pip install mkdocs-material
```

We also use the social plugin for link embedding,
which is a little more complicated.
You will need Visual Studio for this (TLDR: you need C stuff),
but the python side can be downloaded as follows:

```bash
pip install mkdocs-material[imaging]
```

There are a few additional plugins needed,
which can be downloaded in a similar manner.

- Revision Dates
- Git Committers

```bash
pip install mkdocs-git-revision-date-localized-plugin
pip install mkdocs-git-committers-plugin-2
```

That should be it for your environment!

## Best Practice
