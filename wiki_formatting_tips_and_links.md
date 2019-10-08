## Useful links - Wiki features

This wiki uses the [Markdown](http://daringfireball.net/projects/markdown/) syntax. 

1. The [MarkDown Demo tutorial](https://about.gitlab.com/handbook/product/technical-writing/markdown-guide/) shows how various elements are rendered.
2. This 5min video shows how to use markdown for creating [issues](https://www.youtube.com/watch?v=Ix416lAYRSg).
3. The [GitLab documentation](https://docs.gitlab.com/ee/user/project/wiki/) has more information about using a wiki.
4. This video shows how can you use [boards and issues](https://www.youtube.com/watch?v=CiolDtBIOA0) to integrate agile methodologies for working in your team.

The wiki itself is actually a git repository, which means you can clone it, edit it locally/offline, add images or any other file type, and push it back to us. It will be live immediately.

Go ahead and try:

```
$ git clone https://gitlab.eng.unimelb.edu.au/nlipovetzky/comp90054-pacman.wiki.git
```

Wiki pages are normal files, with the .md extension. You can edit them locally, as well as creating new ones.

## Syntax highlighting



Here's an example of some Python code:

```python

def wiki_rocks(text):
    formatter = lambda t: "funky"+t
    return formatter(text)
```


You can check out the source of this page to see how that's done. Just clone the wiki and get inspired to start your own project wiki.


Have fun!