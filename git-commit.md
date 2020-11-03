# Source control

We use Git source control to manage our code base and host them on GitHub. Therefore, a basic knowledge of Git is required. Here, we explain the Git tools we commonly, including branching and commit conventions.

# Clients

Typically, we use the Git CLI client as is our recommended way of using Git. However, if you prefer a GUI client, we use [SourceTree](https://www.sourcetreeapp.com/) by Bitbucket (Windows and Mac OS only). The reason for using SourceTree is that it has the standard Git Flow branching model built in. More on the branching method below.

# Branching

The branching method is highly dependent on context. Nonetheless, branching model we conventionally use for projects is based on this popular branching model by Vincent Driessen.

[https://nvie.com/posts/a-successful-git-branching-model/](https://nvie.com/posts/a-successful-git-branching-model/)

## Git Flow

Git Flow is the Git extension to assist with the branching model we use. Refer to the resources below for installation instructions.

**Introduction**: [https://jeffkreeftmeijer.com/git-flow/](https://jeffkreeftmeijer.com/git-flow/)

**Installation instructions**: [https://github.com/nvie/gitflow/wiki/Installation](https://github.com/nvie/gitflow/wiki/Installation)

**Git Flow with Source Tree:** [https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)

## Commit messages

Git commit messages are split by title and body. Generally, we only use the title to summarize 'what' was committed. The body (or more technically accurate, the second line) is used if you need to explain more elaborately the context or 'why' the change is required.

```bash
git commit -m "The title is here. To summarize what is changed" -m "The body is here if needed. To elaborate the reason or context on why the change is made"
```

The 'how' is explained in the code. Therefore, that is not included in the commit message.

### Length

Writing good commit messages is essential to communicate context with others and also your future self. Limit the title to 50 characters to be concise. If cannot explain in short, the may be committing too much at once (refer to atomic approach below). The upper limit we suggest is 72 as that is the length which GitHub truncates messages when displaying.

### Imperative

Write commit messages in the imperative, such as 'fix' instead of 'fixed' or fixes'. The reason is that the imperative is consistent with the default auto-generated messages on Git. As an example, when using 'git merge', the auto-generated commit message is 'Merge branch feature/myfeature'. So when you write your commit messages in the imperative, you’re following Git’s own built-in conventions.

Imperative example

- *Fix* bug on Y

Writing this way can be a little awkward at first. We’re more used to speaking in the indicative mood, which is all about reporting facts. That’s why commit messages often end up reading like this:

- Fixed bug with Y
- Fixes bug on Y
- Changing behavior of X

And sometimes commit messages get written as a description of their contents:

- More fixes for broken stuff
- Sweet new API methods
- To remove any confusion, here’s a simple rule to get it right every time.

A properly formed Git commit subject line should always be able to complete the following sentence:

**If applied, this commit will** your subject line here

Thus, it's appropriate to start your subject line with a verb keyword such as fix, add, update, change, remove.

## Atomic approach to commits

You are encouraged to follow the Atomic commits approach. Atomic commits are smaller and frequent commits.

**The reasons for atomic commits are:**

- Easy to roll back without affecting other changes
- Easy to make other changes on the fly
- Easy to merge features to other branches

**To achieve the atomic approach to commits:**

- Commit each fix or task as a separate change
- Only commit when a block of work is complete, ensure it can be compiled.
- Commit each layout change separately
- Joint commit for layout file, code behind file, and additional resources