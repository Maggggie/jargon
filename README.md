## Jargon

To post on [Jargon](http://jargon.io), just fork this repo and check your Markdown-formatted articles into the `/articles` directory. We'll automatically detect and publish your content at [jargon.io/yourgithubusername](http://jargon.io/yourgithubusername).

### Drafts

You can post drafts to the `/drafts` directory. This will allow you to privately preview your posts before you publish them. To publish them, simply move them to the `/articles` directory in your repo.

### Images

You can store images anywhere in your repo and refer to them in your articles with relative paths. For instance, if you had `example.gif` in the `/images` directory, then you could refer to it like this:

```
![example](/images/example.gif)
```

### Extended Markdown

Jargon supports an extended version of [GitHub-flavored Markdown](https://help.github.com/articles/github-flavored-markdown/). In addition to normal fenced code blocks, you can also reference code files stored in your `/snippets` directory.

This will embed the file `foo.rb` stored in the `/snippets` folder.

```
[snippet: foo.rb]
```

This will embed lines 18-24 from the file `foo.rb` stored in the `/snippets` folder.

```
[snippet: foo.rb:18,24]
```

### Tags

We'll automatically detect which languages you use in your posts and add a tag for each one. You can also manually add tags with the `[tag: ]`... tag. You can find an example [here](https://github.com/jargon-io/jargon/blob/master/articles/example.md).

### Bio

Anything you add to your repo's bio.txt file will show up on your profile page and any articles you post. We truncate at 250 characters and allow the use of \<a\> tags.
