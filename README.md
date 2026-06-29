# Publish Demo

A page to demonstrate how to use the output of the [publish to web tool](https://github.com/Chat-Hackers/publish-tool).

Here's the rendered version: https://chat-hackers.github.io/publish-tool-demo-site/

## Key Part

The script is the key part of the demonstration. The publishUrl comes from the publish tool. A simple GET request using fetch is made, and then converted to JSON, then iterated through to create some html from each post.

```
        const publishUrl = `https://dashboard.chathackers.uk/publish/api/posts?groupId=`;

        fetch(publishUrl)
            .then(res => res.json())
            .then(posts => {
            posts.forEach(post => {
                    const postElement = document.createElement('p');
                    postElement.innerHTML = post.text;
                    postElement.className = "post"
                    updateContainer.appendChild(postElement);
            [...]
                })
            })
```
