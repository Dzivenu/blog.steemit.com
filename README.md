A proof of concept blog for steem.io, built using greymass/reprint.

## Configuration

### resources/config/config.yml

```
# reprint config
reprint:
  # Choose the locale to localize content for
  locale: 'en'

# blog config
blog:
  # Choose a theme by name
  theme: 'steem.io'
  title: 'Steem Blog'
  # Filter the content to
  filters:
    # Accounts to load activity of
    accounts:
      'steemitblog':
        - post

# steemd connection
steem:
  # Steem Node to retreive data
  host: 'https://node.steem.ws'
```

### resources/config/routes.yml

```
config.routes:
  # Homepage route to handle the options provided in the configuration
  homepage:
    name: 'homepage'
    pattern: /
    method: ['get']
    controller: 'Reprint\Controller\Home::homeAction'

  # View Post
  post_view:
    name: 'post_view'
    pattern: /{category}/@{author}/{permlink}
    method: ['get']
    controller: 'Reprint\Controller\Blog::postAction'

  # View Tagged Posts
  tag_view:
    name: 'tag_view'
    pattern: /tagged/{category}
    method: ['get']
    controller: 'Reprint\Controller\Blog::listAction'
```
